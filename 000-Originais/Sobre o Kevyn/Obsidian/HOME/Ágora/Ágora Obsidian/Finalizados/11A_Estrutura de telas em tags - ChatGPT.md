<ao_abrir>
Animação do logo da Ágora com transição suave para a <tela_0>.

A abertura deve comunicar rapidamente a proposta de valor da plataforma: previsibilidade, inteligência de marketing e análise científica de campanhas.

Após a animação inicial, o usuário é encaminhado para a <tela_0>.
</ao_abrir>

<tela_0>
Tela de landing page / boas-vindas.

Esta tela deve apresentar:
- logo da Ágora
- título principal com promessa de valor
- subtítulo explicando que a plataforma usa IA, dados e previsibilidade para otimizar campanhas
- seção com benefícios principais
- seção com prova social
- grade com os 4 planos: Freemium, Standard, Pro e Enterprise

Botões desta tela:
- "Começar Agora" leva para <tela_2>
- "Entrar" leva para <tela_1>
- "Começar Grátis" em um plano leva para <tela_1>
- "Assinar Agora" em um plano pago leva para <tela_1>

A landing precisa funcionar como página de aquisição e convencimento. O foco principal é fazer o usuário iniciar rapidamente a primeira análise.
</tela_0>

<tela_1>
Tela de login e cadastro.

Essa tela deve alternar entre:
- login
- criar conta
- recuperação de senha

No modo login, mostrar:
- campo de e-mail
- campo de senha
- botão "Entrar"
- link "Esqueci minha senha"
- botão alternador para cadastro

No modo cadastro, mostrar:
- nome
- e-mail
- senha
- botão "Criar conta"
- opção de login social
- link para termos de uso e política de privacidade
- botão alternador para login

No modo recuperação de senha, mostrar:
- campo de e-mail
- botão "Enviar link de recuperação"
- botão "Voltar para login"

Regras de navegação:
- login concluído leva para <tela_2>
- cadastro concluído leva para <tela_2>
- recuperação de senha concluída retorna para login
- botão "Voltar" leva para <tela_0>

Se o usuário veio da landing ao clicar em um plano, o sistema já deve manter o plano selecionado em contexto para continuar depois.
</tela_1>

<tela_2>
Tela de dashboard / hub central.

Essa é a tela principal após autenticação.

Ela deve exibir:
- saudação inicial
- resumo das análises recentes
- indicadores gerais de uso
- atalhos principais
- navegação lateral ou superior

Itens principais da navegação:
- "Nova Análise" leva para <tela_4>
- "Histórico de Campanhas" leva para <tela_3>
- "Biblioteca de Assets" leva para <tela_10>
- "Gestão da Conta" leva para <tela_11>

No corpo principal da tela:
- cards com análises recentes
- status das últimas campanhas
- resumo de performance do usuário
- plano atual
- limite de uploads disponível conforme plano

Se o usuário for Enterprise, pode existir um bloco adicional com integração de dados externos, levando para <tela_12>.

Essa tela funciona como centro operacional do SaaS.
</tela_2>

<tela_3>
Tela de histórico de campanhas.

Cada bloco de histórico deve ter:
- nome ou resumo curto da campanha analisada
- data
- score geral da campanha
- status da análise
- tipo de análise gerada
- canais principais recomendados
- ação de abrir relatório
- ação de avaliar resultado

Botões e ações:
- clicar em um item do histórico leva para <tela_7>
- botão de filtro refina a listagem por data, tipo de campanha ou status
- botão "Nova Análise" leva para <tela_4>
- botão "Voltar ao Dashboard" leva para <tela_2>

Essa tela deve permitir revisitar resultados antigos sem perder contexto.
</tela_3>

<tela_4>
Tela de nova análise / intake inicial da campanha.

Essa é a porta de entrada do Core Engine.

A tela deve conter:
- título explicando que o usuário irá descrever a campanha
- campo principal de texto ou chat de briefing
- área para upload de arquivos
- orientação breve do que informar
- bloco opcional com perguntas iniciais guiadas

O usuário deve conseguir informar:
- produto ou serviço
- público-alvo declarado
- canais atuais
- objetivo da campanha
- métricas já acompanhadas
- contexto de mercado
- região ou localidade, se relevante

Botões:
- "Anexar Arquivos"
- "Enviar Briefing"
- "Cancelar"
- "Voltar"

Regras:
- "Anexar Arquivos" abre <tela_5>
- "Enviar Briefing" leva para <tela_6>, desde que exista contexto mínimo
- "Voltar" leva para <tela_2>

Essa tela deve ser simples e parecida com uma experiência de prompt bem guiada.
</tela_4>

<tela_5>
Tela de upload de arquivos de apoio.

Aqui o usuário envia materiais que ajudem a IA a analisar a campanha.

Exemplos de arquivos aceitos:
- briefing
- PDF de campanha
- prints de criativos
- relatórios
- apresentações
- planilhas
- documentos estratégicos

Elementos da tela:
- área de arrastar e soltar arquivos
- botão de upload manual
- lista dos arquivos anexados
- status de envio
- indicador de limite de uploads conforme plano

Botões:
- "Adicionar Arquivo"
- "Remover Arquivo"
- "Concluir Upload"
- "Voltar"

Regras:
- "Concluir Upload" retorna para <tela_4> com os arquivos já anexados ao contexto
- se o usuário atingir o limite do plano, exibir modal de upgrade levando para <tela_13>
- "Voltar" retorna para <tela_4>

Essa tela precisa deixar claro o limite por plano e o valor do upgrade.
</tela_5>

<tela_6>
Tela de triagem e clarificação da IA.

Após o envio do briefing, a IA executa a triagem inicial e verifica se faltam dados importantes.

A tela deve exibir:
- resumo do que foi entendido pela IA
- lista das variáveis identificadas
- bloco de perguntas de clarificação, se necessário
- status do processamento inicial

Se faltarem dados, o usuário responde diretamente nesta tela.

Exemplos do que a IA pode pedir:
- indústria
- público-alvo mais específico
- orçamento
- canal principal
- KPI principal
- tipo de campanha
- objetivo de negócio

Botões:
- "Responder e Continuar"
- "Editar Briefing"
- "Cancelar Análise"

Regras:
- se faltarem dados, "Responder e Continuar" mantém o usuário em <tela_6> até concluir a triagem
- se os dados estiverem suficientes, "Responder e Continuar" leva para <tela_7>
- "Editar Briefing" volta para <tela_4>
- "Cancelar Análise" volta para <tela_2>

Essa tela é a etapa de validação antes de iniciar a análise completa.
</tela_6>

<tela_7>
Tela de processamento da análise.

Aqui o usuário acompanha o andamento do motor multiagente da Ágora.

A tela deve mostrar:
- barra de progresso geral
- checklist dos especialistas processando
- estados de cada etapa
- mensagens curtas explicando o que está acontecendo

Etapas visíveis:
- triagem concluída
- análise sociocomportamental
- análise de oferta
- análise de performance e KPIs
- síntese estratégica final

É importante mostrar os nomes das frentes:
- Sociocomportamental
- Oferta
- Performance
- Estratégia Final

Botões:
- "Cancelar"
- "Voltar ao Dashboard"

Regras:
- ao finalizar o processamento, o usuário é encaminhado para <tela_8>
- se houver erro, exibir opção de tentar novamente
- "Cancelar" volta para <tela_2>

Essa tela deve transmitir inteligência, transparência e sensação de profundidade analítica.
</tela_7>

<tela_8>
Tela de report executivo.

Essa é a tela principal de entrega da análise.

Ela deve apresentar:
- score geral da campanha
- veredicto resumido
- diagnóstico sociocomportamental
- análise de oferta
- auditoria de métricas e timing
- resumo dos principais erros
- resumo das principais oportunidades

Também deve mostrar um dashboard com nota de 1 a 5 para cada frente:
- Sociocomportamental
- Oferta
- Performance

Além disso, incluir:
- blocos com insights principais
- pontos críticos da campanha
- recomendação estratégica inicial

Botões:
- "Ver Campanha Otimizada" leva para <tela_9>
- "Conversar com o Estrategista" leva para <tela_14>
- "Avaliar Resultado" abre feedback rápido na própria tela
- "Voltar ao Dashboard" leva para <tela_2>

Essa tela é o coração do produto e deve parecer uma entrega premium.
</tela_8>

<tela_9>
Tela de campanha otimizada.

Aqui o usuário vê a versão corrigida da campanha.

A tela deve conter:
- nova promessa principal
- público-alvo corrigido
- mix de canais corrigido
- tom de voz recomendado
- estratégia de neuromarketing
- plano de experimentação A/B
- hipótese principal a ser validada
- métrica north star recomendada

Pode existir navegação em abas:
- Visão Geral
- Canais
- Audiência
- Criativos
- Testes
- Exportação

Também devem aparecer comentários geracionais simulados sobre a campanha, como visão de:
- Geração Z
- Millennials
- Geração X
- Boomers

Botões:
- "Exportar Material" leva para <tela_15>
- "Editar Apresentação" leva para <tela_16>
- "Conversar com o Estrategista" leva para <tela_14>
- "Voltar ao Relatório" leva para <tela_8>

Essa tela transforma diagnóstico em plano de ação.
</tela_9>

<tela_10>
Tela de biblioteca de assets.

Essa tela deve concentrar:
- prompts salvos
- arquivos utilizados em análises anteriores
- relatórios exportados
- apresentações geradas
- materiais auxiliares

Cada item da biblioteca deve mostrar:
- nome
- tipo de arquivo
- data
- vínculo com campanha, se houver
- ação de abrir
- ação de baixar
- ação de reutilizar

Botões:
- "Abrir"
- "Baixar"
- "Reutilizar em Nova Análise"
- "Voltar"

Regras:
- "Reutilizar em Nova Análise" leva para <tela_4> com contexto parcialmente preenchido
- "Voltar" leva para <tela_2>
</tela_10>

<tela_11>
Tela de gestão da conta.

Essa tela reúne:
- dados do usuário
- plano atual
- limite de uploads
- status da assinatura
- configurações de perfil
- preferências de uso
- logout

Seções:
- perfil
- plano e cobrança
- segurança
- preferências
- histórico de uso

Botões:
- "Editar Perfil"
- "Gerenciar Plano" leva para <tela_13>
- "Conectar APIs" leva para <tela_12> se Enterprise
- "Sair"
- "Voltar"

Essa tela organiza a camada administrativa do SaaS.
</tela_11>

<tela_12>
Tela de integrações de dados externas.

Essa tela deve ser exclusiva ou prioritária para usuários Enterprise.

Ela deve permitir:
- conectar API da Meta
- conectar fontes de performance
- visualizar status das integrações
- validar conexão
- remover conexão

Elementos:
- cards de integrações disponíveis
- status conectado / desconectado
- informações sobre benefício da integração

Botões:
- "Conectar"
- "Validar"
- "Desconectar"
- "Voltar"

Regras:
- acesso restrito conforme plano
- se o usuário não tiver permissão, exibir CTA de upgrade levando para <tela_13>
- "Voltar" leva para <tela_11>
</tela_12>

<tela_13>
Tela de planos e upgrade.

A tela deve mostrar comparação clara entre:
- Freemium
- Standard
- Pro
- Enterprise

Cada plano deve listar:
- limite de uploads
- acesso à audiência sintética
- exportações disponíveis
- integrações disponíveis
- profundidade da análise

Botões:
- "Assinar Plano"
- "Fazer Upgrade"
- "Voltar"

Regras:
- ao confirmar assinatura ou upgrade, o usuário retorna para <tela_11> ou para a tela de origem
- se o upgrade veio do bloqueio de upload, após assinar o usuário pode voltar para <tela_5>

Essa tela é crítica para monetização.
</tela_13>

<tela_14>
Tela de chat com o agente estrategista.

Essa tela funciona como continuidade contextual da análise já entregue.

Ela deve abrir com:
- resumo da campanha analisada
- contexto do relatório já carregado
- mensagem inicial da IA perguntando se o usuário quer refinar canais, oferta, público ou testes

O usuário pode:
- tirar dúvidas sobre o diagnóstico
- pedir refinamento
- pedir mais opções de canais
- pedir ajuste no tom de voz
- pedir novas hipóteses de teste

Botões:
- campo de mensagem
- enviar
- anexar contexto adicional
- voltar ao relatório
- voltar à campanha otimizada

Regras:
- "Voltar ao Relatório" leva para <tela_8>
- "Voltar à Campanha Otimizada" leva para <tela_9>

Essa tela precisa parecer um consultor especialista conversando sobre a análise já feita.
</tela_14>

<tela_15>
Tela de exportação.

Aqui o usuário escolhe como deseja baixar ou gerar o material.

Opções de exportação:
- PDF
- PPT
- DOCX
- PNG
- JPEG
- Canva
- Gamma

A tela deve mostrar:
- formato
- descrição curta
- estimativa do tipo de saída
- status da geração

Botões:
- "Exportar PDF"
- "Exportar PPT"
- "Exportar DOCX"
- "Exportar PNG"
- "Exportar JPEG"
- "Abrir no Canva"
- "Abrir no Gamma"
- "Voltar"

Regras:
- exportações locais geram arquivo diretamente
- integrações de edição visual levam para <tela_16>
- "Voltar" leva para <tela_9>
</tela_15>

<tela_16>
Tela de editor / visualizador de apresentação.

Essa tela é usada quando o usuário decide editar a apresentação gerada.

Ela deve conter:
- miniaturas laterais
- canvas central
- ferramentas de design
- ferramentas de conteúdo
- controles de navegação entre páginas ou slides

Botões:
- "Desfazer"
- "Refazer"
- "Salvar"
- "Exportar Final"
- "Voltar"

Regras:
- alterações devem refletir no canvas em tempo real
- "Salvar" mantém o material no histórico / biblioteca
- "Exportar Final" conclui a saída
- "Voltar" leva para <tela_15> ou <tela_9>, conforme origem
</tela_16>

<tela_17>
Modal ou tela de avaliação do resultado.

Essa etapa pode aparecer ao final do relatório ou da campanha otimizada.

A tela deve conter:
- pergunta sobre utilidade do resultado
- botão de like
- botão de dislike
- campo opcional de feedback textual

Se o usuário clicar em like:
- registrar satisfação
- opcionalmente pedir depoimento curto

Se o usuário clicar em dislike:
- abrir campos como:
  - "o que faltou?"
  - "o que pareceu errado?"
  - "qual parte não ajudou?"

Botões:
- "Enviar Avaliação"
- "Pular"
- "Voltar"

Regras:
- após enviar avaliação, retornar para <tela_8> ou <tela_9>, conforme origem
</tela_17>

<fluxo_principal>
Fluxo principal recomendado da Ágora:

<ao_abrir> → <tela_0> → <tela_1> → <tela_2> → <tela_4> → <tela_5> → <tela_6> → <tela_7> → <tela_8> → <tela_9> → <tela_15> ou <tela_14> ou <tela_16>

Fluxos paralelos importantes:
- histórico: <tela_2> → <tela_3> → <tela_8>
- conta: <tela_2> → <tela_11> → <tela_13>
- assets: <tela_2> → <tela_10> → <tela_4>
- enterprise: <tela_11> → <tela_12>
</fluxo_principal>

<observacoes_gerais>
A artéria principal do produto é o fluxo:
Nova Análise → Triagem → Processamento → Report Executivo → Campanha Otimizada.

O sistema deve deixar muito claro quando está:
- coletando contexto
- pedindo clarificação
- processando análise
- entregando diagnóstico
- transformando diagnóstico em ação

A experiência precisa transmitir que a Ágora não é apenas um chat, mas um motor estratégico com múltiplas frentes analíticas.

A lógica de telas acima foi estruturada a partir do modelo em tags do arquivo “Sprint 01 - Em texto corrido.md” e do conteúdo funcional descrito no material da Ágora. 
</observacoes_gerais>