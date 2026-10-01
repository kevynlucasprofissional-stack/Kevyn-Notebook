Para suportar o fluxo de autenticação, gestão de planos, registros de requisições de análise (CoT), armazenamento de contextos de agentes, arquivos e a estrutura de empresas, estas são as entidades fundamentais:

```text
User            # Usuário do sistema
Plan            # Planos de assinatura (Freemium, Standard, Pro, Enterprise)
UserUpload      # Arquivos brutos enviados pelo usuário
UserRequest     # Histórico de interações (prompts) do usuário
Agent           # Catálogo dos agentes (Ex: Analista Sociocomportamental, Estrategista)
AgentResponse   # Resposta estruturada/analítica de cada agente
AgentUpload     # Documentos/relatórios finais gerados pela IA
Enterprise      # Dados cadastrais de empresas (para planos Enterprise)
UserEnterprise  # Relacionamento entre usuários e empresas
AgentEnterprise # Contexto personalizado de agentes por empresa
```

---

### Notas de Refinamento para Implementação (SQL):

*   **User:** Deve conter uma chave estrangeira para `Plan`.
*   **UserRequest:** Será a "espinha dorsal" do fluxo. O ID desta entidade será a chave para conectar `AgentResponse` e `AgentUpload`.
*   **AgentResponse:** Esta entidade é o **coração da análise**. Ela deve armazenar o output em JSON dos sub-agentes, permitindo que o `Sintetizador-Chefe` consuma esse histórico para montar o Report Executivo final.
*   **Gestão de Limites:** Como o plano `Freemium` limita uploads a 2 e o `Standard` a 5, o backend deve validar essa contagem na entidade `UserUpload` antes de permitir novas inserções, usando o `uploads_limit` vindo da entidade `Plan`.