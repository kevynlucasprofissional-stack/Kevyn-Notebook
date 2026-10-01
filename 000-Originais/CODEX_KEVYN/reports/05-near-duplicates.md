# Near Duplicates 05

- Gerado em: 2026-04-04T16:18:23.788311-03:00
- Objetivo: Agrupar notas parecidas por similaridade textual em clusters revisaveis, sem mesclar conteudo.

## Método

- Remocao de frontmatter antes da comparacao textual.
- Fingerprint por trigrams de palavras e MinHash com banding para reduzir pares candidatos.
- Score final por Jaccard e heuristicas conservadoras para hipotese e recomendacao.
- Exclusao conservadora de diarios, dossiers longos e notas dentro de sub-vaults aninhados.

## Critérios

- Apenas notas Markdown fora de areas operacionais, fora de sub-vaults aninhados e fora de diarios ou dossiers longos entram na analise.
- Cada cluster recebe score, notas envolvidas, hipotese do motivo da redundancia e recomendacao revisavel.
- Nenhuma nota foi movida, mesclada, renomeada ou apagada.

## Arquivos afetados

- `reports/05-near-duplicates.json`
- `reports/05-near-duplicates.md`
- `logs/05-near-duplicates.md`
- `_merge_candidates/05-near-duplicates`

## Riscos

- Templates ou checklists reutilizados podem aparecer como near-duplicates intencionais.
- Notas curtas, muito estruturadas ou com muito ruido visual podem ficar fora da amostra.
- O filtro de dossiers longos usa heuristica conservadora de tamanho, palavras-chave e secoes; alguns materiais extensos podem ficar de fora.
- Hipotese e recomendacao sao heuristicas de triagem, nao decisao semantica final.

## Próximos passos

- Revisar primeiro os clusters recomendados como `arquivar`, porque tendem a refletir espelhos e copias estruturais.
- Validar clusters `preparar merge manual` manualmente antes de qualquer staging futuro.
- Se necessario, ajustar threshold e heuristicas por area do vault em uma rodada posterior, sem cruzar sub-vaults.

## Resumo

- Notas consideradas: 1566
- Notas ignoradas por estarem em sub-vaults aninhados: 363
- Notas ignoradas por serem diarios: 115
- Notas ignoradas por parecerem dossiers longos: 97
- Pares candidatos: 336
- Pares acima do threshold: 324
- Clusters revisaveis: 307

## Recomendacoes

- `arquivar`: 105 cluster(s)
- `manter`: 3 cluster(s)
- `preparar merge manual`: 199 cluster(s)

## Top Clusters

- Score 1.00 | `preparar merge manual` | 4 nota(s) | `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 15.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\(Desatualizado) Padrão de qualidade do novo tom de voz.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\(MÉTRICAS) - 2025.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\(RELATÓRIO MÉTRICAS PARA DIRETORIA) - Janeiro.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Fevereiro.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Janeiro.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\(RELEASE) Seminário Multiplicadores de Sucesso.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\050126 - Carta a Vivi.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\100226 - Gustavo Lacerda visita IF Goiano.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\110326 - Insight completo sobre como estou usando meu tempo.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\12 possíveis indicações para o Núcleo de Esporte e Cultura.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\181125 - Roteiro Minuto ACIRV.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\1º Fórum de IA da ACIRV - Planejamento Social Media.md`
- Score 1.00 | `preparar merge manual` | 2 nota(s) | `ACIRV\Notas\250226 - ROTEIRO DE CERIMONIAL CAFÉ ENTRE AMIGOS - Reforma tributária.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\251125 - Minuto ACIRV sobre o Conecta Saúde.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\Blocos de foco\170326 - Bloco de foco tipo operacional.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\BRIEFING COMPLETO – PASTA ENVELOPE INSTITUCIONAL ACIRV.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\CERIMONIAL - Café entre amigos 27.11.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\Como melhorar o relatório mensal.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\como organizar o meu tempo.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\Como é realizado a reunião de apresentação de Métricas de todo dia 30 - Modelo da Vivi.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\CONECTA SAÚDE - Campanha de Guerra.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\Conteúdos que precisam se repetir em 2026.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\cronograma otimizado para o dia 110326.md`
- Score 1.00 | `arquivar` | 2 nota(s) | `ACIRV\Notas\Dados Corrida Corre MOPORV.md`
