Com base na arquitetura Ágora, nas funcionalidades mapeadas e nas necessidades de negócio extraídas dos anexos, apresento os **Fluxos Críticos** que garantem a conversão, a retenção e a qualidade da entrega do sistema.

---

### 1. Fluxo de Onboarding (Aquisição e Conversão)
O objetivo aqui é reduzir o atrito entre o interesse inicial e a primeira experiência de valor (a "entrega" do agente Ágora).

1.  **Landing Page:** O usuário chega pela LP (com prova social e descrição do valor).
2.  **Entrada:** Usuário clica em "Começar Agora" (Direto para Chat) ou em um plano (Direto para Cadastro).
3.  **Coleta de Dados:** Caso o usuário não tenha conta, ele é direcionado ao fluxo de cadastro (simples: nome, email, senha).
4.  **Atribuição:** O sistema atribui automaticamente o **Plano Freemium** no banco de dados (`user.plan_id` -> `plan.id` [Freemium]).
5.  **Setup do Usuário:** O sistema cria um `user_request` vazio para iniciar o contexto da conversa.
6.  **Primeiro Prompt:** O Agente Orquestrador Master saúda o usuário, explica brevemente o Ágora e solicita a descrição da campanha (Intake).
7.  **Estado Concluído:** Usuário interage com o agente, sentindo o valor antes de ser forçado a um "paywall" (estratégia *product-led*).

---

### 2. Fluxo de Contratação (Upgrade de Plano)
Este fluxo ocorre quando o usuário atinge os limites do seu plano atual (ex: 2 uploads no Freemium) ou deseja recursos exclusivos (Audiência Sintética/Enterprise).

1.  **Trigger de Limite:** Ao tentar realizar o 3º upload (no Freemium), o backend bloqueia a ação e dispara um modal de "Upgrade Necessário".
2.  **Exibição de Planos:** O sistema apresenta a tabela comparativa (Freemium vs. Standard vs. Pro vs. Enterprise), destacando os benefícios do próximo nível.
3.  **Seleção:** Usuário escolhe o plano (ex: Standard).
4.  **Checkout:** Integração com gateway de pagamento (simulado/Stripe).
5.  **Provisionamento:** Após confirmação do pagamento pelo gateway:
    *   O `plan_id` do usuário na tabela `user` é atualizado.
    *   O `uploads_limit` é incrementado instantaneamente.
    *   O sistema libera as funcionalidades bloqueadas (ex: acesso aos insights de audiência sintética).
6.  **Confirmação:** Agente Ágora parabeniza o usuário pela nova categoria de recursos.

---

### 3. Fluxo de Pagamento (Ciclos Recorrentes)
*Nota: Como o Ágora utiliza um modelo SaaS, este fluxo gerencia a sustentabilidade financeira.*

1.  **Monitoramento:** O sistema (via Webhook do Gateway) verifica a data de renovação.
2.  **Processamento:** Renovação automática ou envio de lembrete de cobrança (se anual ou mensal).
3.  **Sucesso:** O status do plano é mantido ou renovado na tabela `plan` e `user`.
4.  **Falha (Inadimplência):**
    *   O sistema envia notificação via e-mail.
    *   Após *grace period* (ex: 7 dias), o sistema rebaixa o usuário para o **Plano Freemium** automaticamente.
    *   O acesso a recursos *Pro/Enterprise* (como APIs da Meta) é suspenso.

---

### 4. Fluxo de Avaliação (Feedback Loop e Qualidade)
Este é o fluxo que retroalimenta a IA para garantir que os resultados (Score/Campanha Otimizada) estejam realmente alinhados às expectativas dos especialistas.

1.  **Trigger de Entrega:** O Agente Sintetizador entrega o Report Executivo e a Campanha Otimizada.
2.  **Interface de Feedback:** Abaixo do relatório, aparecem os botões de **Like (👍)** e **Deslike (👎)**.
3.  **Ação de Feedback:**
    *   Se **Like**: O sistema registra a satisfação e o agente solicita um breve depoimento (para prova social na LP).
    *   Se **Deslike**: O sistema abre um formulário de *feedback* rápido ("O que faltou?", "Score não condiz?", "Sugestão errada?").
4.  **Armazenamento:** O feedback é vinculado à `agent_response` específica.
5.  **Aprendizado:**
    *   Se o feedback negativo for alto para um determinado agente, o sistema sinaliza a necessidade de "reajuste de prompt" para aquele Sub-Agente específico no `Master Agent`.
    *   Os dados são estruturados para permitir que, em versões futuras, a IA entenda melhor as nuances que o usuário marcou como "erradas".

---

### Resumo para Implementação:
| Fluxo           | Trigger (Disparador)   | Ação Principal         | Impacto no DB        |
| :-------------- | :--------------------- | :--------------------- | :------------------- |
| **Onboarding**  | Acesso à Landing       | Criação de conta/chat  | `User` + `Plan`      |
| **Contratação** | Limite de uso atingido | Upgrade de plano       | `User.plan_id`       |
| **Pagamento**   | Ciclo Mensal/Anual     | Cobrança               | `Plan` status        |
| **Avaliação**   | Entrega do Relatório   | Coleta de Like/Deslike | `AgentResponse` meta |