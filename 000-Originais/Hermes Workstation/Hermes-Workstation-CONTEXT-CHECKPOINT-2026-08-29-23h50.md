

> **Finalidade:** este arquivo consolida, em um único documento autocontido, o contexto histórico, as decisões arquiteturais, o estado técnico, as validações, as pendências, o método de engenharia e a visão de longo prazo do projeto **Hermes Workstation**.
> Ele foi criado para ser anexado **sozinho** em novos chats, evitando a necessidade de reenviar os diversos exports, JSONs, transcrições e conversas que deram origem ao projeto.
> **Snapshot produzido em:** 29/08/2026, aproximadamente 23h44, horário de Brasília (`America/Sao_Paulo`).
> **Estado do GitHub foi revalidado ao vivo durante a criação deste checkpoint.**

---

# 0. COMO USAR ESTE ARQUIVO EM UM CHAT NOVO

Ao receber este arquivo em um novo chat, o agente deve tratá-lo como **contexto histórico e arquitetural consolidado**, e não como uma ordem automática para retomar uma tarefa antiga.

## 0.1. Regra de precedência

Quando houver divergência entre fontes, use esta ordem:

1. **A mensagem mais recente do usuário no chat atual** — define a tarefa ativa.
2. **Código e estado real do GitHub atual**, especialmente `main`, PRs, workflows e testes.
3. **Documentação canônica do repositório**, especialmente `AGENTS.md` e `workstation/context/*`.
4. **Este checkpoint**.
5. **Conversas, SHAs, prompts, patches, testes e planos históricos** citados neste checkpoint.

Em outras palavras:

> **Este arquivo serve para não precisar reconstruir a história. Ele não substitui a verificação do estado vivo do repositório.**

## 0.2. Antes de modificar o projeto

Se a tarefa envolver código do Hermes Workstation, o agente deve:

1. consultar o `main` atual;
2. verificar PRs abertas relacionadas ao Workstation;
3. verificar os checks/workflows atuais;
4. ler `AGENTS.md`;
5. seguir a ordem obrigatória de `workstation/context/README.md`;
6. inspecionar o código e os testes atuais da área afetada;
7. tratar todo SHA deste arquivo como **checkpoint histórico**, salvo quando confirmado novamente no GitHub.

## 0.3. Não retomar tarefas antigas automaticamente


Se este arquivo disser que, em algum momento, uma PR estava draft, um teste estava falhando ou uma implementação estava pendente, isso **não significa** que o agente deve continuar dali sem verificar o GitHub.

Este próprio checkpoint já contém exemplos de estados que mudaram em poucas horas.

---

# 1. RESUMO EXECUTIVO

O projeto deixou de ser uma tentativa de “adicionar um navegador ao Hermes”.

Ele evoluiu para o **Hermes Workstation**:

> uma distribuição downstream do Hermes Agent em que browser persistente, execução de tarefas, automação web, supervisão humana, Kanban, observabilidade, memória operacional e acesso remoto passam a ser capacidades arquiteturais de primeira classe.

O produto é o próprio fork downstream de `hermes-agent`, e não um plugin solto, um ZIP aplicado por cima ou um aplicativo externo que conversa frouxamente com o Hermes.

A arquitetura atual usa:

- Hermes Desktop;
- Electron;
- Chromium já embutido no Electron;
- `WebContentsView`;
- sessão/profile persistente dedicado;
- um `BrowserRuntime` abstrato;
- um runtime principal interno baseado em Electron Chromium;
- `BrowserTask` como identidade lógica de uma tarefa web;
- controller local autenticado;
- integração com as ferramentas `browser_*`;
- comportamento **fail-closed** depois que uma task é vinculada ao browser interno.

A regra central é:

> **Uma BrowserTask lógica possui no máximo uma página web viva por processo.**

`hide` e `park` não destroem a página. `show` deve reexibir a mesma página enquanto o processo está vivo. `destroy` é explícito. Reinício do Desktop preserva a **identidade lógica e metadata segura**, não o objeto físico `WebContentsView`.

A **Implementation 4 — BrowserTask lifecycle — já foi promovida para `main`**.

O projeto agora está livre para avançar para as fundações seguintes: BrowserSessionState completo, Browser Hub, Chat Browser View, ownership/host transfer, unificação do Preview, linkage com Session/Kanban/run, Execution Journal, relatórios, LAN e, depois, automações de nível mais alto.

---

# 2. IDENTIDADE DO PROJETO

## 2.1. Nome

**Hermes Workstation**

## 2.2. Repositório downstream

```text

kevynlucasprofissional-stack/hermes-agent

```

## 2.3. Relação com o upstream

Conceitualmente:

```text

Hermes upstream

      │

      │ sincronização deliberada

      ▼

fork downstream hermes-agent

      │

      └── Hermes Workstation

```

O objetivo não é divergir do upstream sem necessidade.

O fork deve:

- preservar o máximo possível do Hermes original;
- modificar core somente quando a integração realmente exige;
- manter o delta downstream pequeno;
- documentar esse delta;
- testá-lo;
- facilitar rebase/sincronização futura.

---

# 3. VISÃO DO PRODUTO

A visão não é “um chatbot com browser”.

É mais próxima de:

```text

                    USUÁRIO

                       │

                    objetivo

                       │

                       ▼

                  HERMES

            ORQUESTRADOR OPERACIONAL

                       │

       ┌───────────────┼────────────────┐

       │               │                │

       ▼               ▼                ▼

    AGENTES         WORKFLOWS         MEMORY

       │               │                │

       └───────────────┬┴────────────────┘

                       ▼

                     SKILLS

                       │

       ┌───────────────┼────────────────────┐

       ▼               ▼                    ▼

 WORKSTATION        APIS / MCP           FILESYSTEM

   BROWSER

       │

       ├── Trello

       ├── ChatGPT

       ├── Lovable

       ├── Instagram

       ├── painéis

       ├── sistemas web

       └── outros

```

E, transversalmente:

```text

STATE

LOGGING

VALIDATION

RETRIES

APPROVALS

MODEL ROUTING

RECOVERY

OBSERVABILITY

```

A direção desejada é que uma solicitação complexa possa se transformar em:

```text

Objetivo

  ↓

planejamento

  ↓

Kanban / tarefas

  ↓

BrowserTasks / outras execuções

  ↓

ações observáveis

  ↓

validação

  ↓

aprovação humana quando necessária

  ↓

registro/evidências

  ↓

relatório final

  ↓

novas tarefas descobertas

```

---

# 4. PRINCÍPIO OPERACIONAL DE LONGO PRAZO

Um princípio recorrente em todo o planejamento é:

> **Quanto mais determinístico for o workflow, menos inteligência improvisada será necessária para executá-lo.**

Skills e workflows maduros devem explicitar:

- qual ferramenta usar;
- qual aplicativo abrir;
- onde navegar;
- como identificar o alvo;
- o que clicar/preencher;
- qual dado coletar;
- como interpretar o dado;
- onde salvar;
- como validar;
- o que significa sucesso;
- como detectar falha;
- como tentar recovery;
- quando parar;
- como retomar;
- quais ações exigem aprovação.

Isso permite reservar modelos mais caros e fortes para:

- ambiguidade;
- planejamento;
- investigação;
- mudanças de interface;
- debugging;
- exceções.

E usar modelos menores/mais baratos para rotinas já estabilizadas.

---

# 5. COMO O PROJETO EVOLUIU

Esta seção é importante porque várias recomendações antigas foram posteriormente superadas.

## 5.1. Fase inicial — “qual browser integrar?”

A pergunta original era essencialmente:

> Qual solução de automação web combina melhor com o Hermes?

Foram comparados e estudados, em momentos diferentes:

- `agent-browser`;
- Browser Use;
- BrowserOS / BrowserOS neo;
- Browser4;
- Browser Harness;
- VibeSurf;
- Sabrina;
- Hermes Browser Extension;
- Hermes WebUI;
- browser-memory;
- Lattice;
- BrowserTrace;
- Witness;
- Driftlock;
- outras soluções do ecossistema de browser agents.

### Conclusão antiga, hoje histórica

Em uma fase inicial, a melhor composição parecia:

```text

Hermes

  ├── agent-browser como núcleo

  ├── Browser Use como power mode

  └── BrowserOS como browser pessoal/logado

```

Essa ideia **não é mais a arquitetura principal**.

Ela foi superada pela descoberta de que o Hermes Desktop já traz Electron + Chromium e pode possuir seu próprio navegador de primeira classe.

---

## 5.2. Requisito que mudou o problema

O browser desejado precisava ser:

- visual;
- dedicado ao agente;
- separado do Chrome pessoal;
- persistentemente logado;
- acompanhável em tempo real;
- capaz de continuar trabalhando em background;
- integrado ao próprio Desktop;
- reutilizável por tarefas;
- supervisionável pelo humano;
- futuramente acessível via LAN;
- ligado ao Kanban, sessões, runs e relatórios.

Isso tornou uma simples automação headless insuficiente.

---

## 5.3. Hipótese intermediária — produto externo ao Hermes

Foi considerada uma arquitetura do tipo:

```text

Hermes oficial

+ extensão própria

+ WebUI

+ launcher Workstation

```

Também foi considerada a criação de um repositório separado `hermes-workstation`.

Essa direção foi abandonada como arquitetura principal porque o produto desejado exige mudanças atômicas entre:

- Desktop;
- Gateway;
- tools;
- browser;
- routing;
- sessions;
- UX;
- task lifecycle.

---

## 5.4. Decisão: o fork é o produto

A arquitetura convergiu para:

```text

NousResearch / Hermes upstream

             ↓

downstream fork hermes-agent

             ↓

      Hermes Workstation

```

A pasta `workstation/` funciona como camada explícita da distribuição, mas o Workstation é **first-class** no fork.

---

## 5.5. Grande descoberta técnica — o Chromium já está no Desktop

O Hermes Desktop usa Electron.

Portanto, não é necessário:

- empacotar um segundo Chromium;
- depender do Chrome/Edge;
- usar o profile pessoal do usuário;
- fazer o browser principal viver num processo externo.

A arquitetura passou a usar o Chromium do próprio Electron por meio de `WebContentsView`.

---

# 6. ARQUITETURA CANÔNICA DO BROWSER

## 6.1. Estrutura conceitual

```text

Hermes Desktop

      │

      ├── Chat

      ├── Kanban

      ├── Browser

      │

      │    └── BrowserRuntime

      │           │

      │           └── electron-chromium

      │                  │

      │                  └── WebContentsView

      │

      ├── Skills

      └── demais superfícies

```

## 6.2. Runtime principal

  

```text

electron-chromium

```

  

Ele usa o Chromium integrado ao Electron.

  

## 6.3. Profile persistente

  

No Windows, a decisão histórica adotada foi um profile dedicado equivalente a:

  

```text

%LOCALAPPDATA%\HermesWorkstation\Browser\User Data

```

  

A intenção é preservar:

  

- cookies;

- logins;

- localStorage;

- IndexedDB;

- estado gerenciado pelo Chromium.

  

Sem reutilizar diretamente o profile pessoal do Chrome/Edge.

  

## 6.4. BrowserRuntime permanece abstrato

  

Mesmo com Electron Chromium como runtime principal, `BrowserRuntime` é uma fronteira arquitetural deliberada.

  

O resto do Workstation não deve ser acoplado irreversivelmente ao Electron.

  

Isso preserva a possibilidade futura de runtimes especialistas, desde que não criem estados concorrentes para a mesma BrowserTask.

  

---

  

# 7. BROWSERTASK — A ABSTRAÇÃO CENTRAL

  

## 7.1. O que é

  

`BrowserTask` é a identidade lógica de um trabalho web durável.

  

Conceitualmente, pode carregar ou referenciar:

  

```text

task_id

hermes_session_id

run / agent

tab/page

status

control owner

host visual

visibility

timestamps

evidence

recovery state

lifecycle

```

  

Nem todos esses vínculos estão completamente integrados ainda.

  

## 7.2. Lifecycle

  

O contrato desejado e agora parcialmente promovido inclui:

  

```text

create

navigate

show

hide

focus

park

destroy

recovery

```

  

## 7.3. Invariante fundamental

  

```text

1 BrowserTask lógica

        ↓

no máximo

        ↓

1 página viva por processo

```

  

Nunca criar duas páginas independentes para representar a mesma task.

  

## 7.4. Semântica

  

### `hide`

  

Tira a task de uma visualização.

  

Não destrói:

  

- task;

- profile;

- página;

- sessão.

  

### `park`

  

Retira a página do host visual principal, mantendo-a viva para background.

  

### `show`

  

Reexpõe a página.

  

Enquanto o mesmo processo Electron continua vivo, deve reutilizar a mesma página, estado e URL.

  

### `destroy`

  

É a operação explícita que encerra a página e remove a task correspondente.

  

## 7.5. Primitivos autoritativos dentro do processo

  

A formalização de BrowserTask **não criou um segundo page store**.

  

Continuam autoritativos:

  

- `taskTabs`;

- `BrowserEntry.ownerTaskId`;

- `WebContentsView` existente;

- `WorkstationBrowserRuntime`;

- parking existente;

- attach/detach existente;

- controller/routing existente.

  

BrowserTask formaliza identidade e lifecycle **sobre esses primitivos**.

  

---

  

# 8. PERSISTÊNCIA: PROFILE ≠ BROWSER SESSION STATE

  

Esta separação é canônica.

  

## 8.1. Chromium Profile

  

Responsável por estado do browser:

  

```text

cookies

localStorage

IndexedDB

cache

autenticação compatível

dados do Chromium

```

  

## 8.2. BrowserTask metadata / futuro BrowserSessionState

  

Responsável por estrutura operacional segura, por exemplo:

  

```text

logical tabs

active tab

order

URL/title seguros

BrowserTask linkage

Hermes session linkage

run linkage

status

timestamps

recovery metadata

host metadata

```

  

## 8.3. Segurança

  

Não persistir deliberadamente em estado estrutural próprio:

  

- senhas;

- tokens;

- conteúdo sensível;

- credenciais;

- secrets de páginas.

  

Credenciais pertencem ao mecanismo apropriado do browser/profile, não ao JSON lógico do Workstation.

  

---

  

# 9. RESTART: O QUE SOBREVIVE E O QUE NÃO SOBREVIVE

  

Uma `WebContentsView` é process-local.

  

Portanto, após reiniciar o Hermes Desktop:

  

**não** se afirma que sobrevivem:

  

- o mesmo objeto `WebContentsView`;

- o renderer;

- heap JavaScript;

- identidade física de processo.

  

O que deve sobreviver:

  

```text

BrowserTask lógica

+ metadata estrutural segura

```

  

Fluxo:

  

```text

task existente

   ↓

restart do Desktop

   ↓

metadata restaura como parked/restored

   ↓

nenhuma página de task precisa nascer eager

   ↓

primeiro uso/show

   ↓

cria exatamente uma nova página

   ↓

mesmo task_id lógico

   ↓

recoveryState = recreated

```

  

---

  

# 10. CHAT BROWSER VIEW E BROWSER HUB

  

Decisão arquitetural já tomada, embora a UI completa ainda não esteja implementada:

  

> Chat Browser View e Browser Hub serão duas visualizações da **mesma BrowserTask e do mesmo BrowserRuntime**.

  

Arquitetura:

  

```text

                 BrowserTask

                     │

                página viva

                     │

         ┌───────────┴───────────┐

         │                       │

 Chat Browser View          Browser Hub

    contextual                 global

```

  

Somente **um host por vez** deve possuir o `WebContentsView` vivo.

  

A outra superfície mostra:

  

- estado;

- card;

- thumbnail;

- metadata;

- ação para assumir/abrir.

  

Não deve existir:

  

```text

Chat → Chromium A

Browser Hub → Chromium B

```

  

para a mesma task.

  

---

  

# 11. PREVIEW VS WORKSTATION BROWSER

  

Historicamente, existem duas lanes:

  

1. Preview upstream, com ferramentas como:

   - `open_preview`;

   - `read_preview`;

   - `drive_preview`.

  

2. Workstation Browser, com:

   - `BrowserRuntime`;

   - controller;

   - `browser_*`.

  

No Workstation futuro, isso não deve continuar representando dois browsers independentes para o mesmo trabalho.

  

O objetivo é transformar o Preview, quando apropriado numa sessão Workstation, em:

  

> uma compatibility view/adapter sobre a mesma BrowserTask/runtime.

  

Não sincronizar duas páginas “pela URL”.

  

Não duplicar:

  

- cookies;

- navegação;

- tabs;

- page state.

  

---

  

# 12. CONTROLLER E ROUTING

  

O Workstation possui/prevê um controller local com:

  

- binding de loopback/localhost;

- autenticação por bearer token;

- controle das BrowserTasks;

- integração das ferramentas `browser_*`.

  

A política essencial:

  

## antes do binding

  

Uma requisição ainda não vinculada pode, conforme a configuração, usar fallback.

  

## depois do binding

  

Se a task já foi vinculada ao Workstation Browser:

  

```text

controller indisponível

        ↓

recovery / erro

        ↓

FAIL CLOSED

```

  

Não pode silenciosamente migrar para outro browser com:

  

- outro profile;

- outra autenticação;

- outra página;

- outro estado.

  

---

  

# 13. DECISÕES ARQUITETURAIS CANÔNICAS

  

As decisões abaixo correspondem às decisões formalizadas no repositório.

  

## D-001 — Workstation é first-class

  

O Workstation faz parte do produto downstream.

  

Não é overlay temporário.

  

## D-002 — Preservar Hermes upstream

  

Reutilizar os subsistemas existentes:

  

- Sessions;

- Gateway;

- tool registry/toolsets;

- approvals;

- Memory;

- Kanban;

- profiles;

- browser routing.

  

Não criar control planes paralelos sem necessidade.

  

## D-003 — Browser interno é Electron Chromium

  

Usar `WebContentsView` + sessão persistente dedicada.

  

Não usar profile pessoal do Chrome/Edge.

  

## D-004 — Profile e BrowserSessionState são coisas distintas

  

Nunca misturar credenciais e estado estrutural.

  

## D-005 — Uma BrowserTask possui uma página viva

  

Sem duplicação.

  

`hide/park != destroy`.

  

Restart preserva identidade lógica, não objeto físico.

  

## D-006 — Chat Browser View e Browser Hub compartilham o mesmo runtime

  

Um host vivo por vez.

  

## D-007 — Não criar segundo SessionDB, Kanban ou Memory

  

Esses sistemas já pertencem ao Hermes.

  

## D-008 — Task vinculada é fail-closed

  

Sem fallback silencioso.

  

## D-009 — Capability de surface é session-scoped

  

A existência conceitual da surface Desktop/Browser é propriedade da sessão/plataforma.

  

Ela não deve desaparecer do schema só porque um probe de reachability falhou momentaneamente.

  

Não usar um simples env var global como substituto para identidade da sessão.

  

## D-010 — BrowserRuntime é fronteira de abstração

  

Electron é o runtime principal atual, mas não deve se tornar dependência irreversível de toda a lógica de negócio.

  

## D-011 — `main` é testado como commitado

  

Install/CI não podem “consertar” o código antes de testar e, com isso, esconder integração ausente.

  

---

  

# 14. REGRAS QUE FUNCIONAM COMO UMA CONSTITUIÇÃO

  

Não fazer:

  

```text

❌ segundo SessionDB

❌ segundo Kanban

❌ segunda Memory

❌ segundo agent loop concorrente

❌ segundo page store

❌ segundo browser state para a mesma BrowserTask

❌ segundo Chromium sincronizado por URL para a mesma task

❌ reutilizar profile pessoal Chrome/Edge

❌ fallback silencioso depois do binding

❌ credenciais/tokens em state ou logs

❌ esconder problemas de bounds com z-index

❌ alterar arquitetura por suposição sem reprodução

❌ declarar smoke/manual PASS sem tê-lo executado

❌ tratar SHA histórico como estado atual

```

  

Preservar:

  

```text

✅ Hermes Sessions canônicas

✅ Hermes Kanban canônico

✅ Hermes Memory canônica

✅ BrowserRuntime abstrato

✅ BrowserTask one-live-page

✅ bound task fail-closed

✅ controller local protegido

✅ delta upstream explícito

✅ testes e documentação acompanhando mudanças

✅ journal de hipóteses/evidências

```

  

---

  

# 15. ORDEM DE PRIORIDADE DO PROJETO

  

A ordem histórica formalizada para avaliar trade-offs é:

  

```text

1. confiabilidade

2. integração nativa

3. segurança

4. manutenção

5. UX

6. tokens/performance

7. quantidade de funcionalidades

```

  

“Mais features” não deve vencer uma arquitetura menos confiável.

  

---

  

# 16. ESTADO REAL DO GITHUB NO MOMENTO DESTE CHECKPOINT

  

> **ATENÇÃO:** esta seção é um snapshot. Em um chat futuro, revalidar.

  

## 16.1. `main`

  

No momento da criação deste arquivo:

  

```text

main = 46a6ef9e257b4add01d6eb7f2a95a82bb433ee89

```

  

Commit:

  

```text

docs(workstation): close Implementation 4 promotion state (#10)

```

  

## 16.2. PR #9

  

```text

#9 — feat(workstation): formalize BrowserTask lifecycle

```

  

Estado:

  

```text

MERGED

```

  

Branch histórica:

  

```text

impl4-browser-task-lifecycle

```

  

Accepted head:

  

```text

75d10d35d4757496390debf8e4b4f9efb44c5432

```

  

Merge commit:

  

```text

fada723f43613e5e0f061cab24445573ac298998

```

  

A PR #9 foi a promoção da **Implementation 4**.

  

## 16.3. PR #10

  

```text

#10 — docs(workstation): close Implementation 4 promotion state

```

  

Estado:

  

```text

MERGED

```

  

Foi uma PR **documental**, usada para reconciliar os documentos de estado após a promoção da Implementation 4.

  

Head da PR:

  

```text

90f1d0ce614a113909a56b07b06525f5fbe3336a

```

  

Merge commit / `main` observado:

  

```text

46a6ef9e257b4add01d6eb7f2a95a82bb433ee89

```

  

Não deve ser interpretada como Implementation 5.

  

---

  

# 17. HISTÓRICO DAS IMPLEMENTAÇÕES 1–4

  

## Implementation 1 — Contexto operacional para coding agents

  

Objetivo:

  

- tornar o projeto compreensível por agentes novos;

- aproveitar `AGENTS.md`;

- criar/organizar `workstation/context/`;

- registrar estado, decisões, constraints, testes e known issues;

- impedir dependência de uma conversa específica.

  

Resultado:

  

**concluída**.

  

---

  

## Implementation 2 — `main` como fonte canônica do Workstation

  

Objetivo:

  

- deixar de tratar o Workstation como ZIP/patch externo;

- integrar a distribuição no `main`;

- preservar delta upstream explícito.

  

Resultado:

  

**concluída**.

  

---

  

## Implementation 3 — capability do Workstation Browser no schema/session

  

Problema:

  

A existência da capability de Browser/Desktop não pode depender de um probe global ou cacheado de processo que muda por corrida de inicialização.

  

Princípio:

  

> Surface capability é propriedade da sessão; reachability é outra coisa.

  

Resultado:

  

- Desktop session conhece corretamente sua surface;

- schema capability tornou-se session-scoped;

- cache de definitions considera a capability/surface;

- CLI/TUI não devem receber surface indevida;

- controller health determina execução/recovery, não a existência conceitual da capability.

  

Resultado:

  

**concluída**.

  

Checkpoint histórico de `main` antes da Implementation 4:

  

```text

ce78f120e8ed2974d6174e475cc7572afcfe41e0

```

  

---

  

## Implementation 4 — BrowserTask lifecycle

  

Objetivo:

  

formalizar BrowserTask sobre os primitivos já existentes.

  

Inclui:

  

- create;

- show;

- hide;

- park;

- destroy explícito;

- idempotência;

- recovery controlado;

- metadata segura;

- persistência lógica;

- restart restoration;

- testes focados;

- validação real Electron/Windows.

  

Resultado:

  

**PROMOTED / RESOLVED**.

  

---

  

# 18. EVIDÊNCIA DA IMPLEMENTATION 4

  

A Implementation 4 não foi promovida apenas por mocks.

  

## 18.1. Smoke nativo

  

Ambiente registrado no repositório:

  

```text

Windows release: 10.0.26200

Electron: 40.10.2

Node externo do smoke: v24.14.1

```

  

Probe versionado:

  

```text

workstation/context/engineering-journal/probes/h004-native-browser-task-smoke.mjs

```

  

Resultados:

  

```text

H004_LIVE_DESTROY_PASS

H004_RESTART_PASS

H004_CLASSIFICATION=VALIDATED

```

  

O teste provou em Electron/Chromium real:

  

1. create/show/navigate criou uma página task-owned;

2. hide/show preservou:

   - task id;

   - tab id;

   - `WebContents` dentro do processo;

   - URL;

   - sentinel no renderer;

3. park/show preservou a mesma identidade/página;

4. destroy eliminou a página e task;

5. dois PIDs Electron provaram restart real;

6. restart restaurou task lógica como parked/restored;

7. nenhuma página task-owned foi recriada eager;

8. primeiro show recriou exatamente uma página;

9. o mesmo `taskId` lógico foi preservado;

10. secrets usados pelo smoke não foram gravados no state estrutural.

  

## 18.2. Lição do harness

  

Uma série de timeouts anteriores não era bug do BrowserTask.

  

A investigação mostrou que, naquele ambiente:

  

```text

ESM top-level await app.whenReady()

```

  

travava o harness, enquanto:

  

```text

app.whenReady().then(...)

```

  

chegava ao estado ready.

  

O produto já utilizava a forma não bloqueante.

  

Portanto:

  

> o harness estava errado; o produto não precisava de correção nessa hipótese.

  

Esta é uma lição importante para futuros debugging: **testar o harness antes de culpar o produto**.

  

---

  

# 19. WINDOWS CI E KI-006

  

O workflow Windows amplo continuou vermelho em determinados momentos.

  

Isso não foi simplesmente marcado como “falso negativo”.

  

Foi feita uma comparação controlada:

  

```text

baseline:

ce78f120e8ed2974d6174e475cc7572afcfe41e0

  

candidate controlado:

2ffee2335b6aba071e7b63457a047cd9334d4d92

```

  

Conclusão:

  

```text

WINDOWS_BASELINE_COMPARISON=PASS_WITH_KI-006_RED

```

  

Significa:

  

- nenhuma regressão nova atribuível à Implementation 4 foi encontrada;

- as falhas remanescentes correspondiam a classes existentes no baseline;

- os testes específicos de BrowserTask passaram;

- typecheck relevante passou;

- o vermelho amplo foi preservado como dívida conhecida, não escondido.

  

A dívida KI-006 **não foi convertida artificialmente em verde**.

  

---

  

# 20. O QUE FUNCIONA NO `main` ATUAL DO SNAPSHOT

  

Conforme a documentação canônica após a promoção:

  

- Hermes Workstation integrado ao downstream;

- rota Browser dedicada no Desktop;

- Electron Chromium via `WebContentsView`;

- profile/session persistente;

- navegação manual;

- criação/ativação/fechamento de tabs;

- back/forward/reload;

- pause/resume;

- focus;

- Take Control / Release Control;

- controller localhost-bound;

- bearer auth;

- routing `browser_*` com preferência pelo Workstation;

- fail-closed após binding;

- browser schema capability session-scoped;

- cache de tool definitions consciente de surface;

- separação profile vs state lógico;

- instalação/testes do source commitado;

- BrowserTask first-class;

- lifecycle de create/show/hide/park/destroy;

- create idempotente;

- crash recovery;

- metadata segura versionada;

- persistência atômica;

- logical restart restoration;

- lazy page recreation;

- `taskTabs` + `ownerTaskId` como autoridade da página.

  

---

  

# 21. O QUE AINDA É PARCIAL

  

- BrowserSessionState completo;

- ordenação de tabs manuais;

- active generic tab;

- URL/title estrutural mais completo;

- linkage real com controller/session/run/Kanban;

- host/session/control linkage plenamente operacional;

- recuperação completa dessas ligações após restart;

- Browser route ainda é mais próxima de browser convencional que de Hub.

  

---

  

# 22. O QUE AINDA NÃO ESTÁ IMPLEMENTADO

  

No snapshot deste arquivo:

  

- Browser Hub completo;

- Chat Browser View contextual;

- transferência one-host do mesmo `WebContentsView`;

- Preview compatível sobre a mesma BrowserTask;

- Chat ↔ Browser Hub ↔ Preview host transfer completo;

- E2E completo de bounds/resize/maximize/restore;

- BrowserSessionState completo;

- linkage completo de Session/run/Kanban/controller;

- Kanban automático para solicitações multietapa;

- dependency policy completa;

- Execution Journal do produto com evidências/screenshot seletivo;

- completion reports automáticos no Kanban;

- task rail completo;

- settings LAN completos;

- recuperação completa controller/browser E2E;

- Tailscale;

- procedural web memory;

- perception engine econômica em tokens;

- adaptive/drift governance.

  

---

  

# 23. ROADMAP CANÔNICO APÓS A PROMOÇÃO DA IMPLEMENTATION 4

  

> Esta lista vem do `ROADMAP.md` vivo após a PR #10 e deve ter precedência sobre numerações antigas de Implementations 5–11.

  

## V1 — próximos blocos

  

### 1. BrowserSessionState completo

  

Além da metadata atual de BrowserTask:

  

- tabs lógicas comuns;

- active tab;

- ordering;

- URL/title seguros;

- controller identity;

- session identity;

- run identity;

- Kanban identity;

- recovery policy.

  

### 2. Chat Browser View + Browser Hub

  

Duas superfícies da mesma BrowserTask/runtime.

  

### 3. One-host ownership / viewport

  

Mover um único `WebContentsView` vivo entre Chat e Hub.

  

Validar:

  

- resize;

- maximize;

- restore;

- panes;

- troca de host;

- sem overlap.

  

### 4. Unificar Preview no modo Workstation

  

Preview passa a compatibility adapter/view sobre a mesma BrowserTask/runtime, onde aplicável.

  

### 5. Persistir linkage controller/session/run/Kanban

  

Sem criar segundo SessionDB/Kanban.

  

### 6. Promover solicitações multietapa para Kanban automaticamente

  

### 7. Follow-up task discovery

  

Metadata e parent dependency policy.

  

### 8. Workstation Execution Journal

  

Persistência de execução + screenshots seletivos.

  

### 9. Completion reports

  

Integrar resultados ao:

  

```text

kanban_complete(metadata=...)

```

  

### 10. Browser live task rail

  

Agrupamentos:

  

- active;

- waiting-for-human;

- background;

- recent.

  

Depois também Dashboard/mobile.

  

### 11. LAN settings

  

- toggle;

- auth preflight;

- IP;

- QR.

  

### 12. Popup / SSO / download / upload UX

  

### 13. Recovery E2E

  

```text

crash controller/browser

  ↓

pause

  ↓

reconnect

  ↓

verify

  ↓

resume

```

  

### 14. Windows clean-install + native host-composition E2E

  

---

  

## V1.1

  

- Tailscale;

- compatibilidade opcional com Hermes Browser Extension externa;

- manutenção/cache mais rica;

- download/upload UX mais avançada;

- políticas multi-task/scheduling mais ricas.

  

## V2

  

- procedural web memory:

  ```text

  discover → run → explore → learn

  ```

- perception engine compacta/provenance-aware;

- drift diagnosis;

- governed adaptation;

- Lightpanda para tarefas headless ultraleves.

  

---

  

# 24. NUMERAÇÃO ANTIGA “IMPLEMENTATION 5–11”

  

Nos contextos anteriores à promoção da Implementation 4, havia uma sequência congelada:

  

```text

5  Unificar Preview e Workstation Browser

6  Browser Hub + Chat Browser View

7  Ownership, bounds e composição

8  Browser Session State

9  web_search vs Workstation Browser

10 Session not found

11 prova E2E completa

```

  

Essa sequência é **histórica**.

  

O `ROADMAP.md` vivo após a promoção reordenou os próximos blocos e agora coloca BrowserSessionState como primeiro item do “V1 next”.

  

Portanto:

  

> **Não iniciar automaticamente a antiga “Implementation 5” com base neste checkpoint. Consultar ROADMAP/CURRENT_STATE atuais.**

  

---

  

# 25. WEB_SEARCH VS WORKSTATION BROWSER

  

Mesmo que a antiga numeração tenha mudado, a distinção conceitual continua útil.

  

## `web_search`

  

Usar para:

  

- busca factual;

- informação pública;

- sem necessidade de UI persistente;

- sem necessidade de login/browser state.

  

## Workstation Browser

  

Usar para:

  

- webapps;

- login;

- sessão persistente;

- interação visual;

- formularios;

- interfaces autenticadas;

- navegação longa;

- tarefas que precisam ser retomadas;

- supervisão/takeover humano.

  

Não resolver roteamento apenas por uma lista frágil de keywords.

  

---

  

# 26. “SESSION NOT FOUND”

  

Existe histórico de:

  

- `Session not found`;

- exports com `session: null`.

  

Isso deve permanecer uma trilha causal separada.

  

Não assumir:

  

> “é bug do Browser”.

  

Somente modificar SessionDB/Gateway se houver:

  

```text

reprodução

  ↓

causa

  ↓

linha responsável

  ↓

correção

  ↓

regression test

```

  

---

  

# 27. PAPEL DOS OUTROS PROJETOS ESTUDADOS

  

## BrowserOS neo

  

Hoje é principalmente referência de:

  

- UX;

- navegador dedicado ao agente;

- observabilidade;

- human takeover;

- sessões persistentes;

- replay.

  

Não incorporar código AGPL no downstream MIT sem análise/licenciamento adequado.

  

## agent-browser

  

Permanece útil como:

  

- backend/fallback externo determinístico;

- referência de automação compacta.

  

Não é mais o browser principal do Workstation.

  

## Browser Use / Browser Harness

  

Referência/futuro “Power Mode” para:

  

- fluxos pesados;

- automação semântica avançada;

- técnicas de harness.

  

## browser-use/desktop

  

Referência concreta para:

  

- pooling;

- parking;

- attach/detach;

- lifecycle de `WebContentsView`;

- autenticação/profile.

  

## Browser4

  

Candidato/referência para:

  

- crawl;

- extração pesada.

  

## browser-memory

  

Inspira:

  

- memória procedural web.

  

## Lattice

  

Inspira:

  

- percepção compacta;

- token budgeting;

- provenance-aware perception.

  

## BrowserTrace / Witness

  

Inspiram:

  

- journal;

- replay;

- evidências;

- observabilidade.

  

## Driftlock

  

Inspira:

  

- detecção de drift;

- governança de adaptação.

  

---

  

# 28. DIFERENCIAL DE LONGO PRAZO

  

A visão amadureceu de:

  

> “Hermes com browser persistente”

  

para:

  

> **Hermes com browser persistente + automações que aprendem + memória procedural + percepção eficiente em tokens + execução observável/auditável + recovery governado.**

  

Ou seja:

  

o browser é a fundação.

  

O produto maior é um sistema que acumula capacidade operacional.

  

---

  

# 29. HISTÓRICO DE TESTES BROWSERCLAW / PREVIEW

  

Vários arquivos anexados são registros de experimentos antigos.

  

Eles são importantes como **evidência de por que o Workstation nasceu**, não como arquitetura atual.

  

## 29.1. BrowserClaw

  

Em testes antigos, o agente:

  

- abria ChatGPT no navegador;

- tirava snapshots;

- tentava recuperar contexto;

- navegava por ferramentas;

- às vezes interrompia o fluxo ou se perdia.

  

Esses experimentos demonstraram a fragilidade de depender de uma camada externa pouco integrada ao lifecycle do Hermes.

  

## 29.2. Teste “use exclusivamente Workstation Browser”

  

Em um experimento, foi solicitado explicitamente usar o Workstation Browser, mas o agente usou `open_preview`.

  

Isso evidenciou a confusão entre:

  

- Preview;

- Browser interno;

- disponibilidade de ferramentas;

- surface capability.

  

## 29.3. Teste `browser_navigate` / `browser_snapshot`

  

Em outro experimento, o usuário ordenou:

  

- usar exatamente `browser_navigate`;

- depois `browser_snapshot`;

- não substituir por Preview ou outra ferramenta.

  

Naquele runtime, as ferramentas nativas não apareceram no toolset, e a execução foi interrompida conforme solicitado.

  

Esses testes ajudaram a motivar a Implementation 3:

  

> capability da surface deve ser conhecida pela sessão de forma estável e não desaparecer por probe/cache inadequado.

  

## 29.4. Regra para interpretar esses arquivos

  

Termos como “BrowserClaw” nesses registros são **históricos**.

  

Quando um plano antigo disser “usar BrowserClaw”, no desenho moderno isso normalmente significa:

  

> usar a capacidade de automação web apropriada do Hermes Workstation, salvo se o usuário pedir explicitamente BrowserClaw/BrowserOS externo.

  

---

  

# 30. VISÃO MAIOR: HERMES COMO ORQUESTRADOR DA VIDA DIGITAL

  

Além do desenvolvimento do Workstation em si, os arquivos descrevem um ecossistema de automações futuras.

  

O objetivo maior é transformar o Hermes em:

  

> **orquestrador operacional da vida digital e do trabalho.**

  

Integrações desejadas ao longo do tempo:

  

- arquivos locais;

- Trello;

- Workstation Browser;

- ChatGPT;

- Lovable;

- Telegram;

- Instagram;

- cronjobs;

- agentes especializados;

- bases de conhecimento;

- skills reutilizáveis;

- sistemas administrativos;

- fluxos da ACIRV.

  

---

  

# 31. PLANO HISTÓRICO DE AUTOMAÇÕES

  

A sequência conceitual original foi:

  

## Fase 1 — domínio da automação web

  

Historicamente chamada de BrowserClaw.

  

Objetivo moderno:

  

> Hermes consegue operar aplicações web sem se perder.

  

Capacidades:

  

- navigate;

- identify;

- snapshot/read;

- click;

- fill/type;

- validate;

- detect interface changes;

- retry;

- recovery;

- resume.

  

## Fase 2 — Trello

  

Trello foi considerado laboratório ideal porque é:

  

- útil;

- relativamente simples;

- visual;

- reversível;

- mensurável.

  

Skills/workflows desejados:

  

```text

read-board

create-card

move-card

update-card

prioritize

daily-summary

```

  

## Fase 3 — relatório diário

  

Combinar:

  

- Trello;

- arquivos;

- atividade;

- geração textual.

  

No plano original, havia intenção de gerar relatório diariamente por volta das **18h**.

  

## Fase 4 — ChatGPT + Lovable

  

Hermes como intermediário/orquestrador:

  

```text

objetivo do usuário

   ↓

obter codebase/contexto

   ↓

consultar ChatGPT

   ↓

gerar plano/prompt

   ↓

abrir Lovable

   ↓

implementar

   ↓

validar

   ↓

iterar

```

  

## Fase 5 — ECHO V4

  

Usando:

  

- ingestão;

- pesquisa;

- RAG;

- agentes;

- workflows;

- Telegram;

- browser;

- skills.

  

## Fase 6 — Social Media

  

```text

planejamento

  ↓

criação

  ↓

validação

  ↓

aprovação humana

```

  

## Fase 7 — publicação automática

  

Somente após os blocos anteriores estarem confiáveis.

  

## Fase 8 — ACIRV altamente automatizada

  

Exemplos:

  

- relatório mensal;

- planejamento mensal;

- social media;

- acompanhamento de tarefas;

- outros fluxos recorrentes.

  

---

  

# 32. TRELLO COMO CAMADA OPERACIONAL

  

Objetivos descritos:

  

- ler todos os boards;

- identificar tarefas abertas;

- detectar urgência;

- detectar atraso;

- identificar dependências;

- apontar prioridade;

- reorganizar cards;

- mover status;

- detectar gargalos;

- sugerir mudanças;

- manter fluxos coerentes.

  

No Workstation maior, isso converge com a ideia de que solicitações multietapa devem virar Kanban e gerar tarefas filhas quando novas necessidades forem descobertas.

  

---

  

# 33. ECHO V4 — VISÃO CONSOLIDADA

  

ECHO é um projeto para criar perfis/clones de personalidade/conhecimento.

  

## 33.1. Experiência desejada

  

O usuário fornece:

  

- pessoa-alvo;

- diretório de livros/documentos;

- biografias/autobiografias;

- fontes primárias;

- eventualmente fontes secundárias.

  

O ECHO:

  

1. ingere os materiais;

2. trata materiais fornecidos como fontes primárias;

3. pesquisa lacunas como fontes secundárias;

4. constrói uma base de conhecimento;

5. modela estilo/raciocínio/comunicação;

6. cria o perfil/clone;

7. valida comportamento;

8. idealmente conecta o clone a Telegram.

  

## 33.2. Camadas desejadas

  

Além de conhecimento factual:

  

- tom de voz;

- estilo de escrita;

- estrutura argumentativa;

- forma de apresentar ideias;

- padrões de raciocínio;

- interpretação de problemas;

- forma típica de resolução;

- preferências comunicacionais.

  

Quando apropriado e fundamentado, podem existir metadados auxiliares como:

  

- DISC;

- Eneagrama;

- metaprogramas;

- outros modelos psicométricos.

  

Esses modelos não devem substituir evidência comportamental real.

  

## 33.3. Fluxo conceitual

  

```text

conhecimento

   ↓

raciocínio

   ↓

construção da resposta

   ↓

adaptação ao estilo

   ↓

validação do perfil

```

  

## 33.4. Telegram

  

No cenário ideal, cada clone poderia nascer com um bot próprio no Telegram.

  

Esse processo deve observar segurança de credenciais e jamais registrar tokens em estado/log público.

  

---

  

# 34. CHATGPT + LOVABLE

  

Outro workflow importante do plano:

  

1. Hermes recebe um objetivo;

2. acessa/obtém o projeto atual;

3. fornece objetivo + contexto + codebase a um agente de raciocínio;

4. produz prompt/plano de implementação;

5. abre Lovable;

6. envia o prompt;

7. acompanha as alterações;

8. valida;

9. volta ao agente quando necessário;

10. repete até os critérios serem atendidos.

  

A intenção não é criar um ciclo cego.

  

Precisa existir:

  

```text

objetivo

→ alteração

→ verificação

→ evidência

→ correção

```

  

---

  

# 35. SOCIAL MEDIA AUTOMATIZADO

  

Fluxo desejado:

  

## Planejamento

  

Entrada pode ser:

  

- tema;

- texto;

- evento;

- campanha;

- objetivo.

  

Hermes cria um plano.

  

## Aprovação

  

Antes de publicar, o plano deve ser apresentado ao humano.

  

Depois da aprovação:

  

- salvar planejamento;

- criar schedules/cronjobs;

- registrar datas;

- registrar identidade visual;

- criar instruções reutilizáveis.

  

## Produção

  

Na data:

  

- recuperar objetivo;

- texto;

- identidade visual;

- referências;

- gerar conteúdo.

  

## Validação automática

  

Verificar:

  

- português;

- erros visuais;

- aderência à identidade;

- elementos incorretos;

- briefing.

  

## Aprovação humana

  

Enviar:

  

- imagem;

- legenda.

  

O usuário pode:

  

- aprovar;

- pedir mudanças;

- substituir legenda;

- alterar a peça.

  

A versão explícita do usuário tem precedência.

  

## Publicação

  

Após aprovação final, o agente pode operar a plataforma web e publicar.

  

No desenho moderno, isso deve usar o Workstation Browser ou integração oficial apropriada, não necessariamente o BrowserClaw histórico.

  

---

  

# 36. ACIRV E AUTOMAÇÃO OPERACIONAL

  

A automação da ACIRV aparece como aplicação de alto nível, não como fundação.

  

Possibilidades futuras:

  

- relatórios diários/mensais;

- leitura de Kanban;

- priorização;

- planejamento de conteúdo;

- criação;

- aprovação;

- publicação;

- acompanhamento de campanhas;

- coleta de dados;

- atualização de dashboards;

- criação de tarefas descobertas;

- relatórios de execução.

  

Regra importante:

  

> Não desenvolver cada automação como silo. Primeiro consolidar capacidades fundamentais reutilizáveis.

  

---

  

# 37. ESTRATÉGIA MULTIAGENTE PARA DESENVOLVIMENTO

  

O projeto passou a ser desenvolvido com múltiplos agentes em paralelo.

  

Papéis consolidados:

  

## ChatGPT — Conductor / Chief Architect / Integration Engineer

  

Responsável por:

  

- visão global;

- reconstruir estado atual;

- inspecionar GitHub;

- definir Work Packets;

- proteger invariantes;

- revisar trabalhos conjuntamente;

- decidir integração/promoção;

- impedir sobreposição de escopo;

- atualizar o plano conforme evidência.

  

## Codex — Principal Engineer

  

Preferência de uso:

  

- implementação difícil;

- core;

- refactors arquiteturais;

- correções que exigem compreensão ampla de código.

  

Começar por investigação quando não houver bug comprovado.

  

## OpenCode — Verification & Systems Engineer

  

Preferência de uso:

  

- CI;

- testes;

- diagnóstico;

- workflows;

- baseline comparison;

- investigação de regressão;

- tarefas mecânicas/repetitivas.

  

## Antigravity — E2E / Desktop / Product Validation Engineer

  

Preferência de uso:

  

- Windows real;

- Electron;

- UX;

- E2E;

- smoke;

- comportamento visual;

- validação do produto executável.

  

Pode também ser usado para implementação quando necessário, mas seu papel diferencial é ter acesso ao ambiente Desktop/Windows.

  

---

  

# 38. FLUXO MULTIAGENTE RECOMENDADO

  

```text

CHATGPT / CONDUCTOR

   ↓

verifica estado real

   ↓

define work packets independentes

   ↓

┌──────────────┬──────────────┬──────────────┐

│              │              │              │

▼              ▼              ▼              ▼

Codex        OpenCode      Antigravity   outros

core         verify/CI     Windows/E2E

│              │              │

└──────────────┴──────────────┘

               ↓

 branches / commits / PRs / evidências

               ↓

         CONDUCTOR REVIEW

               ↓

      ┌────────┼────────┐

      ▼        ▼        ▼

   integrar  corrigir  rejeitar

               ↓

        acceptance gate

               ↓

             main

```

  

---

  

# 39. LIÇÃO DE GOVERNANÇA DA RODADA DA PR #9

  

Na primeira grande rodada multiagente, a estratégia desejada era:

  

- cada writer trabalhar em branch própria;

- sub-PR apontar para milestone branch;

- Conductor revisar;

- somente depois entrar na PR principal.

  

Na prática, algumas mudanças foram colocadas diretamente na milestone branch.

  

Isso reduziu a fronteira:

  

```text

worker

→ sub-PR

→ integration review

→ milestone

```

  

A lição para próximas rodadas:

  

> **Não colocar vários agentes escrevendo diretamente na mesma branch crítica.**

  

Preferir:

  

- worktrees isolados;

- branches isoladas;

- ownership explícito;

- arquivos “do not modify” por worker;

- PRs pequenas;

- integração pelo Conductor.

  

Verificadores podem operar sem escrever.

  

---

  

# 40. WORK PACKETS — REGRA

  

Cada trabalho paralelo deve declarar:

  

- papel;

- base SHA/branch;

- missão;

- allowed scope;

- forbidden scope;

- invariantes;

- critérios de aceitação;

- testes mínimos;

- formato de entrega;

- se pode ou não commit/push;

- branch/PR alvo.

  

Isso evita agentes “ajudarem” em áreas que não lhes pertencem.

  

---

  

# 41. MODELOS DE IA — NÃO CONGELAR EM CHECKPOINT

  

Em uma rodada de 29/08/2026, a recomendação para Codex foi usar um modelo forte da família GPT-5.6 com esforço alto/xhigh e escalar para max apenas em problemas arquiteturais/debugging extremos.

  

Também havia disponibilidade mencionada de:

  

- Claude Opus 4.6 no Antigravity;

- GPT-OSS 120B no Antigravity;

- OpenCode com grande disponibilidade.

  

Essas informações são **operacionais e datadas**.

  

Em chats futuros:

  

> consultar quais modelos e níveis de esforço realmente existem naquele momento.

  

Não tratar esta seção como configuração permanente.

  

---

  

# 42. MÉTODO DE ENGENHARIA

  

Para cada implementação:

  

1. inspecionar `main`;

2. ler contexto canônico;

3. reproduzir/demonstrar a lacuna;

4. identificar owner real do estado/capability;

5. formular hipótese;

6. tentar refutá-la;

7. implementar a menor solução arquitetural completa;

8. executar teste focado;

9. corrigir em loop;

10. executar regressões;

11. executar gates relevantes;

12. comparar com baseline quando necessário;

13. registrar evidência;

14. atualizar docs;

15. atualizar `UPSTREAM_DELTA.md` quando aplicável;

16. fazer commit coerente;

17. somente então avançar.

  

Não transformar:

  

```text

“isso parece a causa”

```

  

em:

  

```text

“vou alterar o core”

```

  

sem reprodução.

  

---

  

# 43. JOURNAL DE ENGENHARIA

  

O repositório passou a exigir um journal operacional contínuo:

  

```text

workstation/context/engineering-journal/CURRENT.md

```

  

Antes de um novo experimento:

  

- registrar hipótese;

- registrar experimento;

- registrar o que confirmaria;

- registrar o que refutaria.

  

Depois:

  

- registrar resultado exato;

- classificar;

- atualizar a hipótese.

  

Não repetir experimento falho sem mudança material de premissa/ambiente.

  

As verdades estabilizadas devem sair do journal e ir para documentos canônicos.

  

---

  

# 44. ORDEM OBRIGATÓRIA DE LEITURA PARA CODING AGENTS

  

Conforme `workstation/context/README.md` no snapshot:

  

1. `AGENTS.md`

2. `workstation/context/CURRENT_STATE.md`

3. `workstation/context/DECISIONS.md`

4. `workstation/context/CONSTRAINTS.md`

5. `workstation/ARCHITECTURE.md`

6. `workstation/UPSTREAM.md`

7. `workstation/UPSTREAM_DELTA.md`

8. `workstation/SOURCE_MATRIX.md`

9. `workstation/ROADMAP.md`

10. `workstation/context/TESTING.md`

11. `workstation/context/KNOWN_ISSUES.md`

12. `workstation/context/engineering-journal/CURRENT.md`

13. `workstation/PATCH_MANIFEST.md` quando tocar integração upstream/rebase/patch surface.

  

Depois:

  

> inspecionar a implementação e testes atuais.

  

---

  

# 45. PERGUNTAS QUE UM AGENTE DEVE SABER RESPONDER ANTES DE EDITAR

  

- Quem é o owner canônico desse estado?

- Já existe uma abstração Hermes que deve ser estendida?

- Estou criando uma segunda fonte de verdade?

- Este estado é:

  - process-scoped?

  - session-scoped?

  - BrowserTask-scoped?

  - profile-scoped?

- Qual delta upstream será criado?

- Qual teste prova comportamento real?

- Qual boundary de segurança muda?

- Estou adiantando uma implementação futura dentro da atual?

- Estou baseando a mudança em evidência ou em suposição?

  

---

  

# 46. TESTES E EVIDÊNCIAS

  

Tipos de evidência usados no projeto:

  

- unit/domain tests;

- runtime adapter tests;

- Desktop typecheck;

- UI tests;

- Electron/platform tests;

- Python regressions;

- Workstation CI;

- Docker;

- Windows workflow;

- smoke Electron real;

- baseline comparison;

- checkout clean;

- contributor/process gates.

  

Regra:

  

> Um teste focado verde não transforma um broad gate vermelho em verde.

  

E:

  

> um broad gate vermelho não prova regressão sem comparação causal com baseline.

  

---

  

# 47. BASELINE COMPARISON — PADRÃO

  

Quando houver falha de CI possivelmente preexistente:

  

Classificações úteis:

  

```text

IDENTICAL_BASELINE_FAILURE

BASELINE_VARIANT_SAME_CAUSE

NEW_CANDIDATE_FAILURE

BASELINE_ONLY_FAILURE

ENVIRONMENT_OR_HARNESS

INCONCLUSIVE

```

  

Nunca concluir equivalência apenas porque:

  

- falham no Windows;

- têm mesma contagem;

- parecem similares.

  

Comparar teste por teste e causa por causa.

  

---

  

# 48. SOURCE OF TRUTH VS CHECKPOINT

  

Um dos erros que este arquivo quer evitar é congelar um snapshot.

  

Exemplo real:

  

Em um arquivo anterior:

  

```text

main = ce78f120...

PR #9 = draft

Implementation 4 = não promovida

```

  

Pouco depois:

  

```text

PR #9 = merged

Implementation 4 = promoted

PR #10 = merged

main = 46a6ef9e...

```

  

Portanto:

  

> **SHAs neste checkpoint são ótimos para reconstruir história, não para assumir estado presente.**

  

---

  

# 49. SHAs IMPORTANTES — HISTÓRICO

  

| Papel histórico | SHA |

|---|---|

| `main` após Implementation 3 | `ce78f120e8ed2974d6174e475cc7572afcfe41e0` |

| head antigo da PR #9 | `b13aadcb105bff20817199fd52bf806cf6d46360` |

| código BrowserTask estabilizado em rodada intermediária | `1ac0e0a9ecaaf1c53ee0f8abfc3d8a1d802cae70` |

| candidate usado em baseline Windows controlado | `2ffee2335b6aba071e7b63457a047cd9334d4d92` |

| accepted final head da PR #9 | `75d10d35d4757496390debf8e4b4f9efb44c5432` |

| merge da Implementation 4 | `fada723f43613e5e0f061cab24445573ac298998` |

| head da PR documental #10 | `90f1d0ce614a113909a56b07b06525f5fbe3336a` |

| `main` no snapshot final deste checkpoint | `46a6ef9e257b4add01d6eb7f2a95a82bb433ee89` |

  

Outros SHAs de probes/validações podem existir no journal.

  

---

  

# 50. SEGURANÇA

  

Princípios já adotados ou desejados:

  

- controller local/loopback;

- bearer token;

- arquivo de controle privado;

- approvals para ações sensíveis;

- não colocar secrets em logs;

- não serializar credenciais no BrowserTask state;

- profile separado;

- não usar Chrome pessoal;

- fail-closed após binding;

- não vazar capability Desktop para sessões incompatíveis;

- LAN somente com autenticação/preflight apropriados;

- ações irreversíveis devem respeitar política de confirmação.

  

---

  

# 51. HUMAN TAKEOVER

  

`Take Control` e `Release Control` devem operar sobre a **mesma página**.

  

Objetivo:

  

```text

agente trabalha

   ↓

usuário assume

   ↓

mesmo BrowserTask

mesma página

mesma sessão

   ↓

usuário devolve

   ↓

agente continua

```

  

Não criar uma “cópia humana” e uma “cópia do agente”.

  

---

  

# 52. BACKGROUND EXECUTION

  

Uma das motivações do Workstation é permitir que o browser continue trabalhando mesmo sem ser a surface visível.

  

Isso exige:

  

- parking;

- attach/detach;

- lifecycle separado de visibility;

- controle que não dependa exclusivamente de foco da janela;

- host ownership explícito.

  

Historicamente, CDP foi adotado/estudado para evitar dependência de input que exige janela focada.

  

---

  

# 53. POPUPS, SSO, DOWNLOADS E UPLOADS

  

São capacidades desejadas, mas ainda há trabalho de UX/robustez.

  

Princípio:

  

- popup gerado dentro de uma task deve continuar associado àquela task;

- não perder ownership;

- fluxos SSO devem respeitar a mesma sessão/profile;

- downloads/uploads precisam de UX observável e segura.

  

---

  

# 54. LAN E MULTIDISPOSITIVO

  

Visão:

  

O usuário deve poder ativar LAN dentro do próprio Hermes/Workstation e acessar o sistema por:

  

- outro computador;

- celular;

- rede local.

  

Roadmap inclui:

  

- toggle;

- auth preflight;

- IP;

- QR.

  

V1.1 considera Tailscale.

  

Essa superfície não deve expor o controller/browser de maneira insegura.

  

---

  

# 55. KANBAN COMO EXECUTION PLANE

  

A visão do produto é que solicitações maiores possam virar cards/tarefas.

  

Exemplo:

  

```text

“Faça X”

   ↓

Hermes percebe que é multietapa

   ↓

cria card

   ↓

executa BrowserTask

   ↓

descobre Y

   ↓

cria card filho/dependência

   ↓

continua X

   ↓

fecha X com metadata/evidências

```

  

O Kanban existente do Hermes deve ser reutilizado.

  

Não criar um “Workstation Kanban” separado.

  

---

  

# 56. EXECUTION JOURNAL DO PRODUTO

  

Além do engineering journal de desenvolvimento, a visão V1 inclui journal da execução das próprias automações.

  

Possível registro:

  

```text

intent

→ action

→ target

→ observation/diff

→ screenshot opcional

→ result

→ retry/recovery

→ completion

```

  

Objetivos:

  

- auditabilidade;

- debugging;

- relatórios;

- replay;

- aprendizagem procedural.

  

---

  

# 57. MEMÓRIA PROCEDURAL FUTURA

  

O objetivo de V2 é que o Hermes não precise redescobrir a mesma aplicação sempre.

  

Ciclo conceitual:

  

```text

discover

  ↓

run

  ↓

explore

  ↓

learn

  ↓

procedural memory

  ↓

próxima execução melhor

```

  

Isso deve ser governado para evitar que uma automação “aprenda” um comportamento errado e passe a propagá-lo.

  

---

  

# 58. PERCEPÇÃO ECONÔMICA EM TOKENS

  

Outra direção futura:

  

- não despejar DOM/snapshot enorme a cada passo;

- selecionar evidência relevante;

- usar diffs;

- preservar provenance;

- adaptar granularidade;

- escalar para visão/snapshot rico quando necessário.

  

Lattice e projetos semelhantes foram estudados como inspiração.

  

---

  

# 59. O QUE NÃO FAZER AGORA POR ENTUSIASMO

  

Evitar:

  

- implementar V2 antes de fechar fundações V1;

- adicionar vários runtimes antes do estado central estar correto;

- integrar todo projeto open source estudado;

- copiar código de licença incompatível;

- criar WebUI paralela que vire segunda fonte de estado;

- transformar referências em dependências sem necessidade;

- sobre-engenheirar antes de uma lacuna real;

- iniciar vários agentes na mesma área sem ownership.

  

---

  

# 60. O QUE É “UPSTREAM” NESTE PROJETO

  

`upstream` é a origem principal da qual o fork deriva.

  

Conceitualmente:

  

```text

upstream = projeto Hermes original

downstream = fork personalizado Hermes Workstation

```

  

O objetivo é conseguir:

  

- acompanhar melhorias upstream;

- absorver correções;

- reduzir conflitos;

- saber exatamente quais mudanças pertencem ao Workstation.

  

Daí a importância de:

  

- `UPSTREAM.md`;

- `UPSTREAM_DELTA.md`;

- `PATCH_MANIFEST.md`;

- alterações pequenas e documentadas.

  

---

  

# 61. GLOSSÁRIO

  

## BrowserRuntime

  

Abstração que representa o runtime de browser usado pelo Workstation.

  

## electron-chromium

  

Runtime principal atual, baseado no Chromium integrado ao Electron.

  

## WebContentsView

  

Primitive Electron usada para hospedar/renderizar a página dentro do Desktop.

  

## BrowserTask

  

Identidade lógica de uma tarefa de browser.

  

## taskTabs / ownerTaskId

  

Primitivos autoritativos da relação task → página viva dentro do processo Electron.

  

## park

  

Manter página viva sem ocupar o host visual principal.

  

## hide

  

Ocultar a task sem destruí-la.

  

## destroy

  

Encerrar explicitamente task/página.

  

## fail-closed

  

Depois de um binding, uma falha do runtime esperado produz erro/recovery, em vez de migrar silenciosamente para outro runtime.

  

## BrowserSessionState

  

Estado estrutural seguro do workspace de browser. Não é o profile Chromium.

  

## Chromium Profile

  

Dados gerenciados pelo Chromium, como cookies/localStorage/IndexedDB.

  

## Browser Hub

  

Futura visão global das BrowserTasks.

  

## Chat Browser View

  

Futura visão contextual da BrowserTask associada ao chat/trabalho atual.

  

## Workstation Controller

  

Ponte local que permite às tools do agente operar o browser interno.

  

## KI-006

  

Classe conhecida de dívida/falhas amplas de testes Windows/portabilidade preexistentes, preservada em vez de escondida.

  

## Engineering Journal

  

Registro de hipóteses, experimentos, resultados e decisões do desenvolvimento.

  

---

  

# 62. PROTOCOLO PARA RETOMAR O PROJETO EM OUTRO CHAT

  

Cole/anexe somente este arquivo e diga a tarefa desejada.

  

O agente deve fazer:

  

## Etapa 1 — Context restore

  

Ler este checkpoint.

  

## Etapa 2 — Live verification

  

Consultar:

  

```text

repository

main SHA

open PRs

recent merged PRs

workflow/check status

```

  

## Etapa 3 — Canonical context

  

Ler a ordem atual de:

  

```text

AGENTS.md

workstation/context/README.md

```

  

## Etapa 4 — Reconcile

  

Produzir mentalmente:

  

```text

checkpoint history

vs

repo current truth

```

  

Se mudou:

  

> estado vivo vence.

  

## Etapa 5 — Execute current task

  

Não repetir investigações já resolvidas, salvo se premissas mudaram.

  

---

  

# 63. PROMPT CURTO PARA USAR JUNTO COM ESTE ARQUIVO

  

Você pode anexar este arquivo em um novo chat e escrever algo como:

  

> Leia integralmente o arquivo de checkpoint anexado. Ele contém o histórico e a arquitetura consolidada do Hermes Workstation. Antes de tomar decisões sobre código, verifique o estado real atual do repositório `kevynlucasprofissional-stack/hermes-agent`, leia `AGENTS.md` e siga a ordem de `workstation/context/README.md`. Código/GitHub atual são a fonte de verdade; SHAs e estados do checkpoint são históricos até serem reconfirmados. Depois disso, execute a tarefa que eu passar nesta conversa sem retomar automaticamente tarefas antigas.

  

---

  

# 64. PROMPT PARA O CONDUCTOR EM UMA NOVA RODADA MULTIAGENTE

  

> Assuma o papel de Conductor / Chief Architect / Integration Engineer do Hermes Workstation.

>

> Use o checkpoint anexado apenas para reconstruir histórico, decisões e visão.

>

> Repositório:

>

> `kevynlucasprofissional-stack/hermes-agent`

>

> Antes de distribuir trabalho:

>

> 1. consulte `main`;

> 2. consulte PRs abertas;

> 3. consulte workflows;

> 4. leia `AGENTS.md`;

> 5. siga `workstation/context/README.md`;

> 6. leia `CURRENT_STATE`, `ROADMAP`, `DECISIONS`, `CONSTRAINTS`, `TESTING`, `KNOWN_ISSUES` e engineering journal;

> 7. inspecione o código real do subsystem atual;

> 8. trate todo SHA deste checkpoint apenas como histórico.

>

> Depois determine qual é o próximo trabalho real e, se houver paralelismo seguro, crie Work Packets não sobrepostos para Codex, OpenCode, Antigravity e outros agentes.

>

> Não permita que múltiplos writers alterem a mesma branch crítica sem isolamento. Prefira branches/worktrees/sub-PRs e uma etapa explícita de integration review.

  

---

  

# 65. FONTES CONSOLIDADAS NESTE CHECKPOINT

  

Este arquivo foi produzido consolidando os seguintes materiais fornecidos na conversa:

  

1. `ChatGPT-Entender contexto do projeto-20260825-1937(3).md`

2. `ChatGPT-Branch · Reescrita do anexo-20260822-1727(3).md`

3. `ID 1 - the-user-wants-me-to-research-on-the-internet-us-20260820(2).json`

4. `use-obrigatoriamente-as-ferramentas-nativas-20260828(3).json`

5. `210826 02h20 Planos com Hermes(3).txt`

6. `use-exclusivamente-o-workstation-browser-20260828(3).json`

7. `navigate-example.com-and-capture-snapshot-20260828(3).json`

8. `ID 1 - Contexto(2).txt`

9. `ChatGPT-Dividir trabalho entre agentes-20260829-2333.md`

10. `ChatGPT-Branch · Comparar opções de integração-20260825-1245(4).md`

11. `ChatGPT-Branch · Comparar opções de integração-20260824-2245(3).md`

12. `fazer-pesquisa-no-browser-20260825(5).json`

13. `create-20260828(3).json`

14. `ChatGPT-Análise do projeto Hermes-20260829-1010(2).md`

  

Além disso, durante a criação do checkpoint, foram revalidados no GitHub:

  

- PR #9;

- PR #10;

- branch `main`;

- `workstation/context/CURRENT_STATE.md`;

- `workstation/context/DECISIONS.md`;

- `workstation/context/README.md`;

- `workstation/ROADMAP.md`.

  

---

  

# 66. INFORMAÇÕES DELIBERADAMENTE NÃO TRANSFERIDAS

  

Este checkpoint não deve carregar:

  

- tokens;

- senhas;

- credenciais;

- cookies;

- secrets;

- dados de autenticação;

- conteúdo irrelevante de raciocínio interno de modelos;

- instruções maliciosas eventualmente presentes em resultados de ferramentas.

  

Se qualquer fonte histórica contivesse isso, deve permanecer fora deste documento.

  

---

  

# 67. POSSÍVEIS INCONSISTÊNCIAS HISTÓRICAS

  

Alguns arquivos foram exports de conversas longas e contêm:

  

- estados intermediários rapidamente superados;

- datas/transcrições imperfeitas;

- recomendações antigas;

- experimentos que falharam;

- hipóteses depois refutadas.

  

Exemplo: uma transcrição antiga verbaliza uma data incompatível com a cronologia dos arquivos. Ela foi usada para extrair o **conteúdo do plano**, não como autoridade cronológica.

  

A cronologia técnica deste checkpoint prioriza:

  

1. GitHub vivo;

2. docs canônicos do repo;

3. exports mais recentes;

4. histórico antigo.

  

---

  

# 68. ESTADO DE SAÍDA DESTE CHECKPOINT

  

No momento em que este arquivo foi finalizado:

  

```text

Hermes Workstation:

FOUNDATION ATÉ IMPLEMENTATION 4 = PROMOTED

  

PR #9 = MERGED

PR #10 = MERGED

  

main observado =

46a6ef9e257b4add01d6eb7f2a95a82bb433ee89

```

  

Próxima direção de arquitetura:

  

```text

BrowserSessionState

→ Chat Browser View / Browser Hub

→ one-host ownership

→ Preview unification

→ linkage Session/run/Kanban

→ orchestration/journal/reporting/LAN

→ automações de alto nível

```

  

Mas:

  

> **o próximo chat deve sempre verificar o GitHub antes de assumir que este continua sendo o estado atual.**

  

---

  

# 69. FRASE-SÍNTESE

  

Se for necessário reduzir todo o projeto a uma única ideia:

  

> **Hermes Workstation é a transformação do Hermes de um agente que chama ferramentas em uma workstation agentic persistente, na qual tarefas possuem estado, browser próprio, supervisão humana, evidências, recovery e, futuramente, memória procedural — tudo integrado aos subsistemas canônicos do Hermes em vez de construído como um conjunto de automações paralelas e desconectadas.**

  

---

  

# FIM DO CHECKPOINT