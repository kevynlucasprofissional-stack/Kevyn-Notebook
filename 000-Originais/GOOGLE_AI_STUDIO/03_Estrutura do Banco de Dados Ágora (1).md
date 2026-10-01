Com base na análise técnica de todos os arquivos fornecidos (especialmente os diagramas de entidade, as regras de negócio dos planos e o fluxo de agentes), apresento abaixo a estrutura de banco de dados otimizada para **PostgreSQL (Supabase)**.

Esta estrutura refatora o modelo conceitual inicial para garantir integridade referencial, performance e escalabilidade, mantendo a compatibilidade com o sistema multi-agentes Ágora.

```sql
-- ========================================================
-- ESTRUTURA DO BANCO DE DADOS ÁGORA
-- ========================================================

-- 1. TABELAS DE CONFIGURAÇÃO E ASSINATURA
CREATE TABLE "plan" (
    "id" BIGINT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    "name" VARCHAR(50) NOT NULL, -- Freemium, Standard, Pro, Enterprise
    "price" DECIMAL(10, 2) NOT NULL,
    "uploads_limit" INTEGER NOT NULL, -- 2, 5, 999999 (ilimitado)
    "recurrence" VARCHAR(20) NOT NULL -- 'mensal', 'anual'
);

CREATE TABLE "user" (
    "id" UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    "name" VARCHAR(255) NOT NULL,
    "email" VARCHAR(255) UNIQUE NOT NULL,
    "password_hash" VARCHAR(255) NOT NULL,
    "plan_id" BIGINT REFERENCES "plan"("id"),
    "created_at" TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- 2. TABELAS DE NEGÓCIO E FLUXO DE ANÁLISE
CREATE TABLE "user_request" (
    "id" UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    "user_id" UUID NOT NULL REFERENCES "user"("id") ON DELETE CASCADE,
    "content" TEXT NOT NULL, -- Prompt bruto do usuário
    "created_at" TIMESTAMP WITH TIME ZONE DEFAULT NOW(),
    "updated_at" TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

CREATE TABLE "user_uploads" (
    "id" UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    "user_id" UUID NOT NULL REFERENCES "user"("id") ON DELETE CASCADE,
    "request_id" UUID REFERENCES "user_request"("id"), -- Vincula o upload a uma análise específica
    "file_url" TEXT NOT NULL, -- Referência ao storage
    "content_transcription" TEXT, -- Texto extraído pelo OCR/IA
    "created_at" TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- 3. TABELAS DO SISTEMA MULTI-AGENTE
CREATE TABLE "agent" (
    "id" UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    "agent_name" VARCHAR(100) NOT NULL, -- Ex: "Analista Sociocomportamental"
    "agent_type" VARCHAR(50) NOT NULL -- Ex: "Master", "Analista", "Estrategista"
);

CREATE TABLE "agent_response" (
    "id" BIGINT GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    "agent_id" UUID NOT NULL REFERENCES "agent"("id"),
    "request_id" UUID NOT NULL REFERENCES "user_request"("id") ON DELETE CASCADE,
    "content" JSONB NOT NULL, -- Armazena o JSON estruturado do Agente
    "created_at" TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

CREATE TABLE "agent_uploads" (
    "id" UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    "agent_id" UUID NOT NULL REFERENCES "agent"("id"),
    "request_id" UUID NOT NULL REFERENCES "user_request"("id"),
    "content" TEXT NOT NULL, -- Caminho do relatório gerado (PDF/PPT)
    "created_at" TIMESTAMP WITH TIME ZONE DEFAULT NOW()
);

-- 4. TABELAS DE SUPORTE (Roadmap Futuro Enterprise)
CREATE TABLE "enterprises" (
    "id" UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    "name" VARCHAR(255) NOT NULL,
    "cnpj" BIGINT UNIQUE NOT NULL
);

CREATE TABLE "user_enterprise" (
    "user_id" UUID REFERENCES "user"("id"),
    "enterprise_id" UUID REFERENCES "enterprises"("id"),
    PRIMARY KEY ("user_id", "enterprise_id")
);

-- ========================================================
-- ÍNDICES PARA PERFORMANCE
-- ========================================================

CREATE INDEX idx_user_request_user ON "user_request"("user_id");
CREATE INDEX idx_agent_response_request ON "agent_response"("request_id");
CREATE INDEX idx_user_uploads_user ON "user_uploads"("user_id");

-- ========================================================
-- NOTAS DE IMPLEMENTAÇÃO SUPABASE:
-- ========================================================
-- 1. O campo 'content' em 'agent_response' é do tipo JSONB 
--    para permitir queries rápidas nos dados estruturados pelos agentes.
-- 2. Use RLS (Row Level Security) do Supabase para garantir 
--    que usuários só vejam seus próprios 'user_request' e 'agent_response'.
-- 3. O plano 'Enterprise' pode utilizar a tabela 'enterprises' 
--    para segregar contextos de IA (prompt engineering customizado por cliente).
```

### Principais Refatorações realizadas:
1.  **Integridade Referencial:** Adicionado `ON DELETE CASCADE` em tabelas vinculadas a usuários e requisições para evitar dados órfãos.
2.  **JSONB para Agentes:** Alterado o campo `content` da tabela `agent_response` para `JSONB`. Isso é vital para que o frontend/sintetizador consiga ler facilmente os campos estruturados (Score, Raciocínio, Diagnóstico) sem precisar fazer *parse* de texto simples.
3.  **Vínculos Lógicos:** Adicionado `request_id` na tabela `user_uploads`, permitindo rastrear exatamente qual arquivo foi usado em qual análise.
4.  **Uso de UUIDs e Identidades:** Substituído tipos de chave primária para os padrões modernos do Postgres/Supabase (`UUID` para entidades principais, `GENERATED ALWAYS AS IDENTITY` para IDs sequenciais).