O seu objetivo é criar por completo o SaaS "Ágora", para isso primeiro execute o passo um, primeiro execute o Script SQL e depois execute o passo 2, execute a criação do código. Crie primeiro a Database para depois criar o código. Crie o Database no próprio Lovable Cloud, para a Database não vamos usar a API externa.

Estou anexando dois arquivos que você pode usar como apoio para criar o SaaS, o primeiro é o contexto completo do SaaS (todos os detalhes) e o segundo é um guia de telas que você deve usar de referência junto ao prompt da etapa 2.

Use as cores:
Fundo: f2f1ef
60%: 9bd1ba
30% f6b561
10%: ea534c

### PASSO 1: O Script SQL (Rode isso no seu Supabase)

Crie um projeto no Supabase, vá até o **SQL Editor**, cole o código abaixo e clique em *Run*. Este script cria as tabelas, configura os planos iniciais, os agentes, vincula a autenticação e aplica as regras de segurança (RLS) descritas no seu documento.

```sql
-- ========================================================
-- BANCO DE DADOS ÁGORA - SCRIPT DE INICIALIZAÇÃO (SUPABASE)
-- ========================================================

-- 1. TABELAS DE CONFIGURAÇÃO E ASSINATURA
CREATE TABLE public.plan (
    id BIGINT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    price DECIMAL(10, 2) NOT NULL,
    uploads_limit INTEGER NOT NULL,
    recurrence VARCHAR(20) NOT NULL
);

-- Tabela de Usuários vinculada ao auth.users do Supabase
CREATE TABLE public.users (
    id UUID PRIMARY KEY REFERENCES auth.users(id) ON DELETE CASCADE,
    name VARCHAR(255),
    email VARCHAR(255) UNIQUE NOT NULL,
    plan_id BIGINT REFERENCES public.plan(id) DEFAULT 1,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- 2. TABELAS DE NEGÓCIO E FLUXO DE ANÁLISE
CREATE TABLE public.user_request (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID NOT NULL REFERENCES public.users(id) ON DELETE CASCADE,
    content TEXT NOT NULL,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
    updated_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

CREATE TABLE public.user_uploads (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    user_id UUID NOT NULL REFERENCES public.users(id) ON DELETE CASCADE,
    request_id UUID REFERENCES public.user_request(id),
    file_url TEXT NOT NULL,
    content_transcription TEXT,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- 3. TABELAS DO SISTEMA MULTI-AGENTE
CREATE TABLE public.agent (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    agent_name VARCHAR(100) NOT NULL,
    agent_type VARCHAR(50) NOT NULL
);

CREATE TABLE public.agent_response (
    id BIGINT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    agent_id UUID NOT NULL REFERENCES public.agent(id),
    request_id UUID NOT NULL REFERENCES public.user_request(id) ON DELETE CASCADE,
    content JSONB NOT NULL,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

CREATE TABLE public.agent_uploads (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    agent_id UUID NOT NULL REFERENCES public.agent(id),
    request_id UUID NOT NULL REFERENCES public.user_request(id),
    content TEXT NOT NULL,
    created_at TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- 4. INSERÇÃO DE DADOS INICIAIS (SEED)
INSERT INTO public.plan (name, price, uploads_limit, recurrence) VALUES
('Freemium', 0.00, 2, 'mensal'),
('Standard', 97.00, 5, 'mensal'),
('Pro', 297.00, 999999, 'mensal'),
('Enterprise', 997.00, 999999, 'mensal');

INSERT INTO public.agent (agent_name, agent_type) VALUES
('Agente Orquestrador Master', 'Master'),
('Analista Sociocomportamental', 'Analista'),
('Engenheiro de Oferta e Valor', 'Analista'),
('Cientista de Dados de Performance', 'Analista'),
('Estrategista-Chefe', 'Sintetizador');

-- 5. TRIGGER DE AUTENTICAÇÃO (Cria perfil automaticamente após SignUp)
CREATE OR REPLACE FUNCTION public.handle_new_user() 
RETURNS trigger AS $$
BEGIN
  INSERT INTO public.users (id, email, name, plan_id)
  VALUES (new.id, new.email, new.raw_user_meta_data->>'full_name', 1);
  RETURN new;
END;
$$ LANGUAGE plpgsql SECURITY DEFINER;

CREATE TRIGGER on_auth_user_created
  AFTER INSERT ON auth.users
  FOR EACH ROW EXECUTE PROCEDURE public.handle_new_user();

-- ========================================================
-- 6. ROW LEVEL SECURITY (RLS) - GOVERNANÇA DE DADOS
-- ========================================================
ALTER TABLE public.plan ENABLE ROW LEVEL SECURITY;
ALTER TABLE public.users ENABLE ROW LEVEL SECURITY;
ALTER TABLE public.user_request ENABLE ROW LEVEL SECURITY;
ALTER TABLE public.user_uploads ENABLE ROW LEVEL SECURITY;
ALTER TABLE public.agent ENABLE ROW LEVEL SECURITY;
ALTER TABLE public.agent_response ENABLE ROW LEVEL SECURITY;
ALTER TABLE public.agent_uploads ENABLE ROW LEVEL SECURITY;

-- Políticas
CREATE POLICY "Planos são públicos para leitura" ON public.plan FOR SELECT USING (true);
CREATE POLICY "Agentes são públicos para leitura" ON public.agent FOR SELECT USING (true);

CREATE POLICY "Usuário gerencia seu perfil" ON public.users 
FOR ALL USING (auth.uid() = id);

CREATE POLICY "Usuário gerencia suas requisições" ON public.user_request 
FOR ALL USING (auth.uid() = user_id);

CREATE POLICY "Usuário gerencia seus uploads" ON public.user_uploads 
FOR ALL USING (auth.uid() = user_id);

CREATE POLICY "Usuário lê respostas de agentes da sua requisição" ON public.agent_response 
FOR SELECT USING (
    EXISTS (SELECT 1 FROM public.user_request WHERE id = agent_response.request_id AND user_id = auth.uid())
);
```

---

### PASSO 2: O Prompt Mestre para o Lovable

Copie o texto abaixo **exatamente como está** e cole no primeiro chat de criação do Lovable. Ele servirá como o "documento de arquitetura" para a IA construir o frontend com precisão.

***

**PROMPT PARA O LOVABLE:**

```text
Act as a Senior Full-Stack React Developer. I need you to build the MVP for "Ágora", an AI-powered B2B Marketing SaaS. 

The tech stack must be: React, Vite, Tailwind CSS, shadcn/ui, Lucide Icons, and Supabase (for Auth, Database, and Storage).

CRITICAL CONTEXT:
I have ALREADY executed the SQL script in my Supabase instance. The database tables (plan, users, user_request, user_uploads, agent, agent_response), triggers, and RLS policies already exist. Do NOT try to invent a new database schema. Your job is to connect to this structure and build the UI, routing, and business logic.

APP VIBE & STYLING:
Professional, C-Level consulting tool (think McKinsey meets modern AI). Dark mode enabled by default. Clean layouts, high-end typography, glassmorphism effects for cards, and smooth transitions.

Please build the application with the following 5 main areas:

1. LANDING PAGE & AUTHENTICATION
- A hero section: "O Marketing que Prevê o Futuro" with a CTA "Começar Agora".
- Features section and a Pricing section displaying the 4 plans (Freemium, Standard, Pro, Enterprise).
- Supabase Auth implementation: Login and Signup pages (Email/Password).
- Upon signup, redirect the user to the Dashboard. (Note: my DB trigger will automatically set them to the Freemium plan).

2. DASHBOARD (Hub Central)
- Protected route (requires Auth).
- Sidebar navigation: "Nova Análise", "Histórico de Campanhas", "Configurações".
- Main area: Display basic user stats (current plan, uploads used vs limit).
- A grid showing recent analysis cards (fetched from `user_request` table).

3. CHAT INTERFACE (Core Engine - "Nova Análise")
- A ChatGPT-style interface where the user talks to "Agent Prin".
- An upload button (File input) to attach files. 
- BUSINESS LOGIC: Before uploading, query the `users` and `plan` tables. Check if `uploads_limit` is reached for the day. If yes, block the upload and show an "Upgrade Plan" modal.
- When the user sends a message, save it to `user_request`.
- Create a visual "Processing Checklist" UI that simulates the AI thinking (Orchestrator -> Socio-behavioral -> Offer -> Performance -> Synthesizer) with loaders.

4. THE REPORT PAGE (Apresentação da Campanha Otimizada)
- Once the "analysis" is done, navigate the user to the Report Dashboard.
- Show a Score Circle (0-100).
- Render tabs: "Visão Geral", "Canais", "Audiência", "Criativos".
- Display the content using Markdown rendering (react-markdown), as the AI will output the final strategy in Markdown format.
- Add "Export" buttons (PDF, Canva, Gamma) - for now, make them just trigger a toast notification.
- Include a Like/Dislike (👍/👎) feedback section at the bottom.

5. INFRASTRUCTURE & API CALLS
- Create a Supabase client utility.
- Use React Query (@tanstack/react-query) for fetching user data, requests, and plans.
- Mock the AI response for now: When a user submits a campaign in the chat, wait 3 seconds, create a mock entry in `agent_response`, and redirect to the Report Page with a mocked Markdown report.

Let's do this step-by-step. Start by setting up the routing, the Supabase Auth wrapper, and the main Landing Page layout. Do not write the whole app in one file, use a modular component architecture.
```