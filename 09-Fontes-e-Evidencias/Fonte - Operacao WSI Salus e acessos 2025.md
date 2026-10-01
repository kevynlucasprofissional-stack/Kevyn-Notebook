---
id: fonte-operacao-wsi-salus-e-acessos-2025
titulo: Fonte - Operacao WSI Salus e acessos 2025
tipo: fonte
status: auditado
profundidade: indice
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-06-19
ultima_revisao: 2026-06-19
subtipo: operacao_tecnica_e_comercial
camada_evidencia: documento_operacional
grau_confianca: medio_alto
sensibilidade: muito_alta
fontes_origem:
- SRC-000071
- SRC-000072
- SRC-000073
- SRC-000074
- SRC-000075
- SRC-000076
- SRC-000077
- SRC-000078
ciclos_integracao:
- CICLO-0010
tags:
- tipo/fonte
- privacidade/restrita
---
# Fonte - Operacao WSI Salus e acessos 2025

## Escopo

Fonte agregada para iteracoes SQL/N8N, experimento de busca e recomendacao, campanha DS21, infraestrutura RAG, estudo de conteudo/comunidade, reuniao operacional Salus e arquivos de credenciais.

## Redacao de seguranca

`SRC-000075` e `SRC-000078` contem senhas, client secrets, chaves e identificadores de acesso. Nenhum valor foi transcrito para o vault. Os caminhos exatos permanecem apenas no manifesto de controle.

## Fontes

| Fonte | Tipo | SHA-256 | Uso editorial |
|---|---|---|---|
| `SRC-000071` | changelog SQL | `4e36996de2a7e91de1829cefe5683ad0f45d1784b23fb9c377809a7b8b949029` | evidencia de iteracao entre Supabase e N8N |
| `SRC-000072` | resposta de IA sobre busca local | `697aae4930b94850050f4f9355b37db106fa9d8dd93ec237d76d402d618a5308` | experimento de recomendacao/autoridade, nao resultado de SEO comprovado |
| `SRC-000073` | pergunta reflexiva breve | `f36543e18d8928e2aa9ee87ac6922e3ec0a846400dd1b78ceff198d8603cd01f` | irrelevante justificado |
| `SRC-000074` | contagem regressiva DS21 | `8ec666de484550c45f0550c4e50bc1dc4fd3d6ddfa8001c5697bd19ae422a4a7` | peca de campanha |
| `SRC-000075` | infraestrutura RAG/N8N sensivel | `9e48ddd82a945eaaeecfbd6faf6554fb499dfe90960033db778a72dbdd5bbe98` | evidencia tecnica; segredos redigidos |
| `SRC-000076` | material de conteudo/comunidade | `68f8ce7c780693ac76c771a2d4c45d2279e1dc45265ef6151fe014cec32e895c` | repertorio estudado, nao teoria copiada |
| `SRC-000077` | reuniao operacional Salus | `fdbf316314714245aa67d6a4a8f93abacef4ef9332550f6d8d2f5f7a4287b5a3` | responsabilidades e planejamento, nao entrega concluida |
| `SRC-000078` | credenciais Google Cloud | `dd583f960d6d6d8bac8d83c4f4efefa1df5668871dfa8e8bb658f1440f9c8694` | existencia operacional; segredo redigido |

## Limites

O lote sustenta contato operacional de Kevyn com SQL, pgvector, Supabase, N8N, RAG, Google Cloud, campanha e organizacao de conteudo. Nao prova estabilidade de implantacao, resultado comercial ou autoria integral de materiais estudados.
