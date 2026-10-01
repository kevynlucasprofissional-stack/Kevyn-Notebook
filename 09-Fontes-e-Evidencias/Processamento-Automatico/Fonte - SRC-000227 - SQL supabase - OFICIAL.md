---
id: fonte-src-000227
titulo: Fonte - SRC-000227 - SQL supabase - OFICIAL
tipo: fonte
status: auditado
profundidade: indice
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-06-18
ultima_revisao: 2026-06-18
ciclo_integracao: CICLO-0023
fonte_id: SRC-000227
caminho_origem: Outras notas criadas por Kevyn/SQL supabase - OFICIAL.md
sha256: ae565632e93f810bdae80b928327e51ad730ac80111b2d3556a6d37e24a92c89
bytes: 1018
camada_evidencia: documento_operacional
grau_confianca: medio
sensibilidade: alta
destino_principal: '[[Inteligencia artificial e automacao]]'
tags:
- tipo/fonte
- processo/integracao
- privacidade/restrita
aliases:
- SQL supabase - OFICIAL
---
# Fonte - SRC-000227 - SQL supabase - OFICIAL

## Escopo

Arquivo lido integralmente pelo ciclo automatizado.

## Achados relevantes

- --- Modificado: - domingo 278 05/10/2025 Criado: domingo 278 05/10/2025 --- -- Enable the pgvector extension to work with embedding vectors create extension vector;
- -- Create a table to store your documents create table documents ( id bigserial primary key, content text, -- corresponds to Document.pageContent metadata jsonb, -- corresponds to Document.metadata embedding vector(1536) -- 1536 works for OpenAI embeddings, ch...

## Integracao no nucleo

- Destino principal: [[Inteligencia artificial e automacao]]
- Classificacao: integrado
- Motivo: categoria=study; score=5.0

## Limites

- O texto foi resumido com cautela.
- Trechos sensiveis foram redigidos quando necessario.

## Proveniencia

- `CICLO-0023`: `SRC-000227` foi lido integralmente e integrado em [[Inteligencia artificial e automacao]].
