Esses feedbacks deram origem ao [[2103262209 - Prompt ajuste de UX UI]]

# Feedback 01

A análise do fluxo atual mostra uma base funcional, mas com quebras de encontrabilidade, ambiguidade na entrada do funil e rotas que existem sem estarem integradas de forma clara à navegação. Pelo seu playbook, isso fere principalmente consistência, encontrabilidade, regra dos 3 cliques e microcopy orientada à ação.

Veredito geral

O fluxo atual funciona tecnicamente.  
Mas ainda não está “redondo” como produto.

Ele tem 3 problemas centrais:

Entrada pública confusa
    
Área cliente mais madura que a área profissional
    
Recursos existentes sem descoberta clara
    

---

1. O que está bom no fluxo atual

Separação por role

Você já tem uma arquitetura correta de alto nível:

splash
    
resolução de sessão
    
role-based routing
    
áreas separadas para cliente e profissional
    

Isso é bom porque reduz ambiguidade estrutural.

Auth callback centralizado

O uso de /auth/callback como resolvedor de OAuth está certo.  
Ele evita duplicação de lógica e concentra criação/verificação de perfil.

Área cliente com jornada quase completa

No lado cliente, já existe um funil relativamente coerente:

home → perfil profissional → agendar/chat/favoritar → agendamentos → avaliar

Esse é o pedaço mais “produto” do sistema hoje.

Bottom nav por perfil

A existência de navegação dedicada por role ajuda consistência e continuidade, que são princípios centrais do seu agent.

---

2. Problemas críticos de UX no fluxo

A. Welcome ainda cria bifurcação mal resolvida

Hoje a tela de boas-vindas empurra:

Entrar
    
Criar conta
    
Quero divulgar meus serviços
    

O problema:  
para o usuário novo, isso não separa com clareza suficiente os dois perfis logo no início.

Impacto

Você já percebeu isso na prática: profissional pode cair em cadastro de cliente por distração.

Diagnóstico

O problema não é só visual.  
É de arquitetura da decisão.

Ajuste recomendado

A tela pública precisa deixar explícito, antes do cadastro:

Sou cliente
    
Sou profissional
    

Ou, no mínimo:

“Criar conta como cliente”
    
“Criar conta como profissional”
    

Hoje essa distinção existe, mas não está tratada como decisão principal do fluxo.

---

B. /cliente/busca existe, mas o fluxo real ignora essa rota

No Mermaid você marcou como órfã, e isso está correto.

Impacto

Isso gera 3 sintomas:

rota “fantasma”
    
manutenção desnecessária
    
sensação de feature incompleta
    

Diagnóstico

A busca foi absorvida pela própria home cliente. Então hoje há concorrência entre:

busca embutida na home
    
página dedicada de busca
    

Ajuste recomendado

Escolha uma destas opções:

ou a home é a busca principal e /cliente/busca morre
    
ou /cliente/busca vira a experiência oficial de exploração, e a home só direciona para ela
    

Do jeito atual, está híbrido e confuso.

---

C. Chat existe para os dois lados, mas não é descobrível de forma simétrica

Você já mapeou isso bem:

cliente entra no chat a partir do perfil profissional
    
profissional tem rota de chat, mas não há entrada clara mapeada
    

Impacto

Feature existente sem affordance clara = recurso invisível.

Ajuste recomendado

Se o profissional pode conversar com clientes, isso precisa aparecer a partir de:

pedido recebido
    
agendamento aceito
    
agenda do dia
    

Hoje o fluxo profissional está muito “operacional”, pouco relacional.

---

D. Logout jogando para Welcome é funcional, mas pobre como fluxo

/cliente/perfil e /profissional/perfil acabam servindo como saída da conta e configurações.

Impacto

Não é um erro técnico, mas reforça que perfil virou depósito de funções, não uma página estrategicamente desenhada.

Ajuste recomendado

Perfil deveria ser claramente dividido em:

dados pessoais
    
preferências/conta
    
logout
    
ajuda/termos
    
plano, no caso do profissional
    

---

3. Problemas de produto na jornada do cliente

A. Home cliente está tentando fazer coisa demais

Pelo código, a home concentra:

saudação
    
busca
    
sugestões
    
filtros
    
descoberta de profissionais
    
botão “História das Heroínas”
    

Impacto

Isso pode deixar a home com identidade difusa:  
ela não é só “início”, nem só “busca”, nem só “conteúdo”.

Diagnóstico

Mistura de jobs-to-be-done:

encontrar profissional
    
explorar serviços
    
consumir conteúdo/editorial
    

Ajuste recomendado

Definir o papel principal da home:

encontrar e contratar  
    e tratar “História das Heroínas” como destaque secundário, não como disputa de atenção principal.
    

Seu próprio playbook pede hierarquia visual rígida, simplicidade e remoção do que não ajuda o usuário a agir.

---

B. Falta um fluxo explícito de descoberta progressiva

Hoje o cliente pode:

digitar busca
    
clicar num card
    
entrar no perfil profissional
    

Mas falta um encadeamento mais claro do tipo:

categoria
    
proximidade
    
disponibilidade
    
preço
    
prova social
    

Impacto

A descoberta depende mais de sorte visual do que de arquitetura de decisão.

---

C. Favoritos existe, mas parece secundário demais

O fluxo está correto:

home/perfil → favoritos → perfil
    

Mas falta papel estratégico.

Ajuste recomendado

Favoritos deveria funcionar como:

shortlist de decisão
    
memória de intenção
    
reentrada rápida no funil
    

Hoje parece mais uma página adicionada do que uma etapa forte do processo de conversão.

---

4. Problemas de produto na jornada do profissional

A. Dashboard profissional ainda é painel, não cockpit

Hoje ele mostra:

pendências
    
hoje
    
serviços
    
avaliação
    
solicitações recentes
    

Isso é útil, mas ainda não organiza a operação por prioridade real.

Impacto

O profissional vê números, mas não necessariamente entende:

o que precisa fazer agora
    
o que está travando agenda
    
o que gera mais receita
    

Ajuste recomendado

O dashboard deveria priorizar:

pedidos que exigem ação
    
agenda do dia
    
gargalos de perfil/portfólio
    
performance
    

Hoje ele está mais “resumo” do que “comando”.

---

B. Fluxo profissional tem menos profundidade que o cliente

O profissional hoje gira em torno de:

pedidos
    
agenda
    
portfólio
    
perfil
    

Está correto como estrutura mínima.  
Mas ainda falta sensação de ecossistema operacional.

O que falta como percepção de fluxo

entrada clara para chat
    
retorno fácil de um pedido para conversa
    
conexão entre agenda e ação
    
conexão entre perfil e conversão
    

---

C. Pedidos e agenda estão separados, mas pouco conectados

Tecnicamente faz sentido.  
UXmente, ainda parece compartimentalizado.

Impacto

O profissional pode aceitar no “Pedidos”, mas a continuidade da ação não fica tão evidente dentro de “Agenda”.

Ajuste recomendado

Conectar melhor:

pedido aceito → aparece como próximo compromisso
    
compromisso → ação de conversar/concluir
    
conclusão → gatilho para avaliação/retenção
    

---

5. Problemas de consistência estrutural

A. Mermaid está correto ao marcar órfãs

As órfãs mais relevantes são:

/cliente/busca
    
/profissional/chat/:recipientId
    
/termos-de-uso
    
* / NotFound
    

Diagnóstico por severidade

Alta severidade

/cliente/busca
    
/profissional/chat/:recipientId
    

Porque são rotas de uso potencial, mas sem descoberta forte.

Baixa severidade

/termos-de-uso
    
NotFound
    

Porque são auxiliares por natureza.

---

B. Há fluxo técnico que não aparece como fluxo de UX

Exemplo:

OAuth intent
    
criação automática de perfil
    
fallback para login com erro sem-cadastro
    

Isso está bom tecnicamente, mas a experiência ainda depende demais de estado interno.

Impacto

Se a interface não sinaliza muito bem o que está acontecendo, o usuário sente “comportamento estranho”.

Seu agent pede microcopy que ensine como resolver falhas, e nisso vocês já melhoraram parcialmente no login com o alerta de sem cadastro.

---

6. Gargalos mais importantes, em ordem de prioridade

Prioridade 1 — Resolver a entrada do funil

Maior problema atual: ambiguidade entre cliente e profissional no onboarding público.

Corrigir primeiro

deixar a escolha de perfil impossível de ignorar
    
tornar o CTA de cadastro explicitamente segmentado
    

---

Prioridade 2 — Eliminar ou oficializar rotas órfãs

Especialmente:

/cliente/busca
    
/profissional/chat/:recipientId
    

Corrigir primeiro

ou entram na navegação real
    
ou saem da arquitetura
    

---

Prioridade 3 — Redefinir a home cliente

Ela precisa parar de ser mistura de:

busca
    
feed
    
conteúdo
    
descoberta
    

Corrigir primeiro

uma função principal
    
uma secundária
    
resto subordinado
    

---

Prioridade 4 — Fortalecer o cockpit do profissional

O lado profissional ainda parece mais MVP do que produto completo.

Corrigir primeiro

ações prioritárias
    
comunicação
    
continuidade entre pedidos, agenda e conclusão
    

---

7. Minha leitura do estado do produto hoje

Estado atual

Arquitetura funcional: 8/10  
Clareza de fluxo: 6/10  
Encontrabilidade: 5.5/10  
Consistência entre áreas: 6/10  
Maturidade de UX: 6/10

Resumo honesto

Você já tem:

fundação boa
    
papéis separados
    
funis principais vivos
    
backend/rotas coerentes
    

Mas ainda falta:

poda de ambiguidade
    
fechamento das pontas soltas
    
transformar “rotas existentes” em “experiências claras”
    

---

8. Conclusão objetiva

Seu Mermaid está bem mapeado e representa com boa fidelidade o fluxo atual real do projeto.  
O principal problema não é “estrutura quebrada”.

O principal problema é este:

o sistema já tem várias peças, mas algumas ainda não viraram experiência claramente guiada.

Em UX/UI, isso significa:

menos problema de código
    
mais problema de hierarquia, descoberta e continuidade
    

Pelo seu agent, a direção correta é:

simplificar
    
tornar decisões explícitas
    
reforçar consistência
    
cortar rotas semi-mortas
    
transformar a área profissional em fluxo de ação, não só em páginas soltas
    

No próximo passo, eu posso transformar essa análise em um diagnóstico prático em tópicos “problema → impacto → ajuste” para você colar no Lovable.

# Feedback 02

Analisei o Mermaid contra as rotas reais do projeto e, no geral, seu mapa está bem próximo do fluxo implementado. O principal problema não é “falta de telas”, e sim atrito de decisão, ambiguidades no onboarding e alguns fluxos mal representados ou subaproveitados. Pela sua própria régua de UX, os pontos críticos aqui são: clareza de caminho, consistência, microcopy acionável e redução de fricção.

Veredito geral

O fluxo atual é funcional, mas ainda não está redondo.  
Ele consegue levar usuário e profissional do acesso até áreas logadas, porém há 4 problemas estruturais:

onboarding com decisão sensível cedo demais
    
fluxo público pouco orientado
    
alguns caminhos reais não aparecem ou aparecem incompletos no Mermaid
    
há rotas/telas existentes que enfraquecem a consistência da arquitetura
    

---

O que está certo

1) Estrutura macro faz sentido

Seu fluxo separa corretamente:

entrada
    
autenticação
    
cliente
    
profissional
    
chat compartilhado
    

Isso está alinhado com uma arquitetura compreensível e previsível, o que reforça consistência e confiança.

2) Resolução inicial por sessão/role está correta

O app já entende:

sem sessão → boas-vindas
    
com sessão + cliente → home cliente
    
com sessão + profissional → dashboard profissional
    
com sessão + sem profile → callback
    

Isso é bom porque evita expor tela errada para usuário logado.

3) Cliente e profissional estão bem separados

A separação de áreas evita confusão estrutural.  
Isso é positivo porque cada perfil tem objetivo diferente.

---

Principais problemas

Problema 1 — Escolha de tipo de conta continua sendo um ponto de alto risco

Por que prejudica

Essa é a decisão mais sensível do onboarding e acontece cedo, antes de o usuário entender plenamente a diferença entre os caminhos.  
Se errar aqui, o usuário entra no funil errado e a experiência degrada logo no começo.

O que vejo no fluxo

No Mermaid, isso aparece como:  
Welcome -> /cadastro -> ChooseAccountType -> Signup cliente/profissional

Isso está coerente com o sistema, mas continua sendo um ponto crítico de erro de cadastro.

Prioridade

Alta

---

Problema 2 — O fluxo público ainda é fraco em orientação

Por que prejudica

A Welcome faz basicamente:

Entrar
    
Criar conta
    

Mas o produto depende de uma distinção central entre cliente e profissional.  
Hoje o fluxo público está funcional, porém não prepara bem a decisão seguinte.

Consequência

O usuário só entende a bifurcação de verdade depois que já clicou em criar conta.  
Isso aumenta carga cognitiva e chance de escolha errada. A sua própria referência pede sinalização clara em menos de 2 segundos.

Prioridade

Alta

---

Problema 3 — Seu Mermaid não mostra uma rota real importante: /cliente/busca

Por que prejudica

No código existe a rota:  
/cliente/busca

Mas ela não aparece no fluxo que você colou.

Impacto

Seu mapa atual não representa 100% da arquitetura implementada.  
Isso gera risco de análise errada depois, porque alguém pode achar que a busca só acontece dentro da home do cliente.

Prioridade

Alta

---

Problema 4 — A home do cliente concentra funções demais

Por que prejudica

Na prática, a tela /cliente hoje está fazendo muita coisa ao mesmo tempo:

saudação
    
CTA “História das Heroínas”
    
busca
    
sugestões
    
filtros
    
listagem de profissionais
    

Ou seja: ela virou hub + busca + discovery + conteúdo editorial.

Consequência

A tela pode perder hierarquia visual.  
Quando muita coisa compete pela atenção, o usuário demora mais para entender “qual é a ação principal”. Isso fere diretamente a lei de hierarquia visual e atenção.

Prioridade

Alta

---

Problema 5 — O Mermaid mascara que o chat é mais restrito do que parece

Por que prejudica

No diagrama, o chat parece um fluxo simples:

perfil profissional → chat
    
chat → perfil
    

Mas no produto real, o chat só funciona se houver agendamento entre as partes.

Consequência

No mapa, esse gate de permissão está sub-representado.  
Arquiteturalmente, não é apenas “abrir chat”; é “abrir chat condicionado a vínculo prévio”.

Prioridade

Alta

---

Problema 6 — Fluxo do profissional está subdesenhado

Por que prejudica

No Mermaid, o profissional parece ter só:

pedidos
    
agenda
    
portfólio
    
perfil
    

Mas o perfil profissional, na prática, é bem mais importante do que parece, porque concentra:

edição de dados
    
serviços
    
foto
    
portfólio
    
plano/upgrade
    

Ou seja, a rota /profissional/perfil não é só “perfil”; ela é quase um centro operacional.

Consequência

Seu mapa atual simplifica demais a importância dessa tela.  
Na leitura estratégica, isso esconde onde realmente está o peso do produto para o profissional.

Prioridade

Média/Alta

---

Problema 7 — Fluxo de logout está representado de forma simplificada demais

Por que prejudica

No Mermaid:

S -> C
    
Z -> C
    

Isso sugere “perfil → boas-vindas”.

Mas isso não é um fluxo de navegação comum; isso é uma ação de saída de sessão.  
Misturar logout com navegação normal deixa o mapa menos preciso.

Prioridade

Média

---

Problema 8 — Termos de uso estão conectados só a login no Mermaid

Por que prejudica

No fluxo público, você ligou:  
G -> O

Mas, na lógica de experiência, termos estão muito mais ligados ao cadastro do que ao login.

Consequência

No mapa atual, essa conexão fica semanticamente estranha.  
Parece detalhe, mas detalhe de arquitetura influencia clareza do produto.

Prioridade

Média

---

Problema 9 — Existe duplicação conceitual entre “buscar” e “descobrir”

Por que prejudica

Hoje há:

uma home cliente que já busca/lista profissionais
    
uma rota específica /cliente/busca
    

Isso pode confundir a arquitetura mental do usuário:  
“eu procuro na home ou numa tela dedicada?”

Consequência

Quando duas telas cumprem funções parecidas sem diferença muito clara, a UX perde nitidez.

Prioridade

Média

---

Inconsistências entre Mermaid e projeto real

O Mermaid está faltando

/cliente/busca
    

O Mermaid simplifica demais

a lógica real do AuthCallback
    
o bloqueio do chat por agendamento
    
o peso funcional do perfil profissional
    
o logout como ação distinta
    

O Mermaid acerta

splash
    
welcome
    
login
    
choose account type
    
signup por tipo
    
callback
    
home cliente
    
dashboard profissional
    
bookings
    
favoritos
    
perfil
    
pedidos
    
agenda
    
portfólio
    
chat compartilhado
    

---

Diagnóstico por área

Fluxo público

Estado: funcional, mas com fricção na decisão de tipo de conta.  
Risco principal: usuário cair no caminho errado.

Fluxo cliente

Estado: relativamente rico e utilizável.  
Risco principal: home sobrecarregada e busca com arquitetura ambígua.

Fluxo profissional

Estado: coerente, mas o Mermaid subestima a centralidade da tela de perfil.  
Risco principal: mapa estratégico não refletir onde a operação realmente acontece.

Chat

Estado: funcional com regra de negócio clara.  
Risco principal: o diagrama não explicita a restrição mais importante do recurso.

---

Prioridades reais de UX

Alta

reduzir risco de erro na escolha cliente/profissional
    
explicitar melhor a arquitetura de busca do cliente
    
representar corretamente o gate do chat
    
aliviar a concentração funcional da home cliente
    
incluir /cliente/busca no mapa
    

Média

separar visualmente logout de navegação comum no fluxo
    
reposicionar semanticamente termos de uso no desenho
    
representar melhor o peso da tela de perfil profissional
    

---

Conclusão objetiva

Seu fluxo atual não está ruim.  
Ele já tem base de produto real e separação de papéis coerente. O problema é que ele ainda está mais correto tecnicamente do que claro cognitivamente.

Em UX, isso significa:

a máquina entende
    
mas o usuário ainda pode hesitar
    

E hesitação é exatamente o que você quer remover. Sua própria base de UX aponta isso: sinalização rápida, simplicidade, hierarquia e consistência.

No próximo passo, eu posso te devolver isso em um formato mais cirúrgico:  
“problema → por que prejudica → ajuste recomendado → prioridade”, tela por tela.