O backend deverá fazer parte de um monolito moderno, ou seja, o backend e o frontend rodando em um mesmo servidor node. Ele deve ser feito utilizando node.js e, caso necessário, faça o uso de algum framework.

 O módulo de enterprises, bem como agent e user enterprises não serão implementados, de modo em que a sua presença no banco de dados se justifique pela arquitetura futura.

 Você poderá adicionar colunas e tabelas conforme necessário, desde que as regras e nem a proposta do projeto seja afetada, apenas com o objetivo de refatoração.

Regras de negócio: 

	Teremos 3 planos:
		Freemium: 
			Limites de upload: 2 
			Análise, Validador e Gerador da IA.
		Standart:
			O que temos no freemium
			Audiência sintética
			Limite de upload: 5
		Pro: 
			O que temos no standart
			Uploads ilimitados


Comando SQL da base do banco de dados:

CREATE TABLE "user"(
    "id" UUID NOT NULL,
    "name" VARCHAR(255) NOT NULL,
    "email" VARCHAR(255) NOT NULL,
    "password_hash" VARCHAR(255) NOT NULL,
    "plan_id" BIGINT NOT NULL
);
ALTER TABLE
    "user" ADD PRIMARY KEY("id");
CREATE TABLE "user_uploads"(
    "id" UUID NOT NULL,
    "user_id" UUID NOT NULL,
    "content" TEXT NOT NULL,
    "created_at" DATE NOT NULL
);
ALTER TABLE
    "user_uploads" ADD PRIMARY KEY("id");
CREATE TABLE "plan"(
    "id" BIGINT NOT NULL,
    "uploads_limit" BIGINT NOT NULL,
    "name" VARCHAR(255) NOT NULL,
    "price" DECIMAL(8, 2) NOT NULL,
    "recurrence" VARCHAR(255) CHECK
        ("recurrence" IN('')) NOT NULL
);
ALTER TABLE
    "plan" ADD PRIMARY KEY("id");
CREATE TABLE "user_request"(
    "id" UUID NOT NULL,
    "user_id" UUID NOT NULL,
    "content" TEXT NOT NULL,
    "created_at" DATE NOT NULL,
    "updated_at" DATE NOT NULL
);
ALTER TABLE
    "user_request" ADD PRIMARY KEY("id");
CREATE TABLE "agent"(
    "id" UUID NOT NULL,
    "agent_type" VARCHAR(255) CHECK
        ("agent_type" IN('')) NOT NULL,
        "agent_name" VARCHAR(255) NOT NULL
);
ALTER TABLE
    "agent" ADD PRIMARY KEY("id");
CREATE TABLE "agent_response"(
    "id" BIGINT NOT NULL,
    "agent_id" UUID NOT NULL,
    "user_request" UUID NOT NULL,
    "content" TEXT NOT NULL
);
ALTER TABLE
    "agent_response" ADD PRIMARY KEY("id");
CREATE TABLE "enterprises"(
    "id" UUID NOT NULL,
    "name" VARCHAR(255) NOT NULL,
    "adress" VARCHAR(255) NOT NULL,
    "cnpj" BIGINT NOT NULL
);
ALTER TABLE
    "enterprises" ADD PRIMARY KEY("id");
CREATE TABLE "user_enterprise"(
    "id" UUID NOT NULL,
    "user_id" UUID NOT NULL,
    "enterprise_id" UUID NOT NULL
);
ALTER TABLE
    "user_enterprise" ADD PRIMARY KEY("id");
CREATE TABLE "agent_enterprise"(
    "id" BIGINT NOT NULL,
    "context" TEXT NOT NULL,
    "agent_id" UUID NOT NULL,
    "enterprise_id" UUID NOT NULL
);
ALTER TABLE
    "agent_enterprise" ADD PRIMARY KEY("id");
CREATE TABLE "agent_uploads"(
    "id" UUID NOT NULL,
    "agent_id" UUID NOT NULL,
    "user_id" UUID NOT NULL,
    "content" TEXT NOT NULL,
    "created_at" DATE NOT NULL
);
ALTER TABLE
    "agent_uploads" ADD PRIMARY KEY("id");
ALTER TABLE
    "agent_uploads" ADD CONSTRAINT "agent_uploads_user_id_foreign" FOREIGN KEY("user_id") REFERENCES "user"("id");
ALTER TABLE
    "user_enterprise" ADD CONSTRAINT "user_enterprise_user_id_foreign" FOREIGN KEY("user_id") REFERENCES "user"("id");
ALTER TABLE
    "agent_enterprise" ADD CONSTRAINT "agent_enterprise_enterprise_id_foreign" FOREIGN KEY("enterprise_id") REFERENCES "enterprises"("id");
ALTER TABLE
    "agent" ADD CONSTRAINT "agent_agent_type_foreign" FOREIGN KEY("agent_type") REFERENCES "agent_response"("agent_id");
ALTER TABLE
    "plan" ADD CONSTRAINT "plan_price_foreign" FOREIGN KEY("price") REFERENCES "user"("plan_id");
ALTER TABLE
    "agent_enterprise" ADD CONSTRAINT "agent_enterprise_agent_id_foreign" FOREIGN KEY("agent_id") REFERENCES "agent"("id");
ALTER TABLE
    "agent_response" ADD CONSTRAINT "agent_response_user_request_foreign" FOREIGN KEY("user_request") REFERENCES "user_request"("user_id");
ALTER TABLE
    "user" ADD CONSTRAINT "user_id_foreign" FOREIGN KEY("id") REFERENCES "user_uploads"("user_id");
ALTER TABLE
    "agent_uploads" ADD CONSTRAINT "agent_uploads_agent_id_foreign" FOREIGN KEY("agent_id") REFERENCES "agent"("id");
ALTER TABLE
    "user" ADD CONSTRAINT "user_id_foreign" FOREIGN KEY("id") REFERENCES "user_request"("user_id");
ALTER TABLE
    "user_enterprise" ADD CONSTRAINT "user_enterprise_enterprise_id_foreign" FOREIGN KEY("enterprise_id") REFERENCES "enterprises"("id");

Exemplo de fluxo:

Usuário faz cadastro e fica com o plano freemium automaticamente;
No input do chat, usuário pode fazer upload onde a IA transceve o conteudo e coloca como content na tabela user_uploads, associando ao user_id.
Em paralelo a isso, criada tabela user_request, associando o user_id e colocando content. 
Quando o agente gera a resposta, é inserido na tabela agent_response, associando tabelas e com o content. 
Se o agente gerou documento, a transcrição desse documento irá para o agent_uploads