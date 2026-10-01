Você é um Engenheiro de Software Sênior e Especialista em UX/UI de Produtos Digitais. Sua missão é refatorar a interface e o fluxo de navegação do SaaS "Tudo Para Mulheres" (que possui perfis de Cliente e Profissional) para resolver problemas críticos de usabilidade, encontrabilidade e arquitetura de informação.

A base técnica e o roteamento (auth/callback) já funcionam. O objetivo agora é elevar a maturidade da UX, transformando "telas soltas" em "fluxos orientados à ação" e reduzindo a carga cognitiva do usuário.

Abaixo estão as especificações exatas do que deve ser implementado. Dividi o trabalho em 4 frentes principais. Leia atentamente e depois execute.

### FRENTE 1: Refatoração do Onboarding Público (Acesso)
**Problema atual:** A tela de Welcome causa ambiguidade na criação de conta. O usuário só descobre a diferença entre Cliente e Profissional tarde demais no funil.
**O que você deve fazer:**
1. Redesenhe a tela de Welcome/Cadastro inicial.
2. Crie uma bifurcação visual explícita e impossível de ignorar ANTES do formulário de cadastro.
3. Use botões de CTA claros: "Criar conta como Cliente" e "Criar conta como Profissional".
4. Remova qualquer fricção ou links confusos que misturem os dois fluxos.

### FRENTE 2: Reestruturação da Jornada do Cliente
**Problema atual:** A Home está sobrecarregada (Busca + Feed + Editorial + Listagem) e a rota `/cliente/busca` está órfã ou competindo com a Home. Os Favoritos não têm peso estratégico.
**O que você deve fazer:**
1. **Limpeza da Home:** Transforme a Home do Cliente estritamente em um hub de "Encontrar e Contratar". Remova o excesso de informações. O bloco editorial ("História das Heroínas") deve ser movido para um destaque secundário, abaixo do fold principal.
2. **Unificação da Busca:** Integre definitivamente a busca na Home ou transforme o CTA da Home em um redirecionamento limpo para `/cliente/busca`. Elimine a concorrência de funções. Crie um fluxo progressivo (Filtros claros: categoria > proximidade > disponibilidade > preço).
3. **Elevação dos Favoritos:** Transforme a tela de Favoritos em uma "Shortlist de Decisão". Adicione CTAs rápidos nos cards favoritados para "Agendar" ou "Enviar Mensagem", permitindo reentrada rápida no funil de conversão.

### FRENTE 3: Transformação da Área do Profissional (Cockpit)
**Problema atual:** O dashboard é apenas um resumo passivo. Faltam conexões entre Pedidos, Agenda e Chat. A tela de Perfil está sobrecarregada servindo de depósito de links.
**O que você deve fazer:**
1. **Dashboard Ativo (Cockpit):** Refatore o dashboard inicial do Profissional para priorizar ações. O topo da tela deve mostrar "Pedidos que exigem ação" e "Agenda do dia".
2. **Conexão de Fluxo:** Implemente continuidade visual e lógica: Quando um profissional aceita um "Pedido", deve haver um botão imediato de "Ir para Agenda" ou "Abrir Chat com Cliente". 
3. **Limpeza do Perfil & Logout:** Retire o botão de Logout e as configurações gerais do meio do Perfil. Crie uma seção clara de "Configurações" separada por: Dados Pessoais, Conta, Plano, Ajuda e um botão isolado e claro para Logout.

### FRENTE 4: Descoberta e Regras do Chat
**Problema atual:** O chat é restrito a vínculos prévios (agendamentos), mas a interface não deixa isso claro e faltam atalhos para acessá-lo.
**O que você deve fazer:**
1. Adicione botões de "Abrir Chat" diretamente nos cards de Agendamentos (tanto para o Cliente quanto para o Profissional).
2. Se o chat estiver bloqueado (por falta de vínculo/agendamento), mostre o botão desabilitado com um tooltip ou microcopy claro explicando a regra: "O chat será liberado após a confirmação do agendamento".

---

### INSTRUÇÕES DE FORMATAÇÃO E REGRAS DE EXECUÇÃO:
- Utilize os componentes de UI já existentes no projeto (Tailwind/shadcn ou a biblioteca padrão que estamos usando) para manter a consistência visual.
- Mantenha a rota `/auth/callback` intacta, ela gerencia o estado da sessão perfeitamente.
- O código gerado deve ser modular, limpo e devidamente comentado.

### REFOCO DA TAREFA:
Para evitar falhas na arquitetura, quero que você aplique a técnica de raciocínio lógico. Antes de escrever o código das telas, escreva "Let's think step-by-step" e descreva brevemente como você vai estruturar a árvore de componentes para resolver os problemas citados. 

Após a explicação lógica, forneça um resumo executivo do que foi realizado ou atualizado para as principais telas afetadas (Welcome, Home Cliente, Dashboard Profissional e a nova estrutura de Navegação/Logout).