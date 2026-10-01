# Changelog 04-exact-duplicates

Data: 2026-04-04T16:18:07.194411-03:00

## Executado

- Script Python de duplicatas exatas ajustado para saidas `04-exact-duplicates`.
- Hashes SHA-256 agrupados por igualdade total de conteudo.
- Cada duplicata foi classificada entre `safe_archive` e `needs_review` com sinais `mirror` e `noise`.
- Apenas duplicatas exatas de baixo risco fora de sub-vault aninhado foram movidas para `_archive_review/exact-dupes/`.

## Totais

- Arquivos auditados: 3656
- Grupos exatos: 922
- Arquivos em grupos duplicados: 2100
- Candidatas seguras para arquivamento: 249
- Arquivos movidos nesta rodada: 249
- Arquivos que exigem revisao: 1851
