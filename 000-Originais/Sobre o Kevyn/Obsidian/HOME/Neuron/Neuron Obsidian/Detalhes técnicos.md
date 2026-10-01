Perfeito. Agora entramos na parte que mais ajuda o **Lovable a não se perder**: transformar a visão do produto em **regras claras, permissões, integrações e segurança**.

Como o **MVP do Neuron** foi reduzido para uma estrutura de SaaS com **auth, perfil de aluno, trilha inicial de Engenharia de Prompt, plano free/premium e anúncios no plano gratuito**, a modelagem técnica precisa refletir exatamente isso.  
Além disso, o conceito-base do produto continua sendo uma plataforma de aprendizado gamificada, com jornada guiada, interface simples e feedback rápido.

---

# Fase 6 — Modelagem Técnica

## 13 — Regras do Sistema

### Regras gerais do produto

- usuários podem criar conta e fazer login
    
- todo usuário do MVP é um **aluno**
    
- cada usuário possui um único perfil de aluno
    
- o usuário pode acessar o dashboard após autenticação
    
- o dashboard exibe as trilhas disponíveis
    
- no MVP, apenas a trilha **Engenharia de Prompt** estará disponível
    
- cada trilha é composta por módulos
    
- cada módulo é composto por lições
    
- cada lição pode conter:
    
    - explicação curta
        
    - exemplo de prompt
        
    - exercício
        
    - feedback
        
- o usuário pode avançar lição por lição
    
- o progresso do usuário deve ser salvo
    
- o usuário pode retomar de onde parou
    
- módulos futuros podem ser bloqueados até a conclusão do módulo anterior
    
- usuários do plano free visualizam anúncios ao final das lições
    
- usuários do plano premium não visualizam anúncios
    
- o usuário pode assinar o plano premium
    
- o sistema deve identificar se o usuário está em plano free ou premium
    
- o perfil do aluno deve exibir progresso, trilhas iniciadas e trilhas concluídas
    
- o sistema deve registrar conclusão de lições e módulos
    
- o sistema pode exibir botão ou destaque de **Seja Premium** no dashboard, conforme definido no MVP.
    

### Regras de aprendizado

- o usuário só pode concluir uma lição após interagir com o exercício
    
- o feedback da lição deve estar vinculado à resposta enviada pelo usuário
    
- cada lição concluída incrementa o progresso da trilha
    
- a conclusão de todas as lições de um módulo desbloqueia o próximo módulo
    
- a conclusão de todos os módulos conclui a trilha
    
- o sistema deve armazenar histórico mínimo de progresso por usuário
    

### Regras de assinatura

- apenas usuários autenticados podem assinar o premium
    
- uma assinatura ativa remove anúncios
    
- quando a assinatura expira ou é cancelada, o usuário volta ao plano free
    
- o status da assinatura deve ser refletido imediatamente no acesso ao conteúdo premium e na exibição de anúncios
    

---

## 14 — Permissões

## aluno

- criar conta
    
- fazer login
    
- editar o próprio perfil
    
- acessar dashboard
    
- visualizar trilhas disponíveis
    
- iniciar trilha
    
- acessar módulos liberados
    
- acessar lições liberadas
    
- responder exercícios
    
- receber feedback
    
- salvar progresso
    
- visualizar seu próprio progresso
    
- assinar plano premium
    
- visualizar status da própria assinatura
    

## admin

Mesmo que o MVP não precise expor painel admin agora, é bom prever essa camada para o Lovable não engessar a estrutura.

- criar trilhas
    
- editar trilhas
    
- criar módulos
    
- editar módulos
    
- criar lições
    
- editar lições
    
- definir ordem de módulos
    
- definir ordem de lições
    
- marcar conteúdo como publicado ou rascunho
    
- gerenciar anúncios
    
- gerenciar planos e benefícios
    
- visualizar dados gerais da plataforma
    

## sistema

Permissões automáticas do backend:

- calcular progresso do aluno
    
- liberar próximo módulo
    
- esconder anúncios para premium
    
- exibir anúncios para free
    
- validar acesso a conteúdo bloqueado
    
- atualizar status da assinatura a partir do gateway de pagamento
    

---

# Fase 7 — Integrações

## Integrações externas

### Supabase

- autenticação
    
- banco de dados
    
- storage, se necessário no futuro
    
- RLS
    
- funções server-side, se necessário
    

### Stripe

- checkout da assinatura premium
    
- confirmação de pagamento
    
- webhook para atualizar status da assinatura
    
- cancelamento e renovação da assinatura
    

### Provedor de anúncios

Como o MVP prevê anúncios no plano free, vale modelar isso desde já, mesmo que a implementação possa ser simples no início.

Opções possíveis:

- componente interno de banner gerenciado no próprio sistema
    
- integração futura com Google AdSense, caso seja web
    
- integração futura com AdMob, caso vire app mobile
    

### Serviço de e-mail

- confirmação de cadastro
    
- recuperação de senha
    
- notificações transacionais
    

Exemplos:

- Supabase Auth email
    
- Resend
    
- SendGrid
    

### OpenAI ou outro provedor de IA

Se o feedback das respostas for automatizado por IA.

Uso possível:

- analisar resposta do aluno
    
- comparar prompt enviado com critérios esperados
    
- gerar feedback textual
    
- sugerir melhoria do prompt
    

### Analytics

- acompanhar onboarding
    
- medir início e conclusão de trilhas
    
- medir abandono por lição
    
- medir conversão para premium
    

Exemplos:

- PostHog
    
- Google Analytics
    
- Mixpanel
    

---

# Fase 8 — Segurança

## 1. Autenticação

- autenticação obrigatória para acessar dashboard, perfil e progresso
    
- login por email e senha no MVP
    
- sessão protegida
    
- recuperação de senha
    
- validação de email, se desejado
    
- páginas públicas:
    
    - landing page
        
    - login
        
    - cadastro
        
- páginas protegidas:
    
    - dashboard
        
    - perfil
        
    - trilhas
        
    - módulos
        
    - lições
        
    - assinatura
        
    - progresso
        

## 2. RLS

No Supabase, a segurança precisa assumir que **ninguém pode confiar no frontend**.

### Regras essenciais de RLS

- usuário só pode visualizar o próprio perfil
    
- usuário só pode editar o próprio perfil
    
- usuário só pode visualizar o próprio progresso
    
- usuário só pode criar/editar registros de progresso vinculados ao próprio `user_id`
    
- usuário só pode visualizar a própria assinatura
    
- usuário não pode alterar manualmente seu plano para premium
    
- somente backend seguro ou webhook pode atualizar status de assinatura
    
- usuários comuns não podem criar, editar ou excluir trilhas, módulos e lições
    
- conteúdo administrativo só pode ser alterado por admin
    

### Exemplos de intenção de segurança

- usuário só pode editar seu próprio perfil
    
- usuário só pode acessar seu próprio histórico
    
- usuário não pode ver progresso de outros usuários
    
- usuário free não pode acessar conteúdo que futuramente seja restrito ao premium
    
- aluno não pode publicar ou editar conteúdo pedagógico
    

## 3. Validação

### Validação de entrada

- validar email no cadastro
    
- validar senha com regra mínima
    
- validar campos obrigatórios do perfil
    
- validar resposta do exercício antes de salvar
    
- validar ids de trilha, módulo e lição no backend
    
- validar se a lição pertence ao módulo correto
    
- validar se o módulo pertence à trilha correta
    
- validar se o usuário tem acesso ao módulo solicitado
    
- validar assinatura antes de liberar benefícios premium
    

### Validação de negócio

- não permitir marcar lição inexistente como concluída
    
- não permitir concluir módulo sem concluir lições necessárias
    
- não permitir ativar premium sem pagamento aprovado
    
- não permitir editar progresso de outro usuário
    
- não permitir acesso direto por URL a áreas protegidas sem autenticação
    

### Validação de backend

- toda lógica crítica deve ser verificada no backend
    
- frontend serve para experiência, não para segurança
    
- webhook de pagamento deve validar origem e assinatura do provedor
    
- mudanças de plano devem ocorrer via evento confiável do gateway
    

---

# Estrutura resumida para o Lovable

## Regras do Sistema

- usuários autenticam por login e cadastro
    
- cada usuário possui perfil de aluno
    
- o usuário acessa trilhas de aprendizado
    
- o MVP possui uma trilha inicial: Engenharia de Prompt
    
- trilhas possuem módulos
    
- módulos possuem lições
    
- lições possuem conteúdo, exercício e feedback
    
- progresso é salvo por usuário
    
- free vê anúncios
    
- premium não vê anúncios
    
- usuário pode assinar premium
    

## Permissões

### aluno

- editar próprio perfil
    
- iniciar trilha
    
- acessar módulos liberados
    
- responder exercícios
    
- salvar progresso
    
- assinar premium
    

### admin

- criar e editar trilhas, módulos e lições
    
- gerenciar conteúdo
    
- gerenciar planos
    

## Integrações

- Supabase
    
- Stripe
    
- provedor de anúncios
    
- e-mail transacional
    
- provedor de IA
    
- analytics
    

## Segurança

- autenticação por email e senha
    
- RLS em todas as tabelas sensíveis
    
- usuário acessa apenas seus próprios dados
    
- assinatura só atualizada por backend/webhook
    
- validação de entrada e de regras de negócio no backend
    

---

# Recomendação importante

Antes de mandar para o Lovable, o próximo passo ideal é eu te entregar a **estrutura das entidades do banco**:

- users
    
- profiles
    
- tracks
    
- modules
    
- lessons
    
- lesson_attempts
    
- user_progress
    
- subscriptions
    

Porque aí o Lovable deixa de trabalhar no abstrato e passa a construir em cima de um esqueleto real.

Posso fazer isso agora em formato de **modelagem de banco + relações + campos principais**.