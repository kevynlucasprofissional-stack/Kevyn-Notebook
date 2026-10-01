## Visão Geral

O banco modela um sistema onde:

- **Usuários** fazem **requisições**
    
- **Agentes de IA** respondem essas requisições
    
- **Uploads** podem ser feitos por usuários ou agentes
    
- **Empresas** podem ter usuários e agentes associados
    
- **Planos** controlam limites de uso
    

---

# Tabelas

---

# `user`

Tabela principal de usuários da plataforma.

```markdown
Tabela: user

Campos
- id (uuid) PK
- name (varchar)
- email (varchar)
- password_hash (varchar)
- plan_id (bigint) FK → plan.id
```

### Relações

```
user.plan_id → plan.id
```

---

# `plan`

Define os planos da plataforma.

```markdown
Tabela: plan

Campos
- id (bigint) PK
- uploads_limit (bigint)
- name (varchar)
- price (decimal)
- recurrence (enum)
```

---

# `user_uploads`

Arquivos ou conteúdos enviados pelo usuário.

```markdown
Tabela: user_uploads

Campos
- id (uuid) PK
- user_id (uuid) FK → user.id
- content (text)
- created_at (date)
```

### Relações

```
user_uploads.user_id → user.id
```

---

# `user_request`

Requisições feitas pelo usuário para o sistema / agentes.

```markdown
Tabela: user_request

Campos
- id (uuid) PK
- user_id (uuid) FK → user.id
- content (text)
- created_at (date)
- updated_at (date)
```

### Relações

```
user_request.user_id → user.id
```

---

# `agent`

Define os agentes do sistema.

```markdown
Tabela: agent

Campos
- id (uuid) PK
- agent_type (enum)
- agent_name (varchar)
```

---

# `agent_response`

Respostas geradas pelos agentes para uma requisição do usuário.

```markdown
Tabela: agent_response

Campos
- id (bigint) PK
- agent_id (uuid) FK → agent.id
- user_request (uuid) FK → user_request.id
- content (text)
```

### Relações

```
agent_response.agent_id → agent.id
agent_response.user_request → user_request.id
```

---

# `agent_uploads`

Uploads gerados por agentes.

```markdown
Tabela: agent_uploads

Campos
- id (uuid) PK
- agent_id (uuid) FK → agent.id
- user_id (uuid) FK → user.id
- content (text)
- created_at (date)
```

### Relações

```
agent_uploads.agent_id → agent.id
agent_uploads.user_id → user.id
```

---

# `enterprises`

Empresas cadastradas no sistema.

```markdown
Tabela: enterprises

Campos
- id (uuid) PK
- name (varchar)
- adress (varchar)
- cnpj (bigint)
```

---

# `user_enterprise`

Relaciona usuários com empresas.

```markdown
Tabela: user_enterprise

Campos
- id (uuid) PK
- user_id (uuid) FK → user.id
- enterprise_id (uuid) FK → enterprises.id
```

### Relações

```
user_enterprise.user_id → user.id
user_enterprise.enterprise_id → enterprises.id
```

---

# `agent_enterprise`

Relaciona agentes com empresas e define o contexto utilizado.

```markdown
Tabela: agent_enterprise

Campos
- id (bigint) PK
- context (text)
- agent_id (uuid) FK → agent.id
- enterprise_id (uuid) FK → enterprises.id
```

### Relações

```
agent_enterprise.agent_id → agent.id
agent_enterprise.enterprise_id → enterprises.id
```

---

# Fluxo de Dados (Resumo)

```markdown
User
 ├─ cria → user_request
 │
 ├─ envia → user_uploads
 │
 └─ pertence → enterprise (via user_enterprise)

Agent
 ├─ responde → agent_response
 ├─ gera → agent_uploads
 └─ pertence → enterprise (via agent_enterprise)

Enterprise
 ├─ possui → users
 └─ possui → agents

Plan
 └─ define limites do user
```

---

# Estrutura Conceitual do Sistema

```
User
 ├─ Uploads
 ├─ Requests
 └─ Enterprise

Agent
 ├─ Responses
 ├─ Uploads
 └─ Enterprise

Enterprise
 ├─ Users
 └─ Agents

Plan
 └─ limita usuários
```