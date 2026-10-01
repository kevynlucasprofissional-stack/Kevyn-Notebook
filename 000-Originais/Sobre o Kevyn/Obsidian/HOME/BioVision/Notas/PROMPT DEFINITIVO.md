---
Modificado:
  - terça-feira 83 24/03/2026
Criado: terça-feira 83 24/03/2026
---
Agora vai ser só BioVision, não vai ser mais um sistema de gestão laboratorial. Todas as funções que são próprias de um sistema de gestão laboratorial devem ser deletadas.
O que antes era apenas função dentro do LabControl agora vai ser o SaaS completo. O BioVision agora é o prato principal e não um acompanhamento.
Para isso, quero que analise todo o código e verifique o que pode ser excluido. Exclua tudo o que for relacionado a gestão laboratorial, vamos ficar só com o Fluxo do BioVision.

O fluxo do usuário deve ser algo como:

Landing Page -> Registrar/login -> Tela inicial do BioVision com opção de ver histórico de análises anteriores ou fazer nova análise -> Caso seja nova análise segue o fluxo já definido atualmente (Nisso não vamos mexer, o atual fluxo do BioVision já está funcionando perfeitamente).

Não vamos mecher em nada do seguinte:
-Sistem prompt do biovision
-Lógica de funcionamento da IA do BioVision
-o "Avalie este resultado"
-A tela de resultado e todos os seus detalhes (Obviamente, visto que a tela de resultado do BioVision faz parte do fluxo do BioVision)
-Todo o fluxo do BioVision

Vamos eliminar:
Tela de escolher/criar laboratório
Cadastrar amostra
Amostras
Caixa de entrada
Mensagens
Gerenciar laboratório

Quero que crie um prompt que já resolva tudo isso. Preste principal atenção na landing page, quero uma landing page ótima, bem bonita, use como inspiração para cores, formato, estilo a imagem do "Viora" que anexei e a landing da ARIX como inspiração suprema de design para o estilo do site inteiro.

As cores, use as cores do "VIORA".





Você é um Engenheiro de Software Sênior, Arquiteto de Produto e Especialista em UX/UI para SaaS construídos com React + Vite + TypeScript + Tailwind + shadcn + Supabase.

Sua missão é refatorar profundamente este projeto para transformá-lo em um SaaS focado exclusivamente no BioVision.

IMPORTANTE: NÃO simplifique os requisitos. NÃO faça uma solução genérica. NÃO preserve telas antigas “só por segurança” se elas forem do escopo de gestão laboratorial. Analise o código real do projeto e refatore com base no que já existe, adaptando tudo aos nomes reais de arquivos, rotas, hooks, tabelas, buckets, funções e componentes. Preserve tudo que já funciona no fluxo do BioVision.

==================================================
OBJETIVO PRINCIPAL
==================================================

Este projeto NÃO será mais um sistema de gestão laboratorial / LIMS.

O que antes era uma funcionalidade dentro do LabControl agora passa a ser o produto principal e completo: o SaaS inteiro será o BioVision.

Quero que você:
1. analise o código inteiro,
2. identifique tudo que é próprio de gestão laboratorial,
3. remova essas partes do frontend, do fluxo, da navegação e da lógica associada,
4. mantenha e valorize tudo que pertence ao BioVision,
5. transforme a experiência em um SaaS bonito, premium, coerente e focado em análise microbiológica por IA.

==================================================
REGRA MÁXIMA: O QUE NÃO PODE SER ALTERADO
==================================================

NÃO MEXER em nada do que já está funcionando no fluxo central do BioVision, especialmente:

- system prompt do BioVision
- lógica da IA do BioVision
- “Avalie este resultado”
- tela de resultado do BioVision e todos os seus detalhes
- todo o fluxo atual do BioVision
- edge functions e lógica analítica do BioVision, exceto ajustes mínimos de integração caso sejam indispensáveis para remover a dependência de laboratório sem quebrar o funcionamento

Em resumo:
preserve o coração do BioVision.
A refatoração deve acontecer ao redor dele, não dentro dele.

==================================================
NOVO POSICIONAMENTO DO PRODUTO
==================================================

O produto agora é um SaaS chamado BioVision.

Não é mais um “LabControl com módulo de IA”.
É o contrário:
BioVision é o produto principal.

A experiência deve comunicar:
- tecnologia
- precisão
- sofisticação
- confiança científica
- rapidez
- automação
- análise microbiológica assistida por IA

==================================================
NOVO FLUXO DO USUÁRIO
==================================================

Fluxo principal desejado:

Landing Page -> Registrar/Login -> Tela inicial do BioVision -> opção de:
(a) ver histórico de análises anteriores
(b) fazer nova análise

Se o usuário clicar em “Nova análise”, seguir exatamente o fluxo atual já existente do BioVision, sem estragar o que já funciona.

==================================================
TELAS / MÓDULOS QUE DEVEM SER ELIMINADOS
==================================================

Eliminar completamente da experiência do usuário, da navegação e do roteamento visível:

- Tela de escolher/criar laboratório
- Cadastrar amostra
- Amostras
- Caixa de entrada
- Mensagens
- Gerenciar laboratório

Isso inclui remover:
- links no sidebar/header
- rotas públicas ou protegidas ligadas a esses módulos
- cards, atalhos e CTAs dessas áreas
- estados, loaders e guards dependentes desses fluxos
- textos “LabControl”, “Sistema de Gestão Laboratorial”, “laboratório ativo”, etc.

==================================================
ANÁLISE DO CÓDIGO ATUAL (IMPORTANTE)
==================================================

Antes de implementar, faça uma varredura cuidadosa no código atual.

Priorize revisar estes pontos do projeto, pois eles são centrais para a refatoração:

- src/App.tsx
- src/pages/Index.tsx
- src/pages/Auth.tsx
- src/components/layout/AppLayout.tsx
- src/components/layout/AppSidebar.tsx
- src/contexts/LabContext.tsx
- src/contexts/AuthContext.tsx
- src/pages/Dashboard.tsx
- src/pages/LabAccessPage.tsx
- src/pages/Samples.tsx
- src/pages/NewSample.tsx
- src/pages/SampleDetail.tsx
- src/pages/ChemicalAnalysis.tsx
- src/pages/MicrobiologicalAnalysis.tsx
- src/pages/InboxPage.tsx
- src/pages/MessagesPage.tsx
- src/pages/ParametersPage.tsx
- src/pages/ReportsPage.tsx
- src/pages/AnalysisHistoryPage.tsx
- src/pages/BioVisionListPage.tsx
- src/pages/BioVisionWizardPage.tsx
- src/pages/BioVisionDetailPage.tsx
- src/hooks/useBioVisionRuns.ts
- src/hooks/useBioVisionAnalyses.ts
- src/hooks/useBioVisionChat.ts
- src/components/sample/BioVisionRunChat.tsx
- supabase/functions/analyze-biovision/index.ts
- supabase/functions/biovision-chat/index.ts
- supabase/functions/biovision-count-ufc/index.ts
- supabase/functions/biovision-score-photo/index.ts

Também revise dependências ligadas a:
- labs
- lab_members
- profiles.active_lab_id
- samples
- chemical_analyses
- microbiological_analyses
- inbox_notifications
- internal_conversations
- internal_messages
- lab_history
- lab_settings
- reports

==================================================
ESTRATÉGIA DE REFATORAÇÃO TÉCNICA
==================================================

Quero uma refatoração limpa e segura, sem quebrar o BioVision.

Diretrizes:

1. Remova a dependência de UX de “laboratório”
O usuário não deve mais precisar:
- criar laboratório
- entrar com código
- selecionar laboratório
- gerenciar laboratório

2. O app deve funcionar como um SaaS focado no próprio usuário autenticado
O histórico do BioVision deve ser do usuário logado.
Se houver dependências antigas de lab_id que forem difíceis de remover de uma vez sem risco, você pode manter compatibilidade técnica temporária no backend, MAS:
- sem expor conceito de laboratório na interface
- sem exigir qualquer tela de laboratório
- sem manter guardas de navegação baseados nisso

3. Refatore as rotas protegidas
Hoje existe dependência forte de LabProtectedRoute e do fluxo /lab.
Isso deve ser removido ou substituído por uma proteção simples baseada apenas em autenticação.
O usuário autenticado deve ir direto para a área do BioVision.

4. Reestruture a navegação
A navegação interna deve ficar simples e focada.
Quero algo como:
- Início
- Histórico
- Nova análise
- Sair

Se fizer sentido, “Nova análise” pode ser CTA principal e não apenas item de menu.

5. Dashboard atual
O Dashboard atual está contaminado por métricas de amostras e lógica LIMS.
Transforme o dashboard em uma Home do BioVision.
Essa tela deve mostrar:
- saudação
- CTA principal “Nova análise”
- CTA secundário “Ver histórico”
- cards de resumo ligados ao BioVision
- lista recente de análises BioVision
- visual premium e focado em IA / análise microbiológica

6. Limpeza de código
Depois da refatoração, remova código morto:
- imports não usados
- componentes órfãos
- hooks órfãos
- páginas órfãs
- rotas antigas
- labels e textos antigos
- estados e queries que não fazem mais sentido

Mas NÃO remova utilitários compartilhados que ainda sejam usados pelo BioVision.

==================================================
LANDING PAGE: PRIORIDADE MÁXIMA
==================================================

A landing page é prioridade total.

Quero uma landing page excelente, bonita, com aparência premium, futurista, tecnológica e confiável.

Use como inspiração:
- imagem do VIORA para paleta de cores, clima visual e hero section
- landing da ARIX como inspiração suprema de design, composição, sofisticação, ritmo visual, contraste, elegância e linguagem de interface

IMPORTANTE:
- use as CORES do VIORA
- use a linguagem visual / estilo / refinamento da ARIX como referência de design do site inteiro

==================================================
DIREÇÃO DE ARTE DA LANDING
==================================================

Características visuais desejadas:

- visual premium de biotech / AI SaaS
- forte sensação de inovação
- hero impactante
- fundos com gradientes profundos em azul
- brilho suave, glow tecnológico e depth
- glassmorphism sutil em cards
- contraste alto
- tipografia grande e elegante
- composição limpa, moderna e editorial
- ar futurista e sofisticado
- aspecto “high-end startup”
- muito mais próximo de um produto premium de IA do que de um software administrativo

Evite:
- aparência genérica de dashboard administrativo
- visual de sistema interno
- cara de ERP/LIMS
- excesso de tabelas na landing
- excesso de blocos quadrados sem respiro
- qualquer estética “burocrática”

==================================================
PALETA / TOKENS VISUAIS
==================================================

Basear a identidade nas cores do VIORA:

- azul-marinho profundo como base
- azuis elétricos / vibrantes para CTA e destaques
- ciano luminoso para acentos
- branco / off-white para contraste
- usar roxo apenas se for extremamente sutil e coerente com o conjunto

Atualize os design tokens globais do projeto para refletir essa nova identidade, inclusive:
- background
- foreground
- primary
- accent
- sidebar
- border
- ring
- cards
- gradientes
- sombras
- estados hover/focus

Quero um sistema visual consistente entre:
- landing
- auth
- home interna do BioVision
- histórico
- telas internas do produto

==================================================
ESTRUTURA DE CONTEÚDO DA LANDING
==================================================

Crie uma landing page completa e convincente em PT-BR, com copy profissional e clara.

Sugestão de estrutura:

1. Header premium
- logo BioVision
- navegação limpa
- CTA principal “Solicitar demonstração” ou “Começar agora”

2. Hero section
- headline forte
- subheadline clara
- CTA principal
- CTA secundário
- arte / mockup / composição visual tecnológica
- deixar explícito que o BioVision usa IA para acelerar e qualificar análises microbiológicas

3. Seção de valor
- rapidez
- precisão
- padronização
- apoio técnico
- melhor interpretação dos resultados

4. Como funciona
Exemplo:
- enviar dados / documentos / imagem
- IA executa análise
- usuário recebe resultado estruturado

5. Casos / tipos de análise suportados
Sem inventar funcionalidades inexistentes.
Apresente o que o produto realmente já suporta no fluxo do BioVision.

6. Seção visual premium com cards
- recursos principais
- confiança
- histórico
- rastreabilidade
- experiência guiada

7. CTA final forte

8. Footer refinado

A landing deve convencer e parecer produto sério pronto para mercado.

==================================================
AUTH / LOGIN / CADASTRO
==================================================

A tela de auth deve ser redesenhada para combinar com a nova marca BioVision.

Remover completamente a identidade LabControl.

Trocar:
- nome LabControl
- “Sistema de Gestão Laboratorial”
- qualquer texto que remeta a uso interno de laboratório

A tela deve parecer parte de um SaaS premium.
Quero consistência com a landing.

==================================================
ARQUITETURA DE ROTAS DESEJADA
==================================================

Reorganize as rotas para refletir o novo produto.

Desejo algo nessa linha:

/ -> Landing page BioVision
/auth -> Login / cadastro BioVision
/dashboard -> Home do BioVision
/biovision -> Histórico de análises
/biovision/new -> fluxo atual existente de nova análise
/biovision/:id -> tela atual de resultado / detalhe

Se for melhor tecnicamente, você pode renomear /dashboard para algo mais coerente, mas mantenha a navegação clara e funcional.
Se remover rotas antigas, crie redirects limpos para evitar quebrar navegação antiga.

==================================================
PRESERVAÇÃO DO FLUXO EXISTENTE DO BIOVISION
==================================================

Muito importante:

- mantenha o wizard atual de criação de análise do BioVision
- mantenha a lógica de upload
- mantenha as integrações com Supabase Storage
- mantenha as chamadas às edge functions do BioVision
- mantenha a tela final de resultado
- mantenha a área “Avalie este resultado”
- mantenha tudo que pertença ao fluxo real do BioVision

Se alguma parte do BioVision hoje depende de activeLabId ou lab_id:
- refatore com o menor risco possível
- preserve o comportamento funcional
- troque a dependência visível de laboratório por ownership do usuário autenticado ou outra estratégia compatível
- não reescreva a lógica da análise em si

==================================================
REGRAS DE IMPLEMENTAÇÃO
==================================================

- Analise o código real antes de editar
- Use os nomes reais de tabelas/colunas/rotas/componentes
- Não invente estruturas paralelas sem necessidade
- Não faça mock genérico
- Não simplifique o escopo
- Preserve o que já funciona
- Remova o que é legado do LIMS
- Faça uma refatoração profissional, consistente e sem remendos
- Se precisar de SQL para remover dependências ou ajustar acesso, gere SQL primeiro e use uma estratégia segura, preferencialmente retrocompatível
- Não quebre o fluxo do BioVision
- Não mexa no system prompt nem na lógica da IA do BioVision

==================================================
RESULTADO ESPERADO
==================================================

Ao final, o projeto deve parecer um SaaS chamado BioVision, e não mais um sistema chamado LabControl.

O usuário deve sentir que:
- entrou em um produto premium de IA
- consegue fazer login rapidamente
- encontra logo de cara a opção de nova análise ou histórico
- usa o BioVision sem qualquer ruído de laboratório, amostras, mensagens internas ou gestão operacional
- está em uma experiência bonita, coerente e pronta para comercialização

==================================================
CHECKLIST FINAL
==================================================

Antes de concluir, valide se:

[ ] a landing page foi completamente redesenhada com inspiração visual em VIORA + ARIX
[ ] a paleta principal segue o VIORA
[ ] o produto inteiro deixou de parecer um LIMS
[ ] todas as telas de laboratório foram removidas da experiência
[ ] a navegação está focada apenas em BioVision
[ ] login/cadastro estão alinhados à nova marca
[ ] o dashboard virou Home do BioVision
[ ] o histórico do BioVision continua funcionando
[ ] nova análise do BioVision continua funcionando
[ ] resultado do BioVision continua intacto
[ ] “Avalie este resultado” continua intacto
[ ] não há sobras visíveis de LabControl no app
[ ] código morto foi removido
[ ] a refatoração ficou limpa, bonita e comercialmente apresentável