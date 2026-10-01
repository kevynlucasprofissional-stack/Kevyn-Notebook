# Near Duplicates 04

- Gerado em: 2026-04-04T11:36:55.290000-03:00
- Objetivo: Agrupar notas parecidas por similaridade textual em clusters revisáveis, sem mesclar conteúdo.

## Método

- Remoção de frontmatter antes da comparação textual.
- Fingerprint por trigrams de palavras e MinHash com banding para reduzir pares candidatos.
- Score final por Jaccard e heurísticas conservadoras para hipótese e recomendação.
- Exclusão de notas dentro de sub-vaults aninhados para não cruzar fronteiras sem aprovação.

## Critérios

- Apenas notas Markdown fora de áreas operacionais e fora de sub-vaults aninhados entram na análise.
- Cada cluster recebe score, notas envolvidas, hipótese do motivo da duplicação e recomendação revisável.
- Nenhuma nota foi movida, mesclada, renomeada ou apagada.

## Arquivos afetados

- `reports/04-near-duplicates.json`
- `reports/04-near-duplicates.md`
- `logs/04-near-duplicates.md`
- `_merge_candidates/04-near-duplicates`

## Riscos

- Templates ou checklists reutilizados podem aparecer como near-duplicates intencionais.
- Notas curtas, muito estruturadas ou com muito ruído visual podem ficar fora da amostra.
- Hipótese e recomendação são heurísticas de triagem, não decisão semântica final.

## Próximos passos

- Revisar primeiro os clusters recomendados como `arquivar`, porque tendem a refletir espelhos e cópias estruturais.
- Validar clusters `preparar merge manual` manualmente antes de qualquer staging futuro.
- Se necessário, ajustar threshold por área do vault em uma rodada posterior, sem cruzar sub-vaults.

## Resumo

- Notas consideradas: 1761
- Notas ignoradas por estarem em sub-vaults aninhados: 363
- Pares candidatos: 471
- Pares acima do threshold: 443
- Clusters revisáveis: 355

## Recomendações

- `arquivar`: 148 cluster(s)
- `manter`: 5 cluster(s)
- `preparar merge manual`: 202 cluster(s)

## Top Clusters

- Score 1.00 | `preparar merge manual` | 4 nota(s) | `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 15.md`
- Score 1.00 | `arquivar` | 4 nota(s) | `HOME\Clones\ECO - Contexto Completo\02_disc.md`
- Score 1.00 | `arquivar` | 4 nota(s) | `HOME\Clones\ECO - Contexto Completo\03_eneagrama.md`
- Score 1.00 | `arquivar` | 4 nota(s) | `HOME\Clones\ECO - Contexto Completo\04_valores.md`
- Score 1.00 | `arquivar` | 4 nota(s) | `HOME\Clones\ECO - Contexto Completo\05_heuristicas.md`
- Score 1.00 | `arquivar` | 4 nota(s) | `HOME\Clones\ECO - Contexto Completo\06_metaprogramas.md`
- Score 1.00 | `arquivar` | 4 nota(s) | `HOME\Clones\ECO - Contexto Completo\08_moduladores.md`
- Score 1.00 | `arquivar` | 4 nota(s) | `HOME\Clones\ECO - Contexto Completo\09_contradicoes.md`
- Score 1.00 | `arquivar` | 3 nota(s) | `HOME\Clones\ECO - Contexto Completo\Mais ou menos como o ECO V2.5 deve funcionar.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\11 - novembro\13 - quinta-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\11 - novembro\17 - segunda-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\11 - novembro\18 - terça-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\11 - novembro\19 - quarta-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\11 - novembro\21 - sexta-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\11 - novembro\24 - segunda-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\11 - novembro\25 - terça-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\12 - dezembro\03 - quarta-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\12 - dezembro\04 - quinta-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\12 - dezembro\05 - sexta-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\12 - dezembro\10 - quarta-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\12 - dezembro\12 - dezembro.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2025\12 - dezembro\12 - sexta-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2026\01 - janeiro\08 - quinta-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2026\01 - janeiro\13 - terça-feira.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Diário\2026\02 - fevereiro\03 - terça-feira.md`
