## 1. Autenticação (Identity Management)
A autenticação será gerida pelo módulo de *Auth* do Supabase, utilizando JWTs para sessão.

*   **Provedores:** Email/Senha (padrão) e OAuth Social (Google/Facebook) para reduzir o atrito no *onboarding*.
*   **Regra de Registro:** No momento da criação do usuário (`auth.users`), um gatilho (*trigger*) deve criar automaticamente o registro correspondente na tabela pública `user`, associando o `plan_id` inicial ao **Plano Freemium**.
*   **Gestão de Sessão:** Sessões persistentes com *Refresh Tokens* configurados para expiração padrão de segurança (ex: 24h a 7 dias, dependendo da criticidade).

---

## 2. RLS (Row Level Security - Políticas de Acesso)

As políticas de RLS abaixo devem ser aplicadas em todas as tabelas para garantir que um usuário **jamais** visualize, edite ou delete dados de terceiros.

### Políticas de Acesso (Pseudocódigo SQL)

*   **Tabela `user` (Perfil):**
    *   `SELECT / UPDATE`: "usuário só pode ler e editar seu próprio registro (onde `id = auth.uid()`)."
*   **Tabela `user_request` e `user_uploads` (Dados de Análise):**
    *   `SELECT / INSERT / DELETE`: "usuário só pode acessar requisições e uploads onde `user_id = auth.uid()`."
*   **Tabela `agent_response` e `agent_uploads` (Saída da IA):**
    *   `SELECT`: "usuário só pode ler a resposta do agente se ela estiver vinculada a uma requisição (`user_request`) de sua propriedade."
    *   `INSERT/UPDATE`: Bloqueado para o usuário (apenas o serviço de backend/agente tem permissão).
*   **Tabela `plan` e `agent`:**
    *   `SELECT`: Público para usuários autenticados (necessário para o sistema carregar o catálogo de planos e agentes).
    *   `INSERT / UPDATE / DELETE`: Bloqueado (apenas `service_role`).

---

## 3. Validação e Segurança de Backend

Para além do RLS, a camada de lógica (Edge Functions/Node.js) deve garantir a integridade do sistema:

### A. Validação de Limites (Business Logic)
*   **Regra de Upload:** Antes de realizar um `INSERT` na tabela `user_uploads`, o backend **deve** validar:
    1.  Quantos uploads aquele usuário já realizou hoje.
    2.  Qual é o `uploads_limit` do plano dele.
    3.  *Erro:* Se `uploads_atuais >= uploads_limit`, retornar `403 Forbidden` com a mensagem: "Limite de uploads atingido para o plano [Nome do Plano]".

### B. Sanitização de Input (Prevenção de Injeção)
*   **Prompts de Usuário:** O `content` da `user_request` deve ser sanitizado para evitar que o usuário tente "jailbreakar" os prompts do sistema (ex: tentar forçar a IA a ignorar as diretrizes de segurança).
*   **Arquivos:** Todos os arquivos de upload devem ser validados pelo *Storage* do Supabase por tipo MIME (apenas PDF, DOCX, TXT) e tamanho máximo antes de chegar ao parser de IA.

### C. Acesso Enterprise (Segregação Customizada)
*   **API Meta (Plano Enterprise):** As credenciais (tokens) das APIs de terceiros não devem ser armazenadas no frontend. O backend deve utilizar um mecanismo de criptografia (como `pgcrypto` no Postgres) para armazenar tokens de clientes na tabela `enterprise` (ou uma tabela de `secrets`), nunca em texto plano.

### D. Níveis de Acesso (RBAC Simples)
*   **Usuário Comum:** Acesso restrito a suas próprias tabelas.
*   **Agente (System Role):** Possui permissão de `INSERT` na `agent_response` através de uma chave de serviço (`service_role`) que ignora o RLS, garantindo que o agente escreva no banco sem ser bloqueado pela política do usuário.

---

### Resumo da Segregação de Dados

| Entidade | Quem pode LER | Quem pode ESCREVER |
| :--- | :--- | :--- |
| **Perfil Usuário** | Apenas o próprio dono | Apenas o próprio dono |
| **Requisições/Prompts** | Apenas o próprio dono | Apenas o próprio dono |
| **Respostas do Agente** | Apenas o próprio dono | Apenas o Sistema (Agente) |
| **Planos/Catálogo** | Todos (Autenticados) | Apenas Admin |
| **Integração Meta (Ent)** | Apenas Administrador da Conta | Apenas Administrador da Conta |

---
**Nota de implementação para o Lovable:** Ao implementar o banco, certifique-se de executar `ALTER TABLE ... ENABLE ROW LEVEL SECURITY;` em todas as tabelas listadas acima. Sem isso, o banco é apenas um depósito de dados sem proteção.