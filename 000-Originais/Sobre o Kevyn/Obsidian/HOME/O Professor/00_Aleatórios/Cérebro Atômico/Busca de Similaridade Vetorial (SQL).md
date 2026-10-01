---
Resumo: Função SQL para encontrar documentos semanticamente próximos.
Contexto: Arquivo 0510251937.md
tags:
  - "#sql"
  - "#rag"
  - "#matematica"
ID único: 20251123021022-w2pbzr
created: 2025-11-23
---
# Busca de Similaridade Vetorial (SQL)

## Conceito
A busca de similaridade vetorial em SQL é implementada através de uma função que calcula a distância de cosseno (ou produto escalar) entre o vetor da pergunta (`query_embedding`) e os vetores armazenados. A sintaxe chave é `order by embedding <=> query_embedding`, onde `<=>` é o operador de distância de cosseno. A função retorna os documentos mais próximos (menor distância = maior similaridade), limitados por um `match_count`.

## Importância
É o coração do sistema de recuperação de informação para IA, permitindo que o sistema encontre a resposta correta baseada no significado e não apenas em palavras-chave.

## Insight
Isso se conecta com [[Configuração pgvector (PostgreSQL)]] pois utiliza a estrutura de dados lá definida para operar.

### Conexões:
- [[Configuração pgvector (PostgreSQL)]]
- [[Protocolo de Incerteza Clínica]]

## Ação
- [ ] Implementar função `match_documents` no banco.
- [ ] Testar threshold de similaridade para evitar falsos positivos.

## Flashcards

Qual operador SQL calcula a distância de cosseno no pgvector?::<=>
<!--SR:!2025-11-24,1,230-->

O que significa 'Similaridade Semântica'?::Proximidade de significado entre dois textos, representada matematicamente.
<!--SR:!2025-11-26,3,250-->

A função de busca ordena os resultados pela ==distância== entre os vetores (da menor para a maior).
