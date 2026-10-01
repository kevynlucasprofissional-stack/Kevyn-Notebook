<ao_abrir>
Animação fluida do logo **Ágora** (estética Marketing 4.0, tecnológica e limpa). Transição via fade para a `<tela_0>`.
</ao_abrir>

<tela_0>
**Tela de Boas-Vindas e Login/Cadastro.**
- Seção Superior: Proposta de valor "O Marketing que Prevê o Futuro".
- Formulário: Campos de E-mail e Senha. Botão de "Entrar" e "Criar Conta".
- Social Login: Botões para Google e Facebook.
- Ao autenticar, o sistema verifica o `plan_id`:
    - Se novo usuário: Atribui Plano Freemium e leva para `<tela_1>`.
    - Se usuário recorrente: Leva para `<tela_1>`.
</tela_0>

<tela_1>
**Dashboard (Hub Central).**
- Resumo visual: Card com "Total de Análises Realizadas" e "Status do Plano Atual".
- Botão principal **"Nova Análise"** (destaque visual): Encaminha para `<tela_2>`.
- Lista de "Análises Recentes": Cards clicáveis que levam para o histórico na `<tela_7>`.
- Barra Lateral/Navegação: Perfil, Histórico, Biblioteca de Assets e Upgrade.
</tela_1>

<tela_2>
**Input da Campanha (Chat de Intake).**
Interface estilo ChatGPT onde o **Agente Orquestrador** inicia a conversa.
- O robô solicita: "Descreva sua campanha, produto e quem você acredita ser seu público."
- Opção de **Upload de Arquivos**: Botão de clipe para PDF, DOCX ou Imagens de anúncios.
- **Regra de Negócio (Triagem T1):** A IA deve validar se a descrição contém (Para quem + Resultado + Prazo + Mecanismo).
    - Se faltar informação: A IA faz perguntas curtas de clarificação.
    - Se info OK: Libera o botão "Iniciar Análise Científica" que leva para `<tela_3>`.
- **Validação de Limite:** Antes de permitir o upload, o sistema checa o `uploads_limit` do plano do usuário.
</tela_2>

<tela_3>
**Processamento Multi-Agente (Checklist Ativo).**
Tela de transição com animação de "escaner" ou checklist processando em tempo real.
- Status visível para o usuário:
    - [ ] Consultando dados demográficos (Integração IBGE/Sidra).
    - [ ] Acionando Analista Sociocomportamental.
    - [ ] Calculando Equação de Valor e Regras de Triagem.
    - [ ] Auditando Performance e Timing Index.
- Ao finalizar (aprox. 10-15 segundos), encaminha automaticamente para `<tela_4>`.
</tela_3>

<tela_4>
**Report Executivo (Diagnóstico).**
Apresentação do resultado analítico gerado pelo **Agente Sintetizador**.
- **Score Geral:** Círculo de progresso de 0 a 100.
- **Veredicto do Estrategista:** Texto direto sobre o erro fatal ou maior oportunidade.
- **Grid de 3 Colunas (Frentes Analíticas):**
    1. **Sociocomportamental:** Geração identificada, Era do Marketing (1.0 a 4.0) e gatilhos mentais.
    2. **Oferta:** Notas da Equação de Valor (Resultado, Probabilidade, Latência, Esforço).
    3. **Performance/Timing:** Análise de KPIs e indicação de timing (Always-on vs Pulsed).
- Botão "Gerar Campanha Otimizada" leva para `<tela_5>`.
</tela_4>

<tela_5>
**Campanha Otimizada (Ready-to-Launch).**
O plano de ação prático para o usuário.
- **Nova Promessa:** Título reescrito com base em neuromarketing.
- **Mix de Canais:** Ícones das redes sociais recomendadas com justificativa.
- **Audiência Sintética:** Cards laterais com "comentários fictícios" de cada geração (Gen Z, Millennial, X, Boomer) sobre a campanha proposta.
- **Plano de Teste A/B:** Sugestão de variável de controle e variável desafiante.
- Botão "Exportar Material" leva para `<tela_6>`.
</tela_5>

<tela_6>
**Exportação e Integração.**
- Opções de Download: Botões para PDF, JPEG e DOCX.
- Integrações Externas:
    - Botão **Canva**: Abre modal para escolher template e enviar os dados da IA.
    - Botão **Gamma**: Gera estrutura de apresentação de slides.
- **Exclusivo Enterprise:** Botão "Conectar Meta Ads" para enviar a estratégia direto para o Gerenciador de Anúncios.
</tela_6>

<tela_7>
**Histórico e Biblioteca.**
- Lista de todas as `UserRequest` passadas.
- Filtro por data e Score.
- Cada item tem:
    - Resumo de uma linha.
    - Botão de "Reabrir Chat" (para continuar conversando com a IA sobre aquela campanha).
    - Botão de "Avaliar" (Like/Deslike) para alimentar o fluxo de feedback da IA.
</tela_7>

<tela_8>
**Gestão de Plano e Assinatura.**
- Exibição do plano atual.
- Tabela comparativa de preços e recursos:
    - **Freemium:** 2 uploads, relatório básico.
    - **Standard:** 5 uploads, audiência sintética.
    - **Pro:** Ilimitado, templates avançados.
    - **Enterprise:** Integração Meta API, Dashboards personalizados.
- Botão "Upgrade" que aciona o fluxo de checkout (Stripe).
</tela_8>

<norma_legal>
**Diretrizes de Inteligência e Dados:**
- **Neuromarketing:** Toda análise deve usar o modelo de Sistema 1 (Rápido/Emocional) e Sistema 2 (Lógico/Devagar).
- **Dados Geográficos:** Sempre que uma localização for mencionada, o sistema deve injetar no prompt do agente os dados de População e Renda via API do IBGE/Sidra.
- **Equação de Valor:** As notas de oferta devem seguir a lógica: (Resultado x Probabilidade) / (Tempo x Esforço).
- **Privacidade:** Todos os dados de upload devem ser tratados via RLS (Row Level Security) no Supabase.
</norma_legal>