<ao_abrir>
Apresenta uma animação da logo do Ágora, que se transforma em um ícone pulsante, simbolizando a inteligência artificial em ação. A tela então transiciona suavemente para a <tela_0>.
</ao_abrir>

<tela_0>
**Tela: Landing Page (Boas-vindas)**

**Elementos:**
*   **Título Principal:** "O Marketing que Prevê o Futuro."
*   **Subtítulo:** "Use a nossa IA para analisar, otimizar e prever o resultado de suas campanhas antes de investir um centavo."
*   **Cards de Funcionalidades:** Uma grade visual destacando: "Análise Sociocomportamental", "Engenharia de Oferta", "Otimização de Performance" e "Simulação com Audiências Sintéticas".
*   **Prova Social:** Uma seção com depoimentos e estatísticas como "Reduza em até 40% o desperdício com anúncios ineficazes".
*   **Grade de Planos:** Apresentação clara dos planos Freemium, Standard, Pro e Enterprise, com seus respectivos benefícios e limitações.
*   **Botão (CTA Principal):** "Começar Agora".
*   **Botões Secundários:** "Começar Grátis" (no plano Freemium) e "Assinar Agora" (nos planos pagos).

**Ações:**
*   Ao clicar em "Começar Agora", o usuário é direcionado para a <tela_2> para uma experiência rápida e sem atritos.
*   Ao clicar nos botões dos planos, o usuário é levado para a <tela_1>.
</tela_0>

<tela_1>
**Tela: Login / Cadastro**

**Elementos:**
*   Logo do Ágora.
*   Formulário com campos para "Nome", "Email" e "Senha".
*   Opções de Login Social com "Google" e "Facebook" para facilitar o acesso.
*   Link para "Esqueceu a senha?".
*   Alternador para mudar entre "Já tenho uma conta. Fazer login" e "Não tem uma conta? Cadastre-se".

**Ação:**
*   Após o login ou cadastro bem-sucedido, o usuário é encaminhado para a <tela_2_dashboard>.
</tela_1>

<tela_2_dashboard>
**Tela: Dashboard (Hub Central)**

**Elementos:**
*   **Barra de Navegação:** Acesso rápido para "Nova Análise", "Histórico de Campanhas" e "Gestão da Conta" (Perfil e Planos).
*   **Seção Principal:**
    *   Um resumo de análises recentes em formato de cards, mostrando o "Score Geral da Campanha" e a data da análise.
    *   Um gráfico simples com a evolução dos scores das últimas campanhas analisadas.
*   **Botão (CTA Principal):** "Nova Análise", que leva o usuário para a <tela_3>.

**Ação:**
*   Clicar em um card de análise recente abre o relatório correspondente na <tela_5>.
*   Clicar em "Histórico de Campanhas" leva para a <tela_2_historico>.
</tela_2_dashboard>

<tela_2_historico>
**Tela: Histórico de Campanhas**

**Elementos:**
*   Uma lista detalhada de todas as análises já realizadas pelo usuário.
*   **Filtros:** Opções para filtrar as análises por data ou tipo de campanha.
*   **Ações por Análise:**
    *   **Resumo:** Nome da campanha, data e o "Score Geral".
    *   **Botão "Ver Relatório":** Leva para a <tela_5>.
    *   **Ação "Avaliar Resultado":** Permite ao usuário dar um feedback (Like/Dislike) sobre a análise.

**Ação:**
*   O uso dos filtros atualiza a lista de campanhas exibida.
</tela_2_historico>

<tela_3>
**Tela: Chat de Análise (Core Engine)**

**Elementos:**
*   **Avatar do Agente Orquestrador:** Com um indicador de status (ex: "Analisando...", "Aguardando informações...").
*   **Área de Conversa:** Interface de chat onde o usuário descreve sua campanha e interage com a IA.
*   **Área de Composição de Mensagem:** Campo de texto para o usuário digitar, com um botão para anexar arquivos (documentos de briefing, planilhas de métricas, etc.).
*   **Mensagem Inicial (Padrão do Agente):** "Olá! Eu sou o estrategista-chefe do Ágora. Para começarmos, por favor, descreva a sua campanha. Inclua o produto ou serviço, o público-alvo que você imagina e os canais que está utilizando."

**Ações:**
*   O usuário envia a descrição da campanha e anexa os arquivos relevantes.
*   A IA (Agente Orquestrador) processa a entrada e, se necessário, faz perguntas de clarificação na mesma interface de chat.
*   Uma vez que a IA tenha informações suficientes, ela exibe uma mensagem de confirmação: "Entendido. Nossos especialistas estão analisando sua campanha. Isso levará alguns instantes." e transiciona para a <tela_4>.
</tela_3>

<tela_4>
**Tela: Processamento e Análise**

**Elementos:**
*   **Barra de Progresso Dinâmica:** Um checklist visual que mostra o status de cada sub-agente em tempo real:
    *   [✓] Agente Orquestrador: Dados normalizados.
    *   [Em andamento] Analista Sociocomportamental: Perfil do público-alvo em construção.
    *   [Aguardando] Engenheiro de Oferta: Avaliação da proposta de valor.
    *   [Aguardando] Cientista de Performance: Análise de métricas e timing.
    *   [Aguardando] Estrategista-Chefe: Compilando o relatório final.
*   **Mensagem de Engajamento:** Pequenos insights ou dicas de marketing aparecem enquanto o usuário espera.

**Ação:**
*   Após a conclusão de todas as etapas, a tela redireciona automaticamente para a <tela_5>.
</tela_4>

<tela_5>
**Tela: Relatório Executivo e Estratégia Otimizada**

**Elementos:**
*   **Score Geral da Campanha:** Um número destacado de 0 a 100, com um veredito de uma linha do estrategista-chefe.
*   **Dashboard de Frentes Analíticas:** Notas de 1 a 5 para "Sociocomportamental", "Oferta" e "Performance".
*   **Abas de Navegação:**
    *   **Diagnóstico:** Mostra o detalhamento da análise de cada especialista (erros, acertos e justificativas).
    *   **Campanha Otimizada:** Apresenta a versão corrigida com a "Nova Promessa", "Mix de Canais Corrigido" e o "Plano de Experimentação (Teste A/B)".
    *   **Voz da Audiência:** Exibe cards com comentários simulados de cada geração (Z, Millennials, X, Boomers) sobre a campanha original e a otimizada.
*   **Chat de Refinamento:** Uma janela de chat lateral permite que o usuário faça perguntas sobre o relatório para o Agente Estrategista.
*   **Botões de Exportação:** Opções para "Baixar Relatório (PDF, JPEG)" ou "Gerar Apresentação (Canva, Gamma)".

**Ações:**
*   A seleção de uma opção de exportação de apresentação leva para a <tela_6>.
*   A interação no chat de refinamento gera respostas contextuais da IA.
</tela_5>

<tela_6>
**Tela: Editor de Apresentação (Integração)**

**Elementos:**
*   **Visualização Central:** O canvas principal onde a apresentação gerada (pelo Canva ou Gamma) é exibida.
*   **Barra Lateral de Slides:** Miniaturas de todos os slides da apresentação para fácil navegação.
*   **Ferramentas de Edição Básicas:** Opções para alterar textos, cores e imagens, aproveitando a API da ferramenta integrada.

**Botões:**
*   "Salvar Alterações".
*   "Exportar" (no formato final desejado, como PPT ou PDF).
*   "Voltar para o Relatório".

**Ação:**
*   O usuário pode fazer ajustes finos na apresentação antes de exportá-la, garantindo que o material final esteja perfeitamente alinhado com a identidade visual da sua marca.
</tela_6>