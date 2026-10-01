Preciso que funcione em duas etapas:

1. Rode o Script SQL completo para subir o backend no Supabase antes
    
2. Execute o Prompt otimizado para o Lovable instruindo a IA a primeiro rodar o SQL e só depois construir o frontend com base no Sprint
    

A lógica aqui é simples: o Lovable tende a performar melhor quando já recebe uma base de dados clara, com relações, regras e nomes consistentes.

---

# 1) Script SQL — Neuron MVP

> Rode este script no **Supabase SQL Editor** antes de enviar o prompt ao Lovable.

```sql
-- =========================================================
-- NEURON MVP - DATABASE SETUP
-- Supabase / PostgreSQL
-- =========================================================

-- Extensões úteis
create extension if not exists "pgcrypto";

-- =========================================================
-- ENUMS
-- =========================================================

do $$
begin
  if not exists (select 1 from pg_type where typname = 'subscription_status') then
    create type subscription_status as enum ('free', 'active', 'canceled', 'expired', 'past_due');
  end if;
end$$;

do $$
begin
  if not exists (select 1 from pg_type where typname = 'content_status') then
    create type content_status as enum ('draft', 'published');
  end if;
end$$;

do $$
begin
  if not exists (select 1 from pg_type where typname = 'attempt_status') then
    create type attempt_status as enum ('started', 'submitted', 'reviewed');
  end if;
end$$;

-- =========================================================
-- UPDATED_AT HELPER
-- =========================================================

create or replace function public.set_updated_at()
returns trigger
language plpgsql
as $$
begin
  new.updated_at = now();
  return new;
end;
$$;

-- =========================================================
-- PROFILES
-- Cada usuário autenticado tem um perfil
-- =========================================================

create table if not exists public.profiles (
  id uuid primary key references auth.users(id) on delete cascade,
  full_name text,
  avatar_url text,
  bio text,
  role text not null default 'student' check (role in ('student', 'admin')),
  onboarding_completed boolean not null default false,
  daily_goal integer not null default 1,
  streak_count integer not null default 0,
  last_lesson_completed_at timestamptz,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now()
);

drop trigger if exists trg_profiles_updated_at on public.profiles;
create trigger trg_profiles_updated_at
before update on public.profiles
for each row
execute function public.set_updated_at();

-- =========================================================
-- TRACKS
-- Trilhas de aprendizado
-- =========================================================

create table if not exists public.tracks (
  id uuid primary key default gen_random_uuid(),
  slug text not null unique,
  title text not null,
  short_description text,
  description text,
  cover_image_url text,
  icon text,
  is_premium boolean not null default false,
  sort_order integer not null default 0,
  status content_status not null default 'draft',
  estimated_minutes integer,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now()
);

drop trigger if exists trg_tracks_updated_at on public.tracks;
create trigger trg_tracks_updated_at
before update on public.tracks
for each row
execute function public.set_updated_at();

-- =========================================================
-- MODULES
-- Módulos dentro de uma trilha
-- =========================================================

create table if not exists public.modules (
  id uuid primary key default gen_random_uuid(),
  track_id uuid not null references public.tracks(id) on delete cascade,
  title text not null,
  short_description text,
  description text,
  sort_order integer not null default 0,
  status content_status not null default 'draft',
  is_locked_by_default boolean not null default false,
  estimated_minutes integer,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now(),
  unique(track_id, sort_order)
);

drop trigger if exists trg_modules_updated_at on public.modules;
create trigger trg_modules_updated_at
before update on public.modules
for each row
execute function public.set_updated_at();

-- =========================================================
-- LESSONS
-- Lições dentro de um módulo
-- =========================================================

create table if not exists public.lessons (
  id uuid primary key default gen_random_uuid(),
  module_id uuid not null references public.modules(id) on delete cascade,
  title text not null,
  short_description text,
  lesson_type text not null default 'exercise' check (lesson_type in ('concept', 'exercise', 'quiz', 'mixed')),
  concept_text text,
  example_prompt text,
  exercise_title text,
  exercise_instructions text,
  expected_outcome text,
  feedback_success text,
  feedback_improve text,
  xp_reward integer not null default 10,
  sort_order integer not null default 0,
  status content_status not null default 'draft',
  estimated_minutes integer,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now(),
  unique(module_id, sort_order)
);

drop trigger if exists trg_lessons_updated_at on public.lessons;
create trigger trg_lessons_updated_at
before update on public.lessons
for each row
execute function public.set_updated_at();

-- =========================================================
-- USER TRACK PROGRESS
-- Progresso macro por trilha
-- =========================================================

create table if not exists public.user_track_progress (
  id uuid primary key default gen_random_uuid(),
  user_id uuid not null references auth.users(id) on delete cascade,
  track_id uuid not null references public.tracks(id) on delete cascade,
  started_at timestamptz default now(),
  completed_at timestamptz,
  progress_percent numeric(5,2) not null default 0,
  lessons_completed integer not null default 0,
  total_lessons integer not null default 0,
  current_module_id uuid references public.modules(id) on delete set null,
  current_lesson_id uuid references public.lessons(id) on delete set null,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now(),
  unique(user_id, track_id)
);

drop trigger if exists trg_user_track_progress_updated_at on public.user_track_progress;
create trigger trg_user_track_progress_updated_at
before update on public.user_track_progress
for each row
execute function public.set_updated_at();

-- =========================================================
-- USER LESSON PROGRESS
-- Progresso por lição
-- =========================================================

create table if not exists public.user_lesson_progress (
  id uuid primary key default gen_random_uuid(),
  user_id uuid not null references auth.users(id) on delete cascade,
  lesson_id uuid not null references public.lessons(id) on delete cascade,
  status text not null default 'not_started' check (status in ('not_started', 'in_progress', 'completed')),
  started_at timestamptz,
  completed_at timestamptz,
  attempts_count integer not null default 0,
  best_score integer not null default 0,
  last_response text,
  last_feedback text,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now(),
  unique(user_id, lesson_id)
);

drop trigger if exists trg_user_lesson_progress_updated_at on public.user_lesson_progress;
create trigger trg_user_lesson_progress_updated_at
before update on public.user_lesson_progress
for each row
execute function public.set_updated_at();

-- =========================================================
-- LESSON ATTEMPTS
-- Tentativas do usuário em exercícios
-- =========================================================

create table if not exists public.lesson_attempts (
  id uuid primary key default gen_random_uuid(),
  user_id uuid not null references auth.users(id) on delete cascade,
  lesson_id uuid not null references public.lessons(id) on delete cascade,
  attempt_number integer not null default 1,
  submitted_response text,
  ai_feedback text,
  score integer not null default 0 check (score >= 0 and score <= 100),
  status attempt_status not null default 'submitted',
  created_at timestamptz not null default now()
);

-- =========================================================
-- SUBSCRIPTIONS
-- Controle de plano do usuário
-- =========================================================

create table if not exists public.subscriptions (
  id uuid primary key default gen_random_uuid(),
  user_id uuid not null unique references auth.users(id) on delete cascade,
  plan_name text not null default 'free',
  status subscription_status not null default 'free',
  stripe_customer_id text unique,
  stripe_subscription_id text unique,
  current_period_start timestamptz,
  current_period_end timestamptz,
  cancel_at_period_end boolean not null default false,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now()
);

drop trigger if exists trg_subscriptions_updated_at on public.subscriptions;
create trigger trg_subscriptions_updated_at
before update on public.subscriptions
for each row
execute function public.set_updated_at();

-- =========================================================
-- APP SETTINGS / ADS
-- Configuração simples de banners internos
-- =========================================================

create table if not exists public.ads (
  id uuid primary key default gen_random_uuid(),
  title text not null,
  body text,
  image_url text,
  cta_text text,
  cta_url text,
  active boolean not null default true,
  placement text not null default 'lesson_end' check (placement in ('lesson_end', 'dashboard', 'track_page')),
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now()
);

drop trigger if exists trg_ads_updated_at on public.ads;
create trigger trg_ads_updated_at
before update on public.ads
for each row
execute function public.set_updated_at();

-- =========================================================
-- AUTO CREATE PROFILE + SUBSCRIPTION
-- =========================================================

create or replace function public.handle_new_user()
returns trigger
language plpgsql
security definer
set search_path = public
as $$
begin
  insert into public.profiles (id, full_name)
  values (new.id, coalesce(new.raw_user_meta_data->>'full_name', ''));

  insert into public.subscriptions (user_id, plan_name, status)
  values (new.id, 'free', 'free');

  return new;
end;
$$;

drop trigger if exists on_auth_user_created on auth.users;
create trigger on_auth_user_created
after insert on auth.users
for each row
execute function public.handle_new_user();

-- =========================================================
-- ENABLE RLS
-- =========================================================

alter table public.profiles enable row level security;
alter table public.tracks enable row level security;
alter table public.modules enable row level security;
alter table public.lessons enable row level security;
alter table public.user_track_progress enable row level security;
alter table public.user_lesson_progress enable row level security;
alter table public.lesson_attempts enable row level security;
alter table public.subscriptions enable row level security;
alter table public.ads enable row level security;

-- =========================================================
-- RLS: PROFILES
-- =========================================================

drop policy if exists "Users can view own profile" on public.profiles;
create policy "Users can view own profile"
on public.profiles
for select
to authenticated
using (auth.uid() = id);

drop policy if exists "Users can update own profile" on public.profiles;
create policy "Users can update own profile"
on public.profiles
for update
to authenticated
using (auth.uid() = id)
with check (auth.uid() = id);

-- =========================================================
-- RLS: PUBLIC LEARNING CONTENT
-- Authenticated users can read published content
-- =========================================================

drop policy if exists "Authenticated users can view published tracks" on public.tracks;
create policy "Authenticated users can view published tracks"
on public.tracks
for select
to authenticated
using (status = 'published');

drop policy if exists "Authenticated users can view published modules" on public.modules;
create policy "Authenticated users can view published modules"
on public.modules
for select
to authenticated
using (status = 'published');

drop policy if exists "Authenticated users can view published lessons" on public.lessons;
create policy "Authenticated users can view published lessons"
on public.lessons
for select
to authenticated
using (status = 'published');

drop policy if exists "Authenticated users can view active ads" on public.ads;
create policy "Authenticated users can view active ads"
on public.ads
for select
to authenticated
using (active = true);

-- =========================================================
-- RLS: USER TRACK PROGRESS
-- =========================================================

drop policy if exists "Users can view own track progress" on public.user_track_progress;
create policy "Users can view own track progress"
on public.user_track_progress
for select
to authenticated
using (auth.uid() = user_id);

drop policy if exists "Users can insert own track progress" on public.user_track_progress;
create policy "Users can insert own track progress"
on public.user_track_progress
for insert
to authenticated
with check (auth.uid() = user_id);

drop policy if exists "Users can update own track progress" on public.user_track_progress;
create policy "Users can update own track progress"
on public.user_track_progress
for update
to authenticated
using (auth.uid() = user_id)
with check (auth.uid() = user_id);

-- =========================================================
-- RLS: USER LESSON PROGRESS
-- =========================================================

drop policy if exists "Users can view own lesson progress" on public.user_lesson_progress;
create policy "Users can view own lesson progress"
on public.user_lesson_progress
for select
to authenticated
using (auth.uid() = user_id);

drop policy if exists "Users can insert own lesson progress" on public.user_lesson_progress;
create policy "Users can insert own lesson progress"
on public.user_lesson_progress
for insert
to authenticated
with check (auth.uid() = user_id);

drop policy if exists "Users can update own lesson progress" on public.user_lesson_progress;
create policy "Users can update own lesson progress"
on public.user_lesson_progress
for update
to authenticated
using (auth.uid() = user_id)
with check (auth.uid() = user_id);

-- =========================================================
-- RLS: LESSON ATTEMPTS
-- =========================================================

drop policy if exists "Users can view own attempts" on public.lesson_attempts;
create policy "Users can view own attempts"
on public.lesson_attempts
for select
to authenticated
using (auth.uid() = user_id);

drop policy if exists "Users can insert own attempts" on public.lesson_attempts;
create policy "Users can insert own attempts"
on public.lesson_attempts
for insert
to authenticated
with check (auth.uid() = user_id);

-- =========================================================
-- RLS: SUBSCRIPTIONS
-- =========================================================

drop policy if exists "Users can view own subscription" on public.subscriptions;
create policy "Users can view own subscription"
on public.subscriptions
for select
to authenticated
using (auth.uid() = user_id);

-- IMPORTANT:
-- Do not allow normal authenticated users to update subscription directly.
-- Subscription updates should be done by secure backend / webhooks only.

-- =========================================================
-- HELPER VIEW: USER ACCESS LEVEL
-- =========================================================

create or replace view public.user_access as
select
  s.user_id,
  s.plan_name,
  s.status,
  case
    when s.status = 'active' then true
    else false
  end as is_premium
from public.subscriptions s;

-- =========================================================
-- SEED: TRACK + MODULES + SAMPLE LESSONS
-- MVP inicial da trilha de Prompt Engineering
-- =========================================================

insert into public.tracks (
  slug, title, short_description, description, icon, is_premium, sort_order, status, estimated_minutes
)
values (
  'engenharia-de-prompt',
  'Engenharia de Prompt',
  'Aprenda a escrever prompts melhores com clareza, estrutura e prática.',
  'Trilha inicial do Neuron baseada no livro The Art of Asking ChatGPT for High-Quality Answers. O foco é ensinar técnicas de prompt engineering em uma jornada guiada, gamificada e prática.',
  'sparkles',
  false,
  1,
  'published',
  180
)
on conflict (slug) do nothing;

with selected_track as (
  select id from public.tracks where slug = 'engenharia-de-prompt'
)
insert into public.modules (track_id, title, short_description, description, sort_order, status, estimated_minutes)
select id, 'Fundamentos de Prompt', 'Base conceitual da trilha.', 'Introdução ao que é prompt engineering, estrutura de prompt e mentalidade correta para obter respostas melhores.', 1, 'published', 35 from selected_track
union all
select id, 'Técnicas Essenciais', 'Principais técnicas do livro.', 'Aprenda instruction prompting, role prompting, standard prompts, seed-word e self-consistency.', 2, 'published', 50 from selected_track
union all
select id, 'Técnicas Intermediárias', 'Aplicação prática orientada.', 'Zero-shot, one-shot, few-shot, summarization, question-answering, dialogue e knowledge prompts.', 3, 'published', 55 from selected_track
union all
select id, 'Técnicas Avançadas', 'Camada avançada e estratégica.', 'Controlled generation, clustering, sentiment analysis, classification, curriculum learning e reinforcement learning prompts.', 4, 'published', 40 from selected_track
on conflict do nothing;

-- Lições de exemplo do módulo 1
with m as (
  select m.id
  from public.modules m
  join public.tracks t on t.id = m.track_id
  where t.slug = 'engenharia-de-prompt'
    and m.sort_order = 1
)
insert into public.lessons (
  module_id, title, short_description, lesson_type, concept_text, example_prompt,
  exercise_title, exercise_instructions, expected_outcome, feedback_success, feedback_improve,
  xp_reward, sort_order, status, estimated_minutes
)
select
  id,
  'O que é Prompt Engineering?',
  'Entenda o papel do prompt na qualidade da resposta.',
  'mixed',
  'Prompt engineering é o processo de criar instruções claras para guiar a saída do modelo. Quanto mais claro o objetivo, o contexto e o formato desejado, melhor tende a ser a resposta.',
  'Explique o que é energia solar para um aluno de 12 anos em 3 tópicos curtos.',
  'Reescreva um prompt ruim',
  'Transforme o pedido "fale de energia solar" em um prompt melhor, deixando objetivo, público e formato claros.',
  'O usuário deve produzir um prompt mais específico, com tarefa, público e formato.',
  'Ótimo. Seu prompt ficou mais claro, específico e orientado ao resultado.',
  'Seu prompt ainda está genérico. Tente especificar a tarefa, para quem a resposta é e em qual formato ela deve vir.',
  10,
  1,
  'published',
  5
from m
union all
select
  id,
  'Estrutura de um bom prompt',
  'Aprenda os blocos básicos de um prompt forte.',
  'mixed',
  'Uma boa estrutura de prompt geralmente combina tarefa, contexto, instruções e formato de saída. Em alguns casos, também vale definir papel, restrições e exemplos.',
  'Atue como professor de biologia e explique fotossíntese em uma linguagem simples, com 5 bullets e 1 analogia.',
  'Monte um prompt completo',
  'Crie um prompt para pedir um resumo de um texto jurídico em linguagem simples para leigos.',
  'O usuário deve combinar tarefa, contexto, público e formato.',
  'Muito bom. Você organizou os elementos essenciais do prompt.',
  'Tente incluir melhor o contexto e o formato exato da saída.',
  10,
  2,
  'published',
  5
from m
on conflict do nothing;

-- =========================================================
-- HELPER FUNCTION: RECALCULATE TRACK PROGRESS
-- Pode ser chamada pelo app após concluir lição
-- =========================================================

create or replace function public.recalculate_track_progress(p_user_id uuid, p_track_id uuid)
returns void
language plpgsql
security definer
set search_path = public
as $$
declare
  v_total_lessons integer;
  v_completed_lessons integer;
  v_progress numeric(5,2);
  v_current_lesson uuid;
  v_current_module uuid;
begin
  select count(*)
    into v_total_lessons
  from public.lessons l
  join public.modules m on m.id = l.module_id
  where m.track_id = p_track_id
    and l.status = 'published';

  select count(*)
    into v_completed_lessons
  from public.user_lesson_progress ulp
  join public.lessons l on l.id = ulp.lesson_id
  join public.modules m on m.id = l.module_id
  where ulp.user_id = p_user_id
    and ulp.status = 'completed'
    and m.track_id = p_track_id
    and l.status = 'published';

  if v_total_lessons = 0 then
    v_progress := 0;
  else
    v_progress := round((v_completed_lessons::numeric / v_total_lessons::numeric) * 100, 2);
  end if;

  select l.id, l.module_id
    into v_current_lesson, v_current_module
  from public.lessons l
  join public.modules m on m.id = l.module_id
  where m.track_id = p_track_id
    and l.status = 'published'
    and l.id not in (
      select lesson_id
      from public.user_lesson_progress
      where user_id = p_user_id
        and status = 'completed'
    )
  order by m.sort_order asc, l.sort_order asc
  limit 1;

  insert into public.user_track_progress (
    user_id, track_id, started_at, progress_percent, lessons_completed, total_lessons, current_module_id, current_lesson_id
  )
  values (
    p_user_id, p_track_id, now(), v_progress, v_completed_lessons, v_total_lessons, v_current_module, v_current_lesson
  )
  on conflict (user_id, track_id)
  do update set
    progress_percent = excluded.progress_percent,
    lessons_completed = excluded.lessons_completed,
    total_lessons = excluded.total_lessons,
    current_module_id = excluded.current_module_id,
    current_lesson_id = excluded.current_lesson_id,
    completed_at = case when excluded.progress_percent >= 100 then now() else public.user_track_progress.completed_at end,
    updated_at = now();
end;
$$;
```

---

# 2) Prompt otimizado para o Lovable

> Esse prompt já está escrito para o Lovable entender a ordem correta:  
> **1. Backend/SQL primeiro**  
> **2. Frontend depois**  
> **3. Implementar o SaaS inteiro com base no Sprint**

```
Quero que você implemente o SaaS Neuron seguindo rigorosamente o Sprint de telas anexado cujo o nome é "Sprint Neuron.md", os arquivos de contexto do projeto e a estrutura técnica abaixo. 

## ORDEM OBRIGATÓRIA DE EXECUÇÃO

Você deve seguir exatamente esta ordem:

### PASSO 1 — BACKEND PRIMEIRO
Antes de qualquer coisa, considere que o banco de dados deve ser criado primeiro.

Execute o script SQL fornecido <script_sql></script_sql> para estruturar o backend no Supabase.

A implementação deve começar pelo backend:
- criar as tabelas
- criar os relacionamentos
- respeitar as regras de negócio
- respeitar o modelo de autenticação
- respeitar o controle de progresso
- respeitar o modelo de assinatura
- respeitar o sistema de trilhas, módulos e lições
- respeitar as políticas de segurança e RLS

### PASSO 2 — FRONTEND DEPOIS
Somente depois da estrutura do banco estar pronta, implemente o frontend completo do Neuron com base no Sprint de telas descrito em "Sprint Neuron.md".

O frontend deve ser conectado ao backend.

Não crie primeiro telas soltas e depois tente adaptar.
Primeiro estruture corretamente o backend, depois construa a interface conectada ao banco de dados (vulgo backend).

---

## CONTEXTO DO PRODUTO

O Neuron é um SaaS de aprendizado gamificado sobre Inteligência Artificial.

Porém, o MVP terá inicialmente apenas uma trilha principal:

### Engenharia de Prompt

Essa trilha deve ser o coração do produto neste MVP.

O produto precisa transmitir:
- simplicidade
- elegância
- baixa fricção
- progressão clara
- aprendizado rápido
- feedback imediato
- gamificação leve
- sensação de avanço constante
- experiência moderna e minimalista

O Neuron não deve parecer um curso tradicional.
Ele deve parecer uma plataforma viva de aprendizado guiado.

---

## STACK / TECNOLOGIAS

Use:
- arquitetura organizada e limpa
- componentes reutilizáveis
- navegação clara
- estados bem tratados
- integração do frontend com backend

---

## REGRAS DE NEGÓCIO

Implemente as seguintes regras:

- usuários podem criar conta e fazer login
- todo usuário do MVP é um aluno
- cada usuário tem um perfil
- o dashboard mostra trilhas disponíveis
- no MVP existe uma trilha principal: **Engenharia de Prompt**
- trilhas possuem módulos
- módulos possuem lições
- lições possuem:
  - conceito
  - exemplo
  - exercício
  - feedback
- o progresso deve ser salvo por usuário
- o usuário deve poder continuar de onde parou
- o plano free exibe anúncios ao final das lições
- o plano premium não exibe anúncios
- o dashboard deve ter chamada clara para **Seja Premium**
- deve existir tela de assinatura premium
- deve existir perfil do aluno
- deve existir tela de configurações
- deve existir fluxo de onboarding
- deve existir recuperação de senha
- deve existir feedback visual de conclusão de lição e progresso

---

## ESTRUTURA DA EXPERIÊNCIA

Implemente as telas e fluxos do Sprint, incluindo:

### Público
- Landing page
- Login
- Cadastro
- Recuperação de senha

### Primeira experiência
- Splash/loading inicial
- Onboarding
- Criação/complemento do perfil
- Entrada rápida na trilha

### Área logada
- Dashboard
- Card de trilha
- Botão “Continuar aprendendo”
- Indicador de progresso
- Card ou botão “Seja Premium”
- Perfil
- Configurações

### Aprendizado
- Página da trilha
- Página de módulos
- Página de lições
- Bloco de conceito
- Exemplo de prompt
- Exercício
- Campo de resposta
- Feedback imediato
- Estado concluído
- Próxima lição
- Desbloqueio progressivo

### Premium
- Página de benefícios
- Página de assinatura
- Estado premium ativo
- Ocultação de anúncios quando premium

### Free
- Exibir anúncio/bloque de promoção ao final das lições

---

## TRILHA DE ENGENHARIA DE PROMPT

Monte a trilha principal com base nos arquivos de contexto e na estrutura já modelada no banco.

Estruture a trilha em módulos e lições progressivas.

A interface deve permitir:
- ver a trilha
- ver módulos
- abrir lições
- concluir lições
- salvar progresso
- retomar de onde parou

Use a trilha já iniciada no banco como base e, se necessário, complemente no frontend a apresentação de módulos, lições e progresso.

---

## SEGURANÇA

Respeite integralmente a lógica de segurança:

- autenticação obrigatória para área logada
- usuário só pode ver e editar o próprio perfil
- usuário só pode ver o próprio progresso
- usuário só pode ver a própria assinatura
- atualização de assinatura não deve ser simulada como se fosse livre no cliente
- o frontend deve respeitar as tabelas e políticas já definidas
- não permitir atalhos inseguros ou quebra da lógica de acesso

---

## DIRETRIZES DE UI / UX

Quero uma interface:
- minimalista
- moderna
- elegante
- intuitiva
- limpa
- bem espaçada
- com cara de produto real
- com sensação de produto premium
- com navegação simples
- com estados vazios bem resolvidos
- com boa hierarquia visual
- com progress bars, cards e feedbacks visuais consistentes

A experiência deve lembrar um produto educacional moderno, com inspiração em plataformas gamificadas como Duolingo, mas com estética mais limpa e madura.

---

## COMPORTAMENTOS IMPORTANTES

Implemente corretamente:

- continuar da última lição
- marcar lição como concluída
- recalcular progresso da trilha
- mostrar percentual de progresso
- mostrar módulos concluídos / em andamento
- diferenciar usuário free e premium
- mostrar anúncio apenas para free ao fim da lição
- remover anúncio para premium
- mostrar status da assinatura no perfil/configurações
- permitir editar perfil
- permitir alterar senha
- permitir logout

---

## O QUE NÃO FAZER

- não comece pelo frontend ignorando o backend
- não crie telas desconectadas da base real
- não simplifique demais a experiência
- não entregue apenas layout
- não ignore o Product Loop
- não ignore a lógica de progresso
- não ignore a diferença entre free e premium
- não ignore o Sprint
- não troque os nomes principais do domínio sem necessidade

---

## SQL OFICIAL DO PROJETO

Use este SQL como base oficial para o backend do Neuron e considere que ele deve ser aplicado primeiro no Supabase antes da construção do frontend:


<script_sql>
-- =========================================================
-- NEURON MVP - DATABASE SETUP
-- Supabase / PostgreSQL
-- =========================================================

-- Extensões úteis
create extension if not exists "pgcrypto";

-- =========================================================
-- ENUMS
-- =========================================================

do $$
begin
  if not exists (select 1 from pg_type where typname = 'subscription_status') then
    create type subscription_status as enum ('free', 'active', 'canceled', 'expired', 'past_due');
  end if;
end$$;

do $$
begin
  if not exists (select 1 from pg_type where typname = 'content_status') then
    create type content_status as enum ('draft', 'published');
  end if;
end$$;

do $$
begin
  if not exists (select 1 from pg_type where typname = 'attempt_status') then
    create type attempt_status as enum ('started', 'submitted', 'reviewed');
  end if;
end$$;

-- =========================================================
-- UPDATED_AT HELPER
-- =========================================================

create or replace function public.set_updated_at()
returns trigger
language plpgsql
as $$
begin
  new.updated_at = now();
  return new;
end;
$$;

-- =========================================================
-- PROFILES
-- Cada usuário autenticado tem um perfil
-- =========================================================

create table if not exists public.profiles (
  id uuid primary key references auth.users(id) on delete cascade,
  full_name text,
  avatar_url text,
  bio text,
  role text not null default 'student' check (role in ('student', 'admin')),
  onboarding_completed boolean not null default false,
  daily_goal integer not null default 1,
  streak_count integer not null default 0,
  last_lesson_completed_at timestamptz,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now()
);

drop trigger if exists trg_profiles_updated_at on public.profiles;
create trigger trg_profiles_updated_at
before update on public.profiles
for each row
execute function public.set_updated_at();

-- =========================================================
-- TRACKS
-- Trilhas de aprendizado
-- =========================================================

create table if not exists public.tracks (
  id uuid primary key default gen_random_uuid(),
  slug text not null unique,
  title text not null,
  short_description text,
  description text,
  cover_image_url text,
  icon text,
  is_premium boolean not null default false,
  sort_order integer not null default 0,
  status content_status not null default 'draft',
  estimated_minutes integer,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now()
);

drop trigger if exists trg_tracks_updated_at on public.tracks;
create trigger trg_tracks_updated_at
before update on public.tracks
for each row
execute function public.set_updated_at();

-- =========================================================
-- MODULES
-- Módulos dentro de uma trilha
-- =========================================================

create table if not exists public.modules (
  id uuid primary key default gen_random_uuid(),
  track_id uuid not null references public.tracks(id) on delete cascade,
  title text not null,
  short_description text,
  description text,
  sort_order integer not null default 0,
  status content_status not null default 'draft',
  is_locked_by_default boolean not null default false,
  estimated_minutes integer,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now(),
  unique(track_id, sort_order)
);

drop trigger if exists trg_modules_updated_at on public.modules;
create trigger trg_modules_updated_at
before update on public.modules
for each row
execute function public.set_updated_at();

-- =========================================================
-- LESSONS
-- Lições dentro de um módulo
-- =========================================================

create table if not exists public.lessons (
  id uuid primary key default gen_random_uuid(),
  module_id uuid not null references public.modules(id) on delete cascade,
  title text not null,
  short_description text,
  lesson_type text not null default 'exercise' check (lesson_type in ('concept', 'exercise', 'quiz', 'mixed')),
  concept_text text,
  example_prompt text,
  exercise_title text,
  exercise_instructions text,
  expected_outcome text,
  feedback_success text,
  feedback_improve text,
  xp_reward integer not null default 10,
  sort_order integer not null default 0,
  status content_status not null default 'draft',
  estimated_minutes integer,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now(),
  unique(module_id, sort_order)
);

drop trigger if exists trg_lessons_updated_at on public.lessons;
create trigger trg_lessons_updated_at
before update on public.lessons
for each row
execute function public.set_updated_at();

-- =========================================================
-- USER TRACK PROGRESS
-- Progresso macro por trilha
-- =========================================================

create table if not exists public.user_track_progress (
  id uuid primary key default gen_random_uuid(),
  user_id uuid not null references auth.users(id) on delete cascade,
  track_id uuid not null references public.tracks(id) on delete cascade,
  started_at timestamptz default now(),
  completed_at timestamptz,
  progress_percent numeric(5,2) not null default 0,
  lessons_completed integer not null default 0,
  total_lessons integer not null default 0,
  current_module_id uuid references public.modules(id) on delete set null,
  current_lesson_id uuid references public.lessons(id) on delete set null,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now(),
  unique(user_id, track_id)
);

drop trigger if exists trg_user_track_progress_updated_at on public.user_track_progress;
create trigger trg_user_track_progress_updated_at
before update on public.user_track_progress
for each row
execute function public.set_updated_at();

-- =========================================================
-- USER LESSON PROGRESS
-- Progresso por lição
-- =========================================================

create table if not exists public.user_lesson_progress (
  id uuid primary key default gen_random_uuid(),
  user_id uuid not null references auth.users(id) on delete cascade,
  lesson_id uuid not null references public.lessons(id) on delete cascade,
  status text not null default 'not_started' check (status in ('not_started', 'in_progress', 'completed')),
  started_at timestamptz,
  completed_at timestamptz,
  attempts_count integer not null default 0,
  best_score integer not null default 0,
  last_response text,
  last_feedback text,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now(),
  unique(user_id, lesson_id)
);

drop trigger if exists trg_user_lesson_progress_updated_at on public.user_lesson_progress;
create trigger trg_user_lesson_progress_updated_at
before update on public.user_lesson_progress
for each row
execute function public.set_updated_at();

-- =========================================================
-- LESSON ATTEMPTS
-- Tentativas do usuário em exercícios
-- =========================================================

create table if not exists public.lesson_attempts (
  id uuid primary key default gen_random_uuid(),
  user_id uuid not null references auth.users(id) on delete cascade,
  lesson_id uuid not null references public.lessons(id) on delete cascade,
  attempt_number integer not null default 1,
  submitted_response text,
  ai_feedback text,
  score integer not null default 0 check (score >= 0 and score <= 100),
  status attempt_status not null default 'submitted',
  created_at timestamptz not null default now()
);

-- =========================================================
-- SUBSCRIPTIONS
-- Controle de plano do usuário
-- =========================================================

create table if not exists public.subscriptions (
  id uuid primary key default gen_random_uuid(),
  user_id uuid not null unique references auth.users(id) on delete cascade,
  plan_name text not null default 'free',
  status subscription_status not null default 'free',
  stripe_customer_id text unique,
  stripe_subscription_id text unique,
  current_period_start timestamptz,
  current_period_end timestamptz,
  cancel_at_period_end boolean not null default false,
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now()
);

drop trigger if exists trg_subscriptions_updated_at on public.subscriptions;
create trigger trg_subscriptions_updated_at
before update on public.subscriptions
for each row
execute function public.set_updated_at();

-- =========================================================
-- APP SETTINGS / ADS
-- Configuração simples de banners internos
-- =========================================================

create table if not exists public.ads (
  id uuid primary key default gen_random_uuid(),
  title text not null,
  body text,
  image_url text,
  cta_text text,
  cta_url text,
  active boolean not null default true,
  placement text not null default 'lesson_end' check (placement in ('lesson_end', 'dashboard', 'track_page')),
  created_at timestamptz not null default now(),
  updated_at timestamptz not null default now()
);

drop trigger if exists trg_ads_updated_at on public.ads;
create trigger trg_ads_updated_at
before update on public.ads
for each row
execute function public.set_updated_at();

-- =========================================================
-- AUTO CREATE PROFILE + SUBSCRIPTION
-- =========================================================

create or replace function public.handle_new_user()
returns trigger
language plpgsql
security definer
set search_path = public
as $$
begin
  insert into public.profiles (id, full_name)
  values (new.id, coalesce(new.raw_user_meta_data->>'full_name', ''));

  insert into public.subscriptions (user_id, plan_name, status)
  values (new.id, 'free', 'free');

  return new;
end;
$$;

drop trigger if exists on_auth_user_created on auth.users;
create trigger on_auth_user_created
after insert on auth.users
for each row
execute function public.handle_new_user();

-- =========================================================
-- ENABLE RLS
-- =========================================================

alter table public.profiles enable row level security;
alter table public.tracks enable row level security;
alter table public.modules enable row level security;
alter table public.lessons enable row level security;
alter table public.user_track_progress enable row level security;
alter table public.user_lesson_progress enable row level security;
alter table public.lesson_attempts enable row level security;
alter table public.subscriptions enable row level security;
alter table public.ads enable row level security;

-- =========================================================
-- RLS: PROFILES
-- =========================================================

drop policy if exists "Users can view own profile" on public.profiles;
create policy "Users can view own profile"
on public.profiles
for select
to authenticated
using (auth.uid() = id);

drop policy if exists "Users can update own profile" on public.profiles;
create policy "Users can update own profile"
on public.profiles
for update
to authenticated
using (auth.uid() = id)
with check (auth.uid() = id);

-- =========================================================
-- RLS: PUBLIC LEARNING CONTENT
-- Authenticated users can read published content
-- =========================================================

drop policy if exists "Authenticated users can view published tracks" on public.tracks;
create policy "Authenticated users can view published tracks"
on public.tracks
for select
to authenticated
using (status = 'published');

drop policy if exists "Authenticated users can view published modules" on public.modules;
create policy "Authenticated users can view published modules"
on public.modules
for select
to authenticated
using (status = 'published');

drop policy if exists "Authenticated users can view published lessons" on public.lessons;
create policy "Authenticated users can view published lessons"
on public.lessons
for select
to authenticated
using (status = 'published');

drop policy if exists "Authenticated users can view active ads" on public.ads;
create policy "Authenticated users can view active ads"
on public.ads
for select
to authenticated
using (active = true);

-- =========================================================
-- RLS: USER TRACK PROGRESS
-- =========================================================

drop policy if exists "Users can view own track progress" on public.user_track_progress;
create policy "Users can view own track progress"
on public.user_track_progress
for select
to authenticated
using (auth.uid() = user_id);

drop policy if exists "Users can insert own track progress" on public.user_track_progress;
create policy "Users can insert own track progress"
on public.user_track_progress
for insert
to authenticated
with check (auth.uid() = user_id);

drop policy if exists "Users can update own track progress" on public.user_track_progress;
create policy "Users can update own track progress"
on public.user_track_progress
for update
to authenticated
using (auth.uid() = user_id)
with check (auth.uid() = user_id);

-- =========================================================
-- RLS: USER LESSON PROGRESS
-- =========================================================

drop policy if exists "Users can view own lesson progress" on public.user_lesson_progress;
create policy "Users can view own lesson progress"
on public.user_lesson_progress
for select
to authenticated
using (auth.uid() = user_id);

drop policy if exists "Users can insert own lesson progress" on public.user_lesson_progress;
create policy "Users can insert own lesson progress"
on public.user_lesson_progress
for insert
to authenticated
with check (auth.uid() = user_id);

drop policy if exists "Users can update own lesson progress" on public.user_lesson_progress;
create policy "Users can update own lesson progress"
on public.user_lesson_progress
for update
to authenticated
using (auth.uid() = user_id)
with check (auth.uid() = user_id);

-- =========================================================
-- RLS: LESSON ATTEMPTS
-- =========================================================

drop policy if exists "Users can view own attempts" on public.lesson_attempts;
create policy "Users can view own attempts"
on public.lesson_attempts
for select
to authenticated
using (auth.uid() = user_id);

drop policy if exists "Users can insert own attempts" on public.lesson_attempts;
create policy "Users can insert own attempts"
on public.lesson_attempts
for insert
to authenticated
with check (auth.uid() = user_id);

-- =========================================================
-- RLS: SUBSCRIPTIONS
-- =========================================================

drop policy if exists "Users can view own subscription" on public.subscriptions;
create policy "Users can view own subscription"
on public.subscriptions
for select
to authenticated
using (auth.uid() = user_id);

-- IMPORTANT:
-- Do not allow normal authenticated users to update subscription directly.
-- Subscription updates should be done by secure backend / webhooks only.

-- =========================================================
-- HELPER VIEW: USER ACCESS LEVEL
-- =========================================================

create or replace view public.user_access as
select
  s.user_id,
  s.plan_name,
  s.status,
  case
    when s.status = 'active' then true
    else false
  end as is_premium
from public.subscriptions s;

-- =========================================================
-- SEED: TRACK + MODULES + SAMPLE LESSONS
-- MVP inicial da trilha de Prompt Engineering
-- =========================================================

insert into public.tracks (
  slug, title, short_description, description, icon, is_premium, sort_order, status, estimated_minutes
)
values (
  'engenharia-de-prompt',
  'Engenharia de Prompt',
  'Aprenda a escrever prompts melhores com clareza, estrutura e prática.',
  'Trilha inicial do Neuron baseada no livro The Art of Asking ChatGPT for High-Quality Answers. O foco é ensinar técnicas de prompt engineering em uma jornada guiada, gamificada e prática.',
  'sparkles',
  false,
  1,
  'published',
  180
)
on conflict (slug) do nothing;

with selected_track as (
  select id from public.tracks where slug = 'engenharia-de-prompt'
)
insert into public.modules (track_id, title, short_description, description, sort_order, status, estimated_minutes)
select id, 'Fundamentos de Prompt', 'Base conceitual da trilha.', 'Introdução ao que é prompt engineering, estrutura de prompt e mentalidade correta para obter respostas melhores.', 1, 'published', 35 from selected_track
union all
select id, 'Técnicas Essenciais', 'Principais técnicas do livro.', 'Aprenda instruction prompting, role prompting, standard prompts, seed-word e self-consistency.', 2, 'published', 50 from selected_track
union all
select id, 'Técnicas Intermediárias', 'Aplicação prática orientada.', 'Zero-shot, one-shot, few-shot, summarization, question-answering, dialogue e knowledge prompts.', 3, 'published', 55 from selected_track
union all
select id, 'Técnicas Avançadas', 'Camada avançada e estratégica.', 'Controlled generation, clustering, sentiment analysis, classification, curriculum learning e reinforcement learning prompts.', 4, 'published', 40 from selected_track
on conflict do nothing;

-- Lições de exemplo do módulo 1
with m as (
  select m.id
  from public.modules m
  join public.tracks t on t.id = m.track_id
  where t.slug = 'engenharia-de-prompt'
    and m.sort_order = 1
)
insert into public.lessons (
  module_id, title, short_description, lesson_type, concept_text, example_prompt,
  exercise_title, exercise_instructions, expected_outcome, feedback_success, feedback_improve,
  xp_reward, sort_order, status, estimated_minutes
)
select
  id,
  'O que é Prompt Engineering?',
  'Entenda o papel do prompt na qualidade da resposta.',
  'mixed',
  'Prompt engineering é o processo de criar instruções claras para guiar a saída do modelo. Quanto mais claro o objetivo, o contexto e o formato desejado, melhor tende a ser a resposta.',
  'Explique o que é energia solar para um aluno de 12 anos em 3 tópicos curtos.',
  'Reescreva um prompt ruim',
  'Transforme o pedido "fale de energia solar" em um prompt melhor, deixando objetivo, público e formato claros.',
  'O usuário deve produzir um prompt mais específico, com tarefa, público e formato.',
  'Ótimo. Seu prompt ficou mais claro, específico e orientado ao resultado.',
  'Seu prompt ainda está genérico. Tente especificar a tarefa, para quem a resposta é e em qual formato ela deve vir.',
  10,
  1,
  'published',
  5
from m
union all
select
  id,
  'Estrutura de um bom prompt',
  'Aprenda os blocos básicos de um prompt forte.',
  'mixed',
  'Uma boa estrutura de prompt geralmente combina tarefa, contexto, instruções e formato de saída. Em alguns casos, também vale definir papel, restrições e exemplos.',
  'Atue como professor de biologia e explique fotossíntese em uma linguagem simples, com 5 bullets e 1 analogia.',
  'Monte um prompt completo',
  'Crie um prompt para pedir um resumo de um texto jurídico em linguagem simples para leigos.',
  'O usuário deve combinar tarefa, contexto, público e formato.',
  'Muito bom. Você organizou os elementos essenciais do prompt.',
  'Tente incluir melhor o contexto e o formato exato da saída.',
  10,
  2,
  'published',
  5
from m
on conflict do nothing;

-- =========================================================
-- HELPER FUNCTION: RECALCULATE TRACK PROGRESS
-- Pode ser chamada pelo app após concluir lição
-- =========================================================

create or replace function public.recalculate_track_progress(p_user_id uuid, p_track_id uuid)
returns void
language plpgsql
security definer
set search_path = public
as $$
declare
  v_total_lessons integer;
  v_completed_lessons integer;
  v_progress numeric(5,2);
  v_current_lesson uuid;
  v_current_module uuid;
begin
  select count(*)
    into v_total_lessons
  from public.lessons l
  join public.modules m on m.id = l.module_id
  where m.track_id = p_track_id
    and l.status = 'published';

  select count(*)
    into v_completed_lessons
  from public.user_lesson_progress ulp
  join public.lessons l on l.id = ulp.lesson_id
  join public.modules m on m.id = l.module_id
  where ulp.user_id = p_user_id
    and ulp.status = 'completed'
    and m.track_id = p_track_id
    and l.status = 'published';

  if v_total_lessons = 0 then
    v_progress := 0;
  else
    v_progress := round((v_completed_lessons::numeric / v_total_lessons::numeric) * 100, 2);
  end if;

  select l.id, l.module_id
    into v_current_lesson, v_current_module
  from public.lessons l
  join public.modules m on m.id = l.module_id
  where m.track_id = p_track_id
    and l.status = 'published'
    and l.id not in (
      select lesson_id
      from public.user_lesson_progress
      where user_id = p_user_id
        and status = 'completed'
    )
  order by m.sort_order asc, l.sort_order asc
  limit 1;

  insert into public.user_track_progress (
    user_id, track_id, started_at, progress_percent, lessons_completed, total_lessons, current_module_id, current_lesson_id
  )
  values (
    p_user_id, p_track_id, now(), v_progress, v_completed_lessons, v_total_lessons, v_current_module, v_current_lesson
  )
  on conflict (user_id, track_id)
  do update set
    progress_percent = excluded.progress_percent,
    lessons_completed = excluded.lessons_completed,
    total_lessons = excluded.total_lessons,
    current_module_id = excluded.current_module_id,
    current_lesson_id = excluded.current_lesson_id,
    completed_at = case when excluded.progress_percent >= 100 then now() else public.user_track_progress.completed_at end,
    updated_at = now();
end;
$$;
</script_sql>

---

## RESULTADO ESPERADO

Quero o SaaS Neuron implementado de forma funcional, com:

- backend coerente
- frontend completo
- autenticação real
- dashboard funcional
- trilha funcional
- progresso salvo
- páginas conectadas ao Supabase
- perfil funcional
- premium estruturado
- experiência de aprendizado clara, bonita e pronta para evoluir

Se precisar fazer pequenas adaptações técnicas para a implementação funcionar melhor, mantenha a essência do produto, a arquitetura do banco e o Sprint como fonte principal de verdade.
```

---

## Como usar na prática

1. **Rode o SQL no Supabase**
    
2. **Copie o prompt acima**
    
3. No trecho `[COLE AQUI O SCRIPT SQL COMPLETO]`, cole o script SQL que te entreguei
    
4. Anexe junto no Lovable:
    
    - Sprint
        
    - Product Loop
        
    - Mapa de Navegação
        
    - Detalhes Técnicos
        
    - Manifesto
        
    - MVP
        
    - Pitch Deck
        
    - livro do Prompt Engineering
        

---

## Recomendação importante

Antes de mandar para o Lovable, vale muito a pena eu te entregar uma **versão 2 desse SQL com seed completo da trilha de Prompt Engineering**, já com vários módulos e lições preenchidos.  
Isso pode aumentar bastante a chance de o Lovable construir o Neuron de forma muito mais consistente.