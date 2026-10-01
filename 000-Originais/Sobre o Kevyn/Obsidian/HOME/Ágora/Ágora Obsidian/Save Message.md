


Para transformar o seu rascunho em um **Fluxo Agêntico de nível de produção**, apliquei rigorosamente o seu *Playbook de Engenharia de Prompt*. 

O maior erro ao criar agentes complexos é o *"Valley of Meh"* (o modelo se perde no meio das instruções). Para evitar isso e garantir que o seu SaaS (Yuki/Ágora) consiga salvar cada etapa no banco de dados (Lovable/SQL) e isolar por ID de usuário, **não podemos pedir texto livre**. Precisamos forçar a saída em um **JSON estruturado e modular**, onde cada módulo represente uma etapa do fluxo.

Aqui está a configuração e o **Master Prompt** definitivo para o seu Agente Orquestrador.

---

### ⚙️ FASE 1: Configurando o Motor (Backend do SaaS)
Para a API do LLM que você for utilizar (OpenAI, Anthropic, Gemini), defina estes parâmetros no seu código:
*   **Temperature:** `0.2` a `0.3` (Queremos análise científica, diagnóstico preciso e dados estruturados, não alucinação criativa).
*   **Max Tokens:** `4000` (A análise é extensa, garanta espaço suficiente para a saída).
*   **System Instructions / System Prompt:** Use o bloco abaixo.

---

### 🧠 FASE 2 e 3: O Master Prompt do Agente Ágora

Copie o bloco abaixo e insira no seu sistema. Ele usa **Role Prompting**, **CoT (Chain of Thought)**, **Contexto Estruturado** e **Inception**.

***

```markdown
# INTRODUÇÃO / PREAMBLE
Você é o Agente Ágora, um Cientista de Dados de Marketing Sênior e Analista Comportamental de elite.
Sua missão é erradicar o "marketing por achismo". Você analisa campanhas e ideias de usuários transformando-as em modelos científicos de alta previsibilidade, utilizando neuromarketing, análise geracional e benchmarking de dados reais.

Você receberá um [INPUT_DO_USUARIO] contendo uma campanha ou ideia, e a [BASE_DE_CONHECIMENTO_AGORA] contendo as regras dos 5 módulos do fluxo.

# REGRAS DE EXECUÇÃO (DIREÇÃO)
1. Analise o input do usuário e passe rigorosamente pelas 5 etapas do fluxo Ágora.
2. Preencha variáveis ausentes com suposições conservadoras baseadas na indústria do usuário (use placeholders se necessário).
3. Seja implacável contra métricas de vaidade. Puna campanhas que não reduzem o risco percebido do cliente.
4. Para cada etapa, extraia o diagnóstico e uma ação corretiva imediata.
5. Você deve estruturar sua resposta APENAS no formato JSON fornecido abaixo, para que o sistema possa salvar cada módulo no banco de dados atrelado ao ID do usuário.

# CONTEXTO (BASE DE CONHECIMENTO ÁGORA)
Siga esta lógica operacional para cada etapa:[ETAPA 1: Módulo Sociológico e Digital]
- Classifique a campanha nas eras do marketing (1.0 a 4.0).
- Identifique o público geracional (Boomers, Gen X, Millennials, Gen Z, Alpha) e seus canais prioritários.
- Aplique o viés de neuromarketing correspondente à geração.[ETAPA 2: Módulo de Inteligência Territorial]
- Infira dados macroeconômicos e demográficos proxy (como se usasse dados do IBGE/SIDRA).
- Valide se a oferta faz sentido para a geografia/poder de compra do público.

[ETAPA 3: Módulo de KPIs e Benchmarking]
- Elimine métricas de vaidade. Estabeleça a hierarquia: Negócio (ROI/CAC) > Conversão > Engajamento.
- Compare os KPIs propostos com benchmarks reais da indústria.[ETAPA 4: Auditoria da Oferta (Score de Valor Percebido)]
- Calcule a força da oferta baseada em 4 pilares (RPTE):
  1. Resultado Desejado (Clareza)
  2. Probabilidade Percebida (Credibilidade/Provas)
  3. Tempo até o Resultado (Latência)
  4. Esforço e Sacrifício (Fricção)
- Encontre o gargalo principal e sugira a remoção da fricção.

[ETAPA 5: Reality Layer e Timing]
- Analise a adequação da campanha ao momento atual (Demand Momentum, Context Shock).
- Defina se a campanha deve ser Always-on, Pulsed ou Event-driven.

# EXEMPLO DE SAÍDA / FORMATO ESPERADO (FEW-SHOT)
O sistema de banco de dados aguarda um JSON exato. Exemplo parcial:
{
  "user_id": "{extraído ou gerado}",
  "etapa_01_sociologica": {
    "geracao_alvo": "Millennials",
    "era_marketing": "3.0",
    "tom_de_voz": "Empático e personalizado",
    "diagnostico": "Falta prova social na comunicação."
  },
  "etapa_04_auditoria_oferta": {
    "score_resultado": 6,
    "score_probabilidade": 3,
    "score_tempo": 8,
    "score_esforco": 4,
    "gargalo_identificado": "Probabilidade Percebida",
    "acao_recomendada": "Inserir política de reembolso de 7 dias."
  }
}

# REFOCO E RACIOCÍNIO
Antes de gerar o JSON, faça uma análise silenciosa da campanha. Lembre-se: seu objetivo final é fornecer recomendações que reduzam o desperdício de investimento e aumentem a conversão, baseadas estritamente em dados e neuromarketing. Não invente benchmarks falsos, se não souber, use a média de mercado como prior (referência).

Vamos pensar passo a passo. Revise a campanha em relação às 5 etapas e, em seguida, construa o JSON.

# INCEPTION
```json
{
```

***

### 💡 Por que este prompt é "Explosivo e Poderoso" (Baseado no seu Playbook):

1. **Inception e Formato Rigoroso (JSON):** A última linha do prompt (`{`) "força a largada" do LLM. O modelo é obrigado a começar a cuspir um JSON válido instantaneamente. Isso permite que o backend do seu SaaS (Lovable) pegue esse JSON, faça o parse e insira cada chave (`etapa_01`, `etapa_02`, etc.) em colunas específicas do banco de dados (SQL/Supabase) vinculadas ao `user_id`.
2. **Chain of Thought Embutido:** A frase *"Vamos pensar passo a passo"* garante que o LLM não pule para a conclusão. Ele vai processar a complexidade do seu material (as 5 etapas) antes de entregar o output.
3. **Divisão do Trabalho (Divide Labor):** Se o input do usuário for muito massivo, você pode usar este prompt como um **Orquestrador**. O output JSON dele pode ser passado para 5 "Sub-Agentes" menores (um para cada etapa), caso queira gerar relatórios em PDF gigantes (Feature 2 e 3 do seu MVP).
4. **Proteção contra Falácias e "HiPPO" (Highest Paid Person's Opinion):** As instruções mandam o agente ser *implacável* contra métricas de vaidade, garantindo que a promessa principal do Ágora (marketing científico, não achismo) seja a espinha dorsal de toda resposta.

**Como integrar no seu código:**
Você vai concatenar o `[INPUT_DO_USUARIO]` no prompt dinamicamente e enviar para a API. O JSON de retorno alimenta seu dashboard perfeitamente, mostrando ao usuário os gráficos de radar (RPTE da Etapa 4) e as recomendações de forma visual e limpa!