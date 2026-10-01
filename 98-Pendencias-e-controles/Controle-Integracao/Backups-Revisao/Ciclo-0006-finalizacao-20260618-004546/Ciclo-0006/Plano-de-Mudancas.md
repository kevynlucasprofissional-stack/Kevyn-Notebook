# Plano de Mudancas - Ciclo 0006

## Escopo

Lote `SRC-000043` a `SRC-000050` — "Outras notas criadas por Kevyn" com conteudo diverso: roteiro de campanha para cliente (Moabe), SQL/pgvector, nota de livro, Kanban de producao, lista de tarefas pessoais e framework AI First.

## Decisoes do lote

- `SRC-000043`: roteiro de video para cliente Moabe. Extrair como evidencia de producao de copy/campanha, nao como conteudo de saude.
- `SRC-000044`, `SRC-000045`, `SRC-000047`: codigo SQL/pgvector. Evidencia de implementacao pratica de RAG, nao criar tutorial.
- `SRC-000046`: nota curta de livro Hormozi. Registrar como estudo, sem expansao.
- `SRC-000048`: Kanban de producao "21 dias com Kevyn". Evidencia de organizacao de conteudo, sem copiar cartoes em massa.
- `SRC-000049`: lista de tarefas pessoais. Tratar como evidencia de autorregulacao e compromissos; diferenciar tarefa datada de traco permanente.
- `SRC-000050`: framework AI First. Atualizar notas de IA e automacao com o metodo e projetos citados.

## Unidades

### UNI-000020 — Roteiro de campanha para Moabe/Barbara
- Fontes: `SRC-000043`
- Destinos: `Marketing comunicacao e processos`, `Portfolio de projetos`
- Operacao: ampliar notas existentes
- Justificativa: o arquivo mostra producao de roteiro de video para campanha "Para cuidar, se cuide" no nicho de emagrecimento, evidenciando cpacidade de copywriting e conteudo para cliente.
- Risco: nao confundir afirmacoes nutricionais com fatos sobre Kevyn ou recomendacoes do vault.

### UNI-000021 — Implementacao pratica de pgvector/RAG
- Fontes: `SRC-000044`, `SRC-000045`, `SRC-000047`
- Destinos: `Inteligencia artificial e automacao`, `Tecnologia IA e automacao`
- Operacao: ampliar notas existentes
- Justificativa: tres arquivos com SQL de PostgreSQL + pgvector para tabelas (esbelta, documents, hormozi) demonstram familiaridade pratica com bancos vetoriais, embeddings e busca semantica.
- Risco: nao criar tutorial; extrair apenas a evidencia de competencia tecnica.

### UNI-000022 — Estudo de modelo de negocios Hormozi
- Fontes: `SRC-000046`
- Destinos: `Negocios e marketing`
- Operacao: ampliar nota existente
- Justificativa: nota curta identificando o livro "$100 Million Money Models" de Alex Hormozi como fonte de estudo.
- Risco: baixo; apenas registrar repertorio.

### UNI-000023 — Workflow de producao de conteudo
- Fontes: `SRC-000048`
- Destinos: `Marketing comunicacao e processos`, `Metodo de estudo e producao`
- Operacao: ampliar notas existentes
- Justificativa: Kanban "21 dias com Kevyn" com pipeline de 7 etapas (Base, Brainstorming, Roteiro, Revisao, Gravacao, Edicao, Postado) documenta metodo de producao de conteudo.
- Risco: nao copiar cartoes individuais; extrair apenas o padrao de organizacao.

### UNI-000024 — Autorregulacao e compromissos
- Fontes: `SRC-000049`
- Destinos: `Execucao sob pressao externa`
- Operacao: ampliar nota existente
- Justificativa: lista de tarefas com compromisso de reparar erro na Capital Green, estabelecer limites com Karol, e entregar resultados profissionais. Evidencia de autorregulacao e responsabilizacao.
- Risco: alto — conteudo sensivel. Nao generalizar tarefa datada como traco permanente. Nao expor detalhes especificos desnecessarios.

### UNI-000025 — Framework AI First
- Fontes: `SRC-000050`
- Destinos: `Inteligencia artificial e automacao`, `Tecnologia IA e automacao`
- Operacao: ampliar notas existentes
- Justificativa: documento com mentalidade AI First, 5 pilares metodologicos e projetos concretos para Salus/Svelte (CRM inteligente, clones de IA, automacao de criativos, etc.).
- Risco: medio; nao confirmar implementacao dos projetos sem fontes posteriores.

## Mudancas previstas

| ID | Operacao | Nota | Unidades |
|---|---|---|---|
| MUD-000034 | modificar | Marketing comunicacao e processos | UNI-000020; UNI-000023 |
| MUD-000035 | modificar | Portfolio de projetos | UNI-000020 |
| MUD-000036 | modificar | Inteligencia artificial e automacao | UNI-000021; UNI-000025 |
| MUD-000037 | modificar | Tecnologia IA e automacao | UNI-000021; UNI-000025 |
| MUD-000038 | modificar | Negocios e marketing | UNI-000022 |
| MUD-000039 | modificar | Metodo de estudo e producao | UNI-000023 |
| MUD-000040 | modificar | Execucao sob pressao externa | UNI-000024 |

Nenhuma nota nova sera criada neste ciclo.
Nenhuma fonte agregada sera criada (materiais sao notas proprias de Kevyn, ja suficientemente pequenas).

## Mudancas fora do escopo

- Nao criar conteudo tutorial sobre pgvector, SQL ou embeddings.
- Nao copiar roteiro integral do video da Moabe.
- Nao copiar cartoes do Kanban individualmente.
- Nao reproduzir lista de tarefas como diagnostico de personalidade.
- Nao confirmar implementacao dos projetos AI First.
- Nao alterar `Dados Kevyn`.
