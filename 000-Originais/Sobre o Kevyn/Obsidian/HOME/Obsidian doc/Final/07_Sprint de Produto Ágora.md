### Tela: Landing Page (Boas-vindas)
**Elementos**
- Logo Ágora
- Título: "O Marketing que Prevê o Futuro"
- Subtítulo: Descrição de valor (IA + Previsibilidade)
- Grade de 4 Cards (Funcionalidades: IA Generativa, Segmentação, Previsibilidade, Resultados)
- Seção de Prova Social (Redução de desperdício)
- Grade de 4 Planos (Freemium, Standard, Pro, Enterprise)

**Botões**
- "Começar Agora" (CTA principal)
- "Começar Grátis" / "Assinar Agora" (em cada plano)

**Ação**
- Clicar em "Começar Agora" direciona para <Tela: Chat>.
- Clicar nos botões de plano direciona para <Tela: Login/Cadastro>.

---

### Tela: Login/Cadastro
**Elementos**
- Logo Ágora
- Título dinâmico (Login ou Criar Conta)
- Campos de formulário (Nome, Email, Senha)
- Login Social (Google e Facebook)
- Link "Esqueceu a senha?"

**Botões**
- "Entrar" / "Criar Conta"
- Alternadores ("Cadastre-se" / "Faça login")
- "Voltar"

**Ação**
- Submissão do formulário redireciona para <Tela: Chat>.

---

### Tela: Chat (Core Engine)
**Elementos**
- Avatar do "Agent Prin" + Indicador de Status (Pulsante)
- Área de conversação (mensagens IA e Usuário)
- Checklist de Análise (Aparece após primeiro envio)
- Área de composição de mensagem com suporte a anexos

**Botões**
- Anexo de arquivos
- Remover anexo
- Enviar (ou Enter)
- Voltar (Topo)

**Ação**
- Envio de briefing/dados inicia fluxo de agentes (Triagem -> Especialistas -> Sintetizador).
- Após análise e confirmação do usuário, redireciona para <Tela: Apresentação>.

---

### Tela: Apresentação da Campanha Otimizada
**Elementos**
- Blocos de Estatísticas (Orçamento, Alcance, ROI, Canais, Dashboard que mostra uma nota de 1 a 5 para cada "frente" analisada: Sociocomportamental, Oferta e Performance)
- Abas (Visão Geral, Canais, Audiência, Criativos, Exportação)
- Conteúdo estratégico (Nova Promessa, Mix de Canais, Público-Alvo)
- Cartões que vão se alternando mostrando o ponto de vista de cada geração sobre a campanha.

**Botões**
- "Compartilhar"
- Exportação (Canva, Gamma, PDF, JPEG)
- Voltar

**Ação**
- Seleção de "Canva" ou "Gamma" processa o material e redireciona para <Tela: Editor>.
- Seleção de PDF ou JPEG dispara exportação local.

---

### Tela: Editor de Apresentação
**Elementos**
- Miniaturas de slides (lateral esquerda)
- Canvas de visualização (centro)
- Ferramentas de Design (cor, layout, elementos)
- Ferramentas de Conteúdo (texto)

**Botões**
- Desfazer / Refazer
- Salvar
- Exportar (Final)
- Voltar

**Ação**
- Navegação entre slides atualiza o Canvas central.
- Ações de design/conteúdo atualizam o slide selecionado em tempo real.

---

### 💡 Observações do Sprint
1. **Prioridade Máxima:** O fluxo <Tela: Chat> para <Tela: Apresentação> é a "Artéria" do Ágora. Este é o ponto de maior complexidade de integração (Frontend <-> Backend <-> IAs especialistas).
2. **Plano Enterprise:** A funcionalidade de "Vinculação com API da Meta" citada na mentoria e nos documentos deve estar visível apenas para usuários do plano Enterprise, possivelmente no dashboard de histórico.
3. **Persistência:** Todas as ações em <Tela: Editor> e <Tela: Chat> devem ter seus estados persistidos no banco de dados (`user_request` e `agent_response`) para garantir que o usuário não perca o trabalho.