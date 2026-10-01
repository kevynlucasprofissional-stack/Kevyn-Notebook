# Near Dedupe 04

- Gerado em: 2026-04-04T11:00:21.286983-03:00
- Objetivo: Agrupar notas parecidas por similaridade textual sem mesclar conteúdo.

## Método

- Remoção de frontmatter antes da comparação textual.
- Fingerprint por n-grams de palavras e MinHash com banding para reduzir pares candidatos.
- Score final por Jaccard sobre trigrams.

## Critérios

- Apenas notas Markdown com volume textual mínimo entram na análise.
- A saída é cluster revisável; nenhuma fusão automática é feita.
- Frases em comum são apoio de revisão, não prova semântica final.

## Arquivos afetados

- `reports/04-near-dedupe.json`
- `reports/04-near-dedupe.md`
- `logs/04-near-dedupe.md`

## Riscos

- Notas curtas ou muito estruturadas podem não formar pares relevantes.
- Templates semelhantes podem aparecer como near-duplicate mesmo quando são intencionais.

## Próximos passos

- Revisar clusters maiores em `_merge_candidates/` apenas se houver aprovação para staging posterior.
- Cruzar pares com `exact_dedupe.py` e `quarantine_candidates.py` para separar espelho de duplicação legítima.

## Resumo

- Notas consideradas: 2109
- Pares candidatos: 509
- Pares acima do threshold: 480
- Clusters revisáveis: 368

## Top Clusters

- `HOME\Clones\ECO - Contexto Completo\07_metodologias.md` + 5 arquivo(s), score máximo 1.00
- `ACIRV\Diário\2025\12 - dezembro\02 - terça-feira.md` + 3 arquivo(s), score máximo 1.00
- `ACIRV\Notas\Playbook de Releases.md` + 3 arquivo(s), score máximo 1.00
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 15.md` + 3 arquivo(s), score máximo 1.00
- `HOME\Clones\ECO - Contexto Completo\00_identidade.md` + 3 arquivo(s), score máximo 1.00
- `HOME\Clones\ECO - Contexto Completo\02_disc.md` + 3 arquivo(s), score máximo 1.00
- `HOME\Clones\ECO - Contexto Completo\03_eneagrama.md` + 3 arquivo(s), score máximo 1.00
- `HOME\Clones\ECO - Contexto Completo\04_valores.md` + 3 arquivo(s), score máximo 1.00
- `HOME\Clones\ECO - Contexto Completo\05_heuristicas.md` + 3 arquivo(s), score máximo 1.00
- `HOME\Clones\ECO - Contexto Completo\06_metaprogramas.md` + 3 arquivo(s), score máximo 1.00
- `HOME\Clones\ECO - Contexto Completo\08_moduladores.md` + 3 arquivo(s), score máximo 1.00
- `HOME\Clones\ECO - Contexto Completo\09_contradicoes.md` + 3 arquivo(s), score máximo 1.00
- `HOME\Clones\ECO - Contexto Completo\ECO V2 por Hoor Digital.md` + 3 arquivo(s), score máximo 1.00
- `HOME\Clones\ECO - Contexto Completo\ECO V2.3.md` + 3 arquivo(s), score máximo 1.00
- `ACIRV\Notas\Kevyn vs. Renata - Uma Mudança.md` + 2 arquivo(s), score máximo 1.00
- `HOME\Clones\_Rascunho\Neuron - Plataforma de Aprendizado em Inteligência Artificial.md` + 2 arquivo(s), score máximo 1.00
- `HOME\Clones\ECO - Contexto Completo\Mais ou menos como o ECO V2.5 deve funcionar.md` + 2 arquivo(s), score máximo 1.00
- `HOME\Obsidian doc\Final\00_Motor Multi-Agentes Ágora.md` + 2 arquivo(s), score máximo 1.00
- `HOME\Obsidian doc\Final\01_Funcionalidades.md` + 2 arquivo(s), score máximo 1.00
- `HOME\Obsidian doc\Final\02_Entidades do Sistema (Data Model).md` + 2 arquivo(s), score máximo 1.00
- `HOME\Obsidian doc\Final\03_Estrutura do Banco de Dados Ágora.md` + 2 arquivo(s), score máximo 1.00
- `HOME\Obsidian doc\Final\04B - Mapa de conteúdo USER FIRST.md` + 2 arquivo(s), score máximo 1.00
- `HOME\Obsidian doc\Final\05_User Flow.md` + 2 arquivo(s), score máximo 1.00
- `HOME\Obsidian doc\Final\06_Fluxos Críticos.md` + 2 arquivo(s), score máximo 1.00
- `HOME\Obsidian doc\Final\07_Sprint de Produto Ágora.md` + 2 arquivo(s), score máximo 1.00

## Top Pares

- `.venv\Lib\site-packages\pip-25.3.dist-info\licenses\src\pip\_vendor\idna\LICENSE.md` <-> `.venv\Lib\site-packages\pip\_vendor\idna\LICENSE.md`: 1.00
- `ACIRV\Diário\2025\11 - novembro\13 - quinta-feira.md` <-> `HOME\ACIRV\Diário\2025\11 - novembro\13 - quinta-feira.md`: 1.00
- `ACIRV\Diário\2025\11 - novembro\17 - segunda-feira.md` <-> `HOME\ACIRV\Diário\2025\11 - novembro\17 - segunda-feira.md`: 1.00
- `ACIRV\Diário\2025\11 - novembro\18 - terça-feira.md` <-> `HOME\ACIRV\Diário\2025\11 - novembro\18 - terça-feira.md`: 1.00
- `ACIRV\Diário\2025\11 - novembro\19 - quarta-feira.md` <-> `HOME\ACIRV\Diário\2025\11 - novembro\19 - quarta-feira.md`: 1.00
- `ACIRV\Diário\2025\11 - novembro\21 - sexta-feira.md` <-> `HOME\ACIRV\Diário\2025\11 - novembro\21 - sexta-feira.md`: 1.00
- `ACIRV\Diário\2025\11 - novembro\24 - segunda-feira.md` <-> `HOME\ACIRV\Diário\2025\11 - novembro\24 - segunda-feira.md`: 1.00
- `ACIRV\Diário\2025\11 - novembro\25 - terça-feira.md` <-> `HOME\ACIRV\Diário\2025\11 - novembro\25 - terça-feira.md`: 1.00
- `ACIRV\Diário\2025\12 - dezembro\02 - terça-feira.md` <-> `HOME\ACIRV\Diário\2025\12 - dezembro\02 - terça-feira.md`: 1.00
- `ACIRV\Diário\2025\12 - dezembro\03 - quarta-feira.md` <-> `HOME\ACIRV\Diário\2025\12 - dezembro\03 - quarta-feira.md`: 1.00
- `ACIRV\Diário\2025\12 - dezembro\04 - quinta-feira.md` <-> `HOME\ACIRV\Diário\2025\12 - dezembro\04 - quinta-feira.md`: 1.00
- `ACIRV\Diário\2025\12 - dezembro\05 - sexta-feira.md` <-> `HOME\ACIRV\Diário\2025\12 - dezembro\05 - sexta-feira.md`: 1.00
- `ACIRV\Diário\2025\12 - dezembro\10 - quarta-feira.md` <-> `HOME\ACIRV\Diário\2025\12 - dezembro\10 - quarta-feira.md`: 1.00
- `ACIRV\Diário\2025\12 - dezembro\12 - dezembro.md` <-> `HOME\ACIRV\Diário\2025\12 - dezembro\12 - dezembro.md`: 1.00
- `ACIRV\Diário\2025\12 - dezembro\12 - sexta-feira.md` <-> `HOME\ACIRV\Diário\2025\12 - dezembro\12 - sexta-feira.md`: 1.00
- `ACIRV\Diário\2026\01 - janeiro\08 - quinta-feira.md` <-> `HOME\ACIRV\Diário\2026\01 - janeiro\08 - quinta-feira.md`: 1.00
- `ACIRV\Diário\2026\01 - janeiro\13 - terça-feira.md` <-> `HOME\ACIRV\Diário\2026\01 - janeiro\13 - terça-feira.md`: 1.00
- `ACIRV\Diário\2026\02 - fevereiro\03 - terça-feira.md` <-> `HOME\ACIRV\Diário\2026\02 - fevereiro\03 - terça-feira.md`: 1.00
- `ACIRV\Diário\2026\03 - março\05 - quinta-feira.md` <-> `HOME\ACIRV\Diário\2026\03 - março\05 - quinta-feira.md`: 1.00
- `ACIRV\Notas\(Desatualizado) Padrão de qualidade do novo tom de voz.md` <-> `HOME\ACIRV\Notas\(Desatualizado) Padrão de qualidade do novo tom de voz.md`: 1.00
- `ACIRV\Notas\(MÉTRICAS) - 2025.md` <-> `HOME\ACIRV\Notas\(MÉTRICAS) - 2025.md`: 1.00
- `ACIRV\Notas\(PLANEJAMENTO ANUAL) CONECTA ACIRV 2026.md` <-> `HOME\ACIRV\Notas\(PLANEJAMENTO ANUAL) CONECTA ACIRV 2026.md`: 1.00
- `ACIRV\Notas\(RELATÓRIO MÉTRICAS PARA DIRETORIA) - Janeiro.md` <-> `HOME\ACIRV\Notas\(RELATÓRIO MÉTRICAS PARA DIRETORIA) - Janeiro.md`: 1.00
- `ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Fevereiro.md` <-> `HOME\ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Fevereiro.md`: 1.00
- `ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Janeiro.md` <-> `HOME\ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Janeiro.md`: 1.00
