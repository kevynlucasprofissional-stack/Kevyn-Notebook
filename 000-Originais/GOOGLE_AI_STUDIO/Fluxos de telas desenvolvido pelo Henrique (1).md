
```xml
<sprint_agora_prototipo>

  <visao_geral>
  Este sprint descreve o fluxo completo do protótipo do SaaS Ágora, desde a entrada na landing page até a visualização da campanha otimizada, edição da apresentação e exportação. O sistema é composto por cinco telas principais: landing page, login/cadastro, chat com o agente, apresentação da campanha e editor de apresentação. A navegação é linear, porém com pontos de retorno. O objetivo do fluxo é conduzir o usuário da descoberta do produto até a geração e edição de uma apresentação estratégica criada por IA.
  </visao_geral>

  <rotas_principais>
  A aplicação possui as seguintes rotas principais. A rota "/" abre a tela inicial de boas-vindas. A rota "/login" abre a tela de login e cadastro. A rota "/chat" abre a interface conversacional com o Agent Prin. A rota "/presentation" abre a tela de apresentação da campanha otimizada. A rota "/editor" abre o editor da apresentação.
  </rotas_principais>

  <logica_global_de_navegacao>
  O fluxo principal esperado é: <tela_0_landing> leva para <tela_2_chat> pelo botão principal “Começar Agora”, ou leva para <tela_1_login> pelos botões de assinatura dos planos. A <tela_1_login> leva para <tela_2_chat> após envio do formulário. A <tela_2_chat> leva para <tela_3_apresentacao> após a conclusão da análise e uma nova interação do usuário. A <tela_3_apresentacao> leva para <tela_4_editor> quando o usuário escolhe exportar em Canva ou Gamma. A <tela_4_editor> pode retornar para <tela_3_apresentacao>.
  </logica_global_de_navegacao>

  <ao_abrir>
  Ao abrir o sistema, o usuário entra em <tela_0_landing>. A interface apresenta a marca Ágora, o posicionamento “O Marketing que Prevê o Futuro”, uma descrição curta do valor do produto, um botão de ação principal, uma grade de funcionalidades, uma frase estatística de impacto e uma seção de planos. O visual reforça modernidade, IA, previsibilidade e automação estratégica.
  </ao_abrir>

  <tela_0_landing>
    <objetivo>
    Apresentar o produto, comunicar proposta de valor, destacar benefícios e conduzir o usuário para iniciar o fluxo ou escolher um plano.
    </objetivo>

    <elementos_visuais>
    A tela possui o logo “Ágora” em destaque, subtítulo principal, texto descritivo, botão principal “Começar Agora”, quatro cards de funcionalidades, texto de prova de valor sobre redução de desperdício em campanhas e uma grade com quatro planos: Freemium, Standard, Pro e Enterprise.
    </elementos_visuais>

    <funcionalidades_exibidas>
    Os cards de funcionalidades mostram IA Generativa, Segmentação Precisa, Previsibilidade e Resultados Rápidos. Cada card comunica um benefício resumido do sistema.
    </funcionalidades_exibidas>

    <secao_de_planos>
    A tela apresenta quatro planos. O plano Freemium informa recursos limitados. O plano Standard adiciona audiência sintética e uploads ilimitados. O plano Pro adiciona template para todas as redes sociais. O plano Enterprise adiciona histórico de feedbacks, vínculo com APIs da Meta e dashboard com métricas atuais e previsibilidade.
    </secao_de_planos>

    <acoes_e_botoes>
    O botão “Começar Agora” chama diretamente <tela_2_chat>.
    Os botões “Começar Grátis” e “Assinar Agora”, exibidos em cada card de plano, chamam <tela_1_login>.
    Não há travas de autenticação antes de entrar em <tela_2_chat> pelo CTA principal.
    </acoes_e_botoes>

    <estado_esperado>
    A tela funciona como porta de entrada comercial e institucional. O usuário pode tanto experimentar rapidamente o produto quanto entrar pelo caminho de assinatura/login.
    </estado_esperado>
  </tela_0_landing>

  <tela_1_login>
    <objetivo>
    Permitir autenticação ou criação de conta antes da continuação do uso comercial do produto.
    </objetivo>

    <modos_da_tela>
    A tela possui dois modos internos: modo login e modo cadastro. O modo login exibe campos de email e senha. O modo cadastro exibe nome completo, email e senha.
    </modos_da_tela>

    <elementos_da_tela>
    A interface contém botão “Voltar”, logo Ágora, título dinâmico conforme o modo, subtítulo explicativo, formulário principal, alternância entre login e cadastro, bloco de login social com Google e Facebook e, no modo login, opção “Lembrar de mim” e link “Esqueceu a senha?”.
    </elementos_da_tela>

    <acoes_e_botoes>
    O botão “Voltar” chama <tela_0_landing>.
    O botão “Entrar” chama <tela_2_chat> após o envio do formulário.
    O botão “Criar Conta” chama <tela_2_chat> após o envio do formulário.
    O botão de alternância “Cadastre-se” troca do modo login para cadastro sem mudar de tela.
    O botão “Faça login” troca do modo cadastro para login sem mudar de tela.
    Os botões “Google” e “Facebook” aparecem visualmente como login social, mas no protótipo não possuem fluxo funcional implementado.
    O link “Esqueceu a senha?” aparece visualmente, mas não chama uma tela real no protótipo atual.
    </acoes_e_botoes>

    <estado_de_envio>
    Após submeter o formulário, há um pequeno atraso simulado e o sistema redireciona o usuário para <tela_2_chat>.
    </estado_de_envio>
  </tela_1_login>

  <tela_2_chat>
    <objetivo>
    Coletar descrição da campanha e arquivos de apoio, simular análise automatizada completa via IA e conduzir o usuário para a apresentação da campanha otimizada.
    </objetivo>

    <estrutura_da_tela>
    A tela possui cabeçalho com botão de voltar, identidade do agente “Agent Prin”, indicador de status e área principal de mensagens. Na parte inferior existe a área de composição da mensagem com suporte a anexos.
    </estrutura_da_tela>

    <estado_inicial>
    Ao entrar na tela, o sistema já mostra uma mensagem do agente explicando que ele é especializado em campanhas de marketing e pedindo para o usuário descrever a campanha e anexar documentos relevantes, como briefing, materiais anteriores e dados do público.
    </estado_inicial>

    <componentes_principais>
    A área conversacional mostra mensagens do usuário, do assistente e do sistema. O usuário pode digitar texto, anexar arquivos e remover arquivos antes do envio. Quando arquivos são adicionados, eles ficam em estado de pré-envio.
    </componentes_principais>

    <acoes_e_botoes>
    O botão de seta no cabeçalho chama <tela_0_landing>.
    O botão de anexo abre seleção de arquivos e adiciona arquivos à lista local da mensagem.
    O botão de remover arquivo exclui um item anexado da lista antes do envio.
    O botão de envio, ou a tecla Enter sem Shift, envia a mensagem atual com ou sem anexos.
    </acoes_e_botoes>

    <fluxo_de_analise_primeira_interacao>
    Na primeira interação enviada pelo usuário, o sistema entra no fluxo de análise completa. Primeiro, adiciona uma mensagem de sistema informando “Iniciando Análise Completa” e exibe uma checklist de etapas. Em seguida, a checklist vai sendo preenchida progressivamente.
    </fluxo_de_analise_primeira_interacao>

    <checklist_de_analise>
    A checklist contém os seguintes itens: Objetivo/Proposta de valor, Características da audiência (IBGE), Segmento (gerado pelo Prin), Perfil do consumidor do público-alvo, Benchmarking, Análise de KPIs, Posicionamento de marca e Análise dos criativos (Canva).
    </checklist_de_analise>

    <resultado_da_analise>
    Ao finalizar a checklist, o sistema mostra uma mensagem de conclusão da análise com score 85. Depois exibe um resumo da análise contendo audiência IBGE identificada, segmento sugerido, canais recomendados, ROI estimado, alcance previsto, pontos fortes e oportunidades de melhoria. A mensagem final pergunta se o usuário deseja visualizar a apresentação completa da campanha otimizada.
    </resultado_da_analise>

    <transicao_para_apresentacao>
    Depois que a análise é concluída, a tela entra em um segundo estado. A próxima mensagem enviada pelo usuário, interpretada como confirmação ou continuação da conversa, dispara a resposta “Perfeito! Preparando sua apresentação personalizada...” e então chama <tela_3_apresentacao>.
    </transicao_para_apresentacao>

    <observacoes_de_comportamento>
    Durante a análise, o cabeçalho muda o status do agente para “Analisando sua campanha...”. Há também indicador visual pulsante junto ao avatar do agente.
    </observacoes_de_comportamento>
  </tela_2_chat>

  <tela_3_apresentacao>
    <objetivo>
    Exibir a campanha otimizada gerada pela IA em formato executivo, organizada por dados estratégicos, canais, audiência, criativos e opções de exportação.
    </objetivo>

    <cabecalho>
    O cabeçalho mostra botão de voltar, título “Sua Campanha Otimizada”, subtítulo “Criada com IA • Pronta para executar” e botão “Compartilhar”.
    </cabecalho>

    <acoes_e_botoes_do_cabecalho>
    O botão de seta no cabeçalho chama <tela_2_chat>.
    O botão “Compartilhar” existe visualmente, porém no protótipo atual não possui navegação ou fluxo funcional implementado.
    </acoes_e_botoes_do_cabecalho>

    <bloco_de_estatisticas>
    A tela apresenta quatro cards de destaque com: orçamento total, alcance estimado, ROI previsto e quantidade de canais principais.
    </bloco_de_estatisticas>

    <dados_da_campanha>
    A campanha exibida no protótipo usa dados simulados como “Campanha de Verão 2026”, orçamento de R$ 25.000, alcance estimado de 2.5M usuários e ROI previsto de 4.2x.
    </dados_da_campanha>

    <abas_principais>
    A apresentação está organizada em abas. O conteúdo inclui visão geral, canais, audiência, criativos e exportação.
    </abas_principais>

    <conteudo_visao_geral>
    A aba de visão geral resume o racional estratégico da campanha e seus indicadores principais.
    </conteudo_visao_geral>

    <conteudo_canais>
    A aba de canais exibe os canais recomendados com orçamento, alcance e engajamento. No protótipo aparecem Instagram & Facebook, Google Ads e TikTok.
    </conteudo_canais>

    <conteudo_audiencia>
    A aba de audiência mostra faixa etária, gênero, localização, interesses e classes sociais prioritárias. No protótipo, a audiência é descrita como 25-45 anos, todos os gêneros, principais capitais do Brasil, interesses em moda, lifestyle e compras online, classes B e C.
    </conteudo_audiencia>

    <conteudo_criativos>
    A aba de criativos mostra os formatos recomendados e suas quantidades, como vídeos curtos, imagens estáticas e carrosséis.
    </conteudo_criativos>

    <bloco_de_exportacao>
    A tela oferece quatro opções de exportação: Canva, Gamma, PDF e JPEG.
    </bloco_de_exportacao>

    <acoes_das_exportacoes>
    O card ou botão de exportação “Canva” chama <tela_4_editor> após simulação de processamento.
    O card ou botão de exportação “Gamma” chama <tela_4_editor> após simulação de processamento.
    O card ou botão de exportação “PDF” não muda de tela; dispara uma ação local de exportação simulada.
    O card ou botão de exportação “JPEG” não muda de tela; dispara uma ação local de exportação simulada.
    </acoes_das_exportacoes>

    <estado_de_exportacao>
    Ao escolher uma exportação, a opção selecionada entra temporariamente em estado de processamento. Após isso, o sistema limpa o estado e executa a ação correspondente.
    </estado_de_exportacao>
  </tela_3_apresentacao>

  <tela_4_editor>
    <objetivo>
    Permitir edição visual simplificada da apresentação gerada, com navegação entre slides, ferramentas de design, conteúdo e exportação.
    </objetivo>

    <cabecalho>
    O cabeçalho mostra botão de voltar, identidade do editor, ações de desfazer, refazer, salvar e exportar.
    </cabecalho>

    <acoes_e_botoes_do_cabecalho>
    O botão de seta no cabeçalho chama <tela_3_apresentacao>.
    O botão “Desfazer” existe visualmente, mas não possui lógica funcional implementada.
    O botão “Refazer” existe visualmente, mas não possui lógica funcional implementada.
    O botão “Salvar” dispara um estado temporário “Salvando...” e depois mostra confirmação local de sucesso, sem trocar de tela.
    O botão “Exportar” dispara uma ação local simulada de exportação, sem trocar de tela.
    </acoes_e_botoes_do_cabecalho>

    <estrutura_interna>
    A tela é dividida em três colunas. A coluna esquerda mostra miniaturas dos slides. A área central mostra o canvas principal do slide selecionado. A coluna direita mostra ferramentas separadas por abas de “Design” e “Conteúdo”.
    </estrutura_interna>

    <navegacao_entre_slides>
    O usuário pode selecionar um slide clicando na miniatura correspondente na lateral esquerda. Também pode avançar e voltar usando os botões “Anterior” e “Próximo” na navegação inferior. Os indicadores em pontos na parte inferior também permitem mudar de slide.
    </navegacao_entre_slides>

    <slides_do_prototipo>
    O protótipo contém quatro slides simulados: “Campanha de Verão 2026”, “Análise de Mercado”, “Estratégia Multi-Canal” e “Resultados Esperados”.
    </slides_do_prototipo>

    <ferramentas_design>
    Na aba “Design”, o usuário vê opções visuais como paleta de cores do tema, opções de layout e elementos gráficos.
    </ferramentas_design>

    <ferramentas_conteudo>
    Na aba “Conteúdo”, o usuário vê ferramentas relacionadas a texto e estrutura do conteúdo do slide. No protótipo, essas ações estão representadas principalmente como interface visual, sem edição profunda implementada.
    </ferramentas_conteudo>

    <estado_esperado>
    Esta tela funciona como editor conceitual de apresentação, servindo como continuidade da exportação para Canva/Gamma. Ela reforça que o material pode ser personalizado antes da entrega final.
    </estado_esperado>
  </tela_4_editor>

  <fluxo_principal_resumido>
  O usuário entra em <tela_0_landing>, entende a proposta de valor e clica em “Começar Agora” para abrir <tela_2_chat>, ou escolhe um plano e vai para <tela_1_login>. Em <tela_1_login>, após autenticação ou cadastro, entra em <tela_2_chat>. Em <tela_2_chat>, descreve a campanha, anexa arquivos e envia. O sistema executa a análise completa, apresenta checklist, score e resumo. Em uma nova interação do usuário, a aplicação chama <tela_3_apresentacao>. Em <tela_3_apresentacao>, o usuário revisa a campanha e pode exportar. Ao escolher Canva ou Gamma, entra em <tela_4_editor>, onde consegue navegar entre slides, salvar, ajustar visualmente e exportar.
  </fluxo_principal_resumido>

  <mapeamento_exato_de_botoes_para_telas>
  Em <tela_0_landing>, “Começar Agora” chama <tela_2_chat>. Em <tela_0_landing>, “Começar Grátis” chama <tela_1_login>. Em <tela_0_landing>, “Assinar Agora” chama <tela_1_login>. Em <tela_1_login>, “Voltar” chama <tela_0_landing>. Em <tela_1_login>, “Entrar” chama <tela_2_chat>. Em <tela_1_login>, “Criar Conta” chama <tela_2_chat>. Em <tela_2_chat>, botão de voltar no topo chama <tela_0_landing>. Em <tela_2_chat>, após análise concluída, a próxima mensagem enviada pelo usuário chama <tela_3_apresentacao>. Em <tela_3_apresentacao>, botão de voltar chama <tela_2_chat>. Em <tela_3_apresentacao>, exportação “Canva” chama <tela_4_editor>. Em <tela_3_apresentacao>, exportação “Gamma” chama <tela_4_editor>. Em <tela_4_editor>, botão de voltar chama <tela_3_apresentacao>.
  </mapeamento_exato_de_botoes_para_telas>

  <estados_importantes_do_sistema>
  O sistema possui estado inicial de descoberta em <tela_0_landing>, estado de autenticação em <tela_1_login>, estado de conversa e coleta de dados em <tela_2_chat>, estado de análise em andamento em <tela_2_chat>, estado de análise concluída em <tela_2_chat>, estado de visualização estratégica em <tela_3_apresentacao> e estado de edição em <tela_4_editor>.
  </estados_importantes_do_sistema>

  <lacunas_do_prototipo_identificadas_no_sprint>
  O protótipo atual ainda não implementa tela real de recuperação de senha, fluxo funcional de login social, compartilhamento real da apresentação, persistência real da edição, exportação real em arquivo e edição detalhada de conteúdo slide a slide. Esses pontos existem visualmente ou conceitualmente, mas ainda estão em estado de protótipo.
  </lacunas_do_prototipo_identificadas_no_sprint>

</sprint_agora_prototipo>
```
