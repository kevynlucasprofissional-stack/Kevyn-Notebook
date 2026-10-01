---
Resumo: Setup técnico para armazenamento de vetores de embedding em SQL.
Contexto: Arquivo 0510251937.md e 0610251433.md
tags:
  - "#engenharia-de-dados"
  - "#sql"
  - "#rag"
  - "#ia"
ID único: 20251123021022-6vtxhr
created: 2025-11-23
---
# Configuração pgvector (PostgreSQL)

## Conceito
Para habilitar busca semântica (RAG) em PostgreSQL, usa-se a extensão `pgvector`. O processo envolve: 1) Habilitar extensão: `create extension vector;`; 2) Criar tabela com coluna vetorizada: `embedding vector(768)` (768 é a dimensão padrão de modelos como Gemini/OpenAI); 3) Criar índice IVFFlat para performance: `create index ... using ivfflat ...`. A tabela armazena o conteúdo textual (`content`), metadados em JSON (`metadata`) e o vetor matemático.

## Importância
Permite que aplicações de IA busquem contexto relevante na base de dados de forma eficiente e semântica, base para sistemas RAG (Retrieval-Augmented Generation).

## Insight
Isso se conecta com [[Busca de Similaridade Vetorial]] pois a tabela criada aqui é o alvo da função de busca.

### Conexões:
- [[Busca de Similaridade Vetorial]]

## Ação
- [ ] Executar script de criação de tabela no banco de dados.
- [ ] Garantir que a dimensão do vetor (768) corresponda ao modelo de embedding usado.

## Flashcards

Qual extensão PostgreSQL habilita o armazenamento de vetores?::pgvector.

O que representa o número 768 na definição `vector(768)`?::A dimensão do vetor de embedding (tamanho do array).
<!--SR:!2025-11-24,1,230-->

O índice ==IVFFlat== é usado para acelerar a busca de similaridade vetorial.
<!--SR:!2025-11-25,1,208-->
