# Exact Duplicates 04

- Gerado em: 2026-04-04T16:18:07.194411-03:00
- Objetivo: Detectar duplicatas exatas por hash de conteudo, sugerir um arquivo canonico por grupo e mover apenas duplicatas de baixo risco classificadas como `mirror` ou `noise` para `_archive_review/exact-dupes/`.

## Método

- Hash SHA-256 calculado para cada arquivo fora das areas operacionais.
- Agrupamento apenas quando o hash do conteudo e identico.
- Escolha de arquivo canonico sugerido por heuristica conservadora, priorizando fora de espelho/import e fora de sub-vault aninhado.
- Arquivamento reversivel aplicado somente a duplicatas nao canonicas com sinal de `mirror` ou `noise` e fora de sub-vault aninhado.

## Critérios

- Apenas duplicatas exatas entram no agrupamento.
- Nenhum arquivo foi apagado.
- O arquivo canonico de cada grupo nunca e movido automaticamente.
- Duplicatas dentro de sub-vault aninhado ficam em `needs_review`.

## Arquivos afetados

- `reports/04-exact-duplicates.json`
- `reports/04-exact-duplicates.md`
- `logs/04-exact-duplicates.md`

## Riscos

- A escolha de canonico usa heuristica estrutural, nao julgamento semantico.
- Arquivos marcados como `mirror` podem ainda ser uteis como referencia historica; o move e reversivel, nao destrutivo.
- Duplicatas exatas sem sinal forte de `mirror` ou `noise` continuam exigindo revisao humana.

## Próximos passos

- Revisar os grupos com mais itens em `needs_review`, especialmente quando houver material fora de espelho/import.
- Se necessario, cruzar os grupos restantes com auditoria de links antes de novas rodadas de arquivamento.
- Usar o JSON desta rodada como base para checkpoints Git antes de uma nova fase de quarentena.

## Resumo

- Arquivos auditados: 3656
- Grupos de duplicata exata: 922
- Arquivos em grupos duplicados: 2100
- Candidatas seguras para arquivamento: 249
- Arquivos movidos nesta rodada: 249
- Arquivos que exigem revisao: 1851

## Arquivamento Seguro

- `mirror`: 248 arquivo(s) arquivado(s)
- `noise`: 120 arquivo(s) arquivado(s)

## Revisao Pendente

- `unclassified`: 1810 arquivo(s) em revisao
- `mirror`: 41 arquivo(s) em revisao

## Maiores Grupos

- `ACIRV\Notas\Regulamento da postagem e captura de material de eventos da ACIRV.md`: 227 arquivos, 194 arquivados, 33 em revisao
- `ACIRV\Diário\Diário.md`: 7 arquivos, 0 arquivados, 7 em revisao
- `HOME\Clones\ECO - Contexto Completo\07_metodologias.md`: 4 arquivos, 3 arquivados, 1 em revisao
- `HOME\Clones\ECO - Contexto Completo\09_contradicoes.md`: 4 arquivos, 3 arquivados, 1 em revisao
- `HOME\Clones\ECO - Contexto Completo\06_metaprogramas.md`: 4 arquivos, 3 arquivados, 1 em revisao
- `HOME\Clones\ECO - Contexto Completo\05_heuristicas.md`: 4 arquivos, 3 arquivados, 1 em revisao
- `HOME\Clones\ECO - Contexto Completo\08_moduladores.md`: 4 arquivos, 3 arquivados, 1 em revisao
- `HOME\Clones\ECO - Contexto Completo\04_valores.md`: 4 arquivos, 3 arquivados, 1 em revisao
- `HOME\Clones\ECO - Contexto Completo\03_eneagrama.md`: 4 arquivos, 3 arquivados, 1 em revisao
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 15.md`: 4 arquivos, 0 arquivados, 4 em revisao
- `HOME\Segundo Cérebro\Glow.md`: 4 arquivos, 0 arquivados, 4 em revisao
- `ACIRV\Notas\Kevyn vs. Renata - Uma Mudança.md`: 3 arquivos, 0 arquivados, 3 em revisao
- `HOME\Obsidian doc\Final\09_Integrações.md`: 3 arquivos, 0 arquivados, 3 em revisao
- `HOME\Clones\ECO - Contexto Completo\eco 2.5 - Mais ou menos como o ECO V2.5 deve funcionar.md`: 3 arquivos, 2 arquivados, 1 em revisao
- `HOME\Obsidian doc\Final\03_Estrutura do Banco de Dados Ágora.md`: 3 arquivos, 0 arquivados, 3 em revisao
- `HOME\Obsidian doc\Final\06_Fluxos Críticos.md`: 3 arquivos, 0 arquivados, 3 em revisao
- `HOME\Obsidian doc\Final\10_Segurança e Governança de Dados.md`: 3 arquivos, 0 arquivados, 3 em revisao
- `HOME\Obsidian doc\Final\08_Regras e Permissões.md`: 3 arquivos, 0 arquivados, 3 em revisao
- `HOME\Obsidian doc\Final\02_Entidades do Sistema (Data Model).md`: 3 arquivos, 0 arquivados, 3 em revisao
- `HOME\SaaS com Kelvyn\TPM\Arquivos\Pitch Deck.pdf`: 2 arquivos, 1 arquivados, 1 em revisao
- `HOME\Neuron\ARQUIVOS\Neuron - Pitch Deck.pdf`: 2 arquivos, 1 arquivados, 1 em revisao
- `ACIRV\Notas\Lista de associados em JSON.md`: 2 arquivos, 0 arquivados, 2 em revisao
- `HOME\Segundo Cérebro\Conversa sobre meu Segundo Cérebro.md`: 2 arquivos, 0 arquivados, 2 em revisao
- `HOME\Clones\_ECO\ECO V2.3.md`: 2 arquivos, 1 arquivados, 1 em revisao
- `HOME\Clones\_ECO\ECO V3.md`: 2 arquivos, 1 arquivados, 1 em revisao

## Grupos Detalhados

### Grupo 1: hash `e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855`
- Canonico sugerido: `ACIRV\Notas\Regulamento da postagem e captura de material de eventos da ACIRV.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 227
- Candidatas a arquivar: 194
- Exigem revisao: 33
- Arquivadas nesta rodada:
  - `HOME\Cérebro Profissional\Notas\Sem título.md` -> `_archive_review\exact-dupes\HOME\Cérebro Profissional\Notas\Sem título.md` [moved]
  - `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -10_trajetoria.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO 2.5 -10_trajetoria.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Gestão de Tempo\Gestão de tempo.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Gestão de Tempo\Gestão de tempo.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\202506020353.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\202506020353.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\202506020410.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\202506020410.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\@@@AAA.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\@@@AAA.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Another Brick In The Wall.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Another Brick In The Wall.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Como atender melhor seu cliente - Senai Shego.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Como atender melhor seu cliente - Senai Shego.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\DJ Thiago MD.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\DJ Thiago MD.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Estudar Hegel.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Estudar Hegel.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Lucia Alcantra Divina.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Lucia Alcantra Divina.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Lâmpada de Lava - DTTAP.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Lâmpada de Lava - DTTAP.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Manipulação com AI no PS.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Manipulação com AI no PS.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Mentalidade para Afiliados.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Mentalidade para Afiliados.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Por finalizar.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Por finalizar.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Use o tempo, e não deixe o tempo usar você..md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Use o tempo, e não deixe o tempo usar você..md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\TODAS AS NOTAS DA ACIRV\(RELATÓRIO MÉTRICAS) - Dezembro.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\TODAS AS NOTAS DA ACIRV\(RELATÓRIO MÉTRICAS) - Dezembro.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\TODAS AS NOTAS DA ACIRV\12 - segunda-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\TODAS AS NOTAS DA ACIRV\12 - segunda-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\image1.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\image1.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\03 - terça-feira 2.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\03 - terça-feira 2.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\04 - quarta-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\04 - quarta-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\08 - terça-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\08 - terça-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\09 - quarta-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\09 - quarta-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\17 - domingo.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\17 - domingo.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\2025 6-junho 03-terça-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\2025 6-junho 03-terça-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\2025-08-17.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\2025-08-17.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Imagens 2.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Imagens 2.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\novo.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\novo.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Pitch Definitivo - Espaço Prema.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Pitch Definitivo - Espaço Prema.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\S.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\S.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 1 11.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 1 11.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 1 5.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 1 5.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 1 6.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 1 6.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 12.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 12.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 15.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 15.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 16.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 16.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 17.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 17.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 25.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 25.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 31.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 31.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 34.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 34.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 37.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 37.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 39.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 39.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 40.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 40.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 41.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 41.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 42.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 42.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 43.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 43.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 46.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 46.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 47.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 47.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 48.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 48.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 50.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 50.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Untitled 1.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Untitled 1.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Untitled.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Untitled.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\(PLANO 10K EM 15 DIAS) -.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\(PLANO 10K EM 15 DIAS) -.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\Leia Charles Dickens.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\Leia Charles Dickens.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\Reunião com o André.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\Reunião com o André.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\Sem título.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\Sem título.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\03 - terça-feira 2.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\03 - terça-feira 2.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\04 - quarta-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\04 - quarta-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\08 - terça-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\08 - terça-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\09 - quarta-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\09 - quarta-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\17 - domingo.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\17 - domingo.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\2025 6-junho 03-terça-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\2025 6-junho 03-terça-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\2025-08-17.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\2025-08-17.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Imagens 2.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Imagens 2.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\novo.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\novo.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 1 5.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 1 5.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 1 6.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 1 6.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 12.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 12.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 15.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 15.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 16.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 16.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 17.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 17.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 25.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 25.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 31.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 31.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 34.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 34.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 37.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 37.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 39.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 39.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 40.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 40.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001\Obsidian Hormoziano\image1.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001\Obsidian Hormoziano\image1.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\2025-03-26.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\2025-03-26.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\A piada do Macgyver.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\A piada do Macgyver.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Animação de Personagens.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Animação de Personagens.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\CEVC AE RASCUNHO.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\CEVC AE RASCUNHO.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\CEVC AE REVISADO.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\CEVC AE REVISADO.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Comissão por afiliação.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Comissão por afiliação.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Cursos que quero fazer na área do Design.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Cursos que quero fazer na área do Design.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Design Gráfico.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Design Gráfico.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Estrutura Básica.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Estrutura Básica.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Expressões Ozi.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Expressões Ozi.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Expressõews AE.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Expressõews AE.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\handbrake.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\handbrake.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Livros.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Livros.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\M01A01 Conheça Prof. Francisco Catão.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\M01A01 Conheça Prof. Francisco Catão.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\M02A08 Como lidar com arquivos perdidos.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\M02A08 Como lidar com arquivos perdidos.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\M03A14 Como animar máscaras máscaras.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\M03A14 Como animar máscaras máscaras.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Meus serviços como designer 2.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Meus serviços como designer 2.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Meus serviços como designer.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Meus serviços como designer.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Notas gerais MA - Original.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Notas gerais MA - Original.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\O segredo é brincar - DTTAP.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\O segredo é brincar - DTTAP.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Portfólio.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Portfólio.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Quero fazer 2.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Quero fazer 2.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 1.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 1.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 10.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 10.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 2.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 2.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 3.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 3.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 4.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 4.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 5.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 5.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 6.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 6.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 7.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 7.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 8.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 8.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 9.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 9.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sobre Victor, vulgo Gaúcho. 2.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sobre Victor, vulgo Gaúcho. 2.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\techcell.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\techcell.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Tenha suas inspirações bem a vista.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Tenha suas inspirações bem a vista.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Thelema.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Thelema.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Uma nova doutrina à vista..md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Uma nova doutrina à vista..md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Ver depois.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Ver depois.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Wicca.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Wicca.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\youworkforthem.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\youworkforthem.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\202506020353.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\202506020353.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\202506020410.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\202506020410.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\@@@AAA.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\@@@AAA.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Another Brick In The Wall.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Another Brick In The Wall.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Como atender melhor seu cliente - Senai Shego.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Como atender melhor seu cliente - Senai Shego.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\DJ Thiago MD.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\DJ Thiago MD.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Estudar Hegel.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Estudar Hegel.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Lucia Alcantra Divina.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Lucia Alcantra Divina.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Lâmpada de Lava - DTTAP.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Lâmpada de Lava - DTTAP.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Manipulação com AI no PS.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Manipulação com AI no PS.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Mentalidade para Afiliados.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Mentalidade para Afiliados.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Por finalizar.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Por finalizar.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Use o tempo, e não deixe o tempo usar você..md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Use o tempo, e não deixe o tempo usar você..md` [moved]
  - `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -10_trajetoria.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -10_trajetoria.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\Misc\Goodwill compounds faster than revenue.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\Misc\Goodwill compounds faster than revenue.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\Misc\leading indicator.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\Misc\leading indicator.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\Misc\one channel.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\Misc\one channel.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Hormozi\mat\.md\Goodwill compounds faster than revenue.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Hormozi\mat\.md\Goodwill compounds faster than revenue.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Hormozi\mat\.md\leading indicator.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Hormozi\mat\.md\leading indicator.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Hormozi\mat\.md\one channel.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Hormozi\mat\.md\one channel.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\(PLANO 10K EM 15 DIAS) -.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\(PLANO 10K EM 15 DIAS) -.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\11 - novembro.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\11 - novembro.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\2) Princípios, crenças e estilo de comunicação da Barbara.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\2) Princípios, crenças e estilo de comunicação da Barbara.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\202506020353.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\202506020353.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\202506020410.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\202506020410.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\@@@AAA.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\@@@AAA.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Another Brick In The Wall.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Another Brick In The Wall.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Como atender melhor seu cliente - Senai Shego.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Como atender melhor seu cliente - Senai Shego.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\DJ Thiago MD.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\DJ Thiago MD.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Estudar Hegel.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Estudar Hegel.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Leia Charles Dickens.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Leia Charles Dickens.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Lucia Alcantra Divina.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Lucia Alcantra Divina.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Lâmpada de Lava - DTTAP.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Lâmpada de Lava - DTTAP.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Manipulação com AI no PS.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Manipulação com AI no PS.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Mentalidade para Afiliados.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Mentalidade para Afiliados.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Por finalizar.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Por finalizar.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Reunião com o André.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Reunião com o André.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Sem título.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Sem título.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Use o tempo, e não deixe o tempo usar você..md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Use o tempo, e não deixe o tempo usar você..md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\03 - terça-feira 2.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\03 - terça-feira 2.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\04 - quarta-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\04 - quarta-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\08 - terça-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\08 - terça-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\09 - quarta-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\09 - quarta-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\2025 6-junho 03-terça-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\2025 6-junho 03-terça-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Imagens 2.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Imagens 2.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\novo.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\novo.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 1 5.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 1 5.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 1 6.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 1 6.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 12.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 12.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 15.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 15.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 16.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 16.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 17.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 17.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 25.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 25.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 31.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 31.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 34.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 34.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 37.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 37.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001\Obsidian Hormoziano\Misc\Goodwill compounds faster than revenue.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001\Obsidian Hormoziano\Misc\Goodwill compounds faster than revenue.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001\Obsidian Hormoziano\Misc\leading indicator.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001\Obsidian Hormoziano\Misc\leading indicator.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001\Obsidian Hormoziano\Misc\one channel.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001\Obsidian Hormoziano\Misc\one channel.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Clones\_ECO\ECO V2.5\prompt_parts\10_trajetoria.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Clones\_ECO\ECO V2.5\prompt_parts\10_trajetoria.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\04 Livros\Livro 100M Leads\Seção V Comece.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\04 Livros\Livro 100M Leads\Seção V Comece.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Transcrição da reunião de Análise do Lançamento Semente - Ocorrida no dia 22\09\25.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Transcrição da reunião de Análise do Lançamento Semente - Ocorrida no dia 22\09\25.md` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Esbelta\Sabedoria da Bárbara\Entrevista\2) Princípios, crenças e estilo de comunicação da Barbara\2) Princípios, crenças e estilo de comunicação da Barbara.md` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Esbelta\Sabedoria da Bárbara\Entrevista\2) Princípios, crenças e estilo de comunicação da Barbara\2) Princípios, crenças e estilo de comunicação da Barbara.md` [moved]
  - `HOME\Clones\ECO - Contexto Completo\eco 2.5 - main.py` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\eco 2.5 - main.py` [moved]
  - `HOME\Clones\ECO - Contexto Completo\main.py` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\main.py` [moved]
  - `HOME\Clones\_ECO\ECO V2.5\eco 2.5 - main.py` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V2.5\eco 2.5 - main.py` [moved]
  - `HOME\Clones\_ECO\ECO V3\main.py` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V3\main.py` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 2.canvas` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 2.canvas` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Clones\_ECO\ECO V2.5\main.py` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Clones\_ECO\ECO V2.5\main.py` [moved]
  - `Google Drive (Not synced)\Meu Drive\HOME\Clones\_ECO\ECO V3\main.py` -> `_archive_review\exact-dupes\Google Drive (Not synced)\Meu Drive\HOME\Clones\_ECO\ECO V3\main.py` [moved]
- Revisao humana:
  - `ACIRV\Notas\Regulamento da postagem e captura de material de eventos da ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Gestão de Tempo\Gestão de tempo.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Segundo Cérebro\202506020353.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Segundo Cérebro\202506020410.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Segundo Cérebro\@@@AAA.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Segundo Cérebro\Another Brick In The Wall.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Segundo Cérebro\Como atender melhor seu cliente - Senai Shego.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Segundo Cérebro\DJ Thiago MD.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Segundo Cérebro\Estudar Hegel.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Segundo Cérebro\Lucia Alcantra Divina.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Segundo Cérebro\Lâmpada de Lava - DTTAP.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Segundo Cérebro\Manipulação com AI no PS.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - ... e mais 21 arquivo(s) no JSON.
### Grupo 2: hash `57cebb7f4a9c877b891acf72c38b5ec8fd823a11ead785d1ee27c369e7f90bc4`
- Canonico sugerido: `ACIRV\Diário\Diário.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 7
- Candidatas a arquivar: 0
- Exigem revisao: 7
- Revisao humana:
  - `ACIRV\Diário\Diário.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Diário\Diário.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\AULAS FGV - FUNDAÇÃO GETÚLIO VARGAS\Diário\Diário.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\BioVision\Diário\Diário.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Cérebro Criador\Diário\Diário.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Cérebro Profissional\Diário\Diário.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Nova Acrópole\Diário\Diário.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 3: hash `5547479dcb1de1fe9de4ecae09e50b93fd48c9754f0f4439127049b2c47e7a7b`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\07_metodologias.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 4
- Candidatas a arquivar: 3
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -07_metodologias.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO 2.5 -07_metodologias.md` [moved]
  - `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -07_metodologias.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -07_metodologias.md` [moved]
  - `HOME\Clones\_ECO\ECO V3\prompt_parts\07_metodologias.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V3\prompt_parts\07_metodologias.md` [moved]
- Revisao humana:
  - `HOME\Clones\ECO - Contexto Completo\07_metodologias.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 4: hash `dd9b8848b7d20514b3018fe8c5d67619c391975890d2e530694a536815f1a9a4`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\09_contradicoes.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 4
- Candidatas a arquivar: 3
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -09_contradicoes.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO 2.5 -09_contradicoes.md` [moved]
  - `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -09_contradicoes.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -09_contradicoes.md` [moved]
  - `HOME\Clones\_ECO\ECO V3\prompt_parts\09_contradicoes.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V3\prompt_parts\09_contradicoes.md` [moved]
- Revisao humana:
  - `HOME\Clones\ECO - Contexto Completo\09_contradicoes.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 5: hash `2a3e590264fe52ac50ae51a93f93d2203f40abd944c71b58cf05c4d74482a31d`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\06_metaprogramas.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 4
- Candidatas a arquivar: 3
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -06_metaprogramas.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO 2.5 -06_metaprogramas.md` [moved]
  - `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -06_metaprogramas.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -06_metaprogramas.md` [moved]
  - `HOME\Clones\_ECO\ECO V3\prompt_parts\06_metaprogramas.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V3\prompt_parts\06_metaprogramas.md` [moved]
- Revisao humana:
  - `HOME\Clones\ECO - Contexto Completo\06_metaprogramas.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 6: hash `8206c0af2658433e36e3abae870d4a90b202edb2ad12233c0e840b0cac575c31`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\05_heuristicas.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 4
- Candidatas a arquivar: 3
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -05_heuristicas.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO 2.5 -05_heuristicas.md` [moved]
  - `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -05_heuristicas.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -05_heuristicas.md` [moved]
  - `HOME\Clones\_ECO\ECO V3\prompt_parts\05_heuristicas.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V3\prompt_parts\05_heuristicas.md` [moved]
- Revisao humana:
  - `HOME\Clones\ECO - Contexto Completo\05_heuristicas.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 7: hash `3af6f81b46045b6c2c03710a8afa98a13b34ce4eb8f1ec985808accf245bd3a8`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\08_moduladores.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 4
- Candidatas a arquivar: 3
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -08_moduladores.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO 2.5 -08_moduladores.md` [moved]
  - `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -08_moduladores.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -08_moduladores.md` [moved]
  - `HOME\Clones\_ECO\ECO V3\prompt_parts\08_moduladores.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V3\prompt_parts\08_moduladores.md` [moved]
- Revisao humana:
  - `HOME\Clones\ECO - Contexto Completo\08_moduladores.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 8: hash `0edbab451f2cd86fc8896cd6006f5dbc164cfe91efbb10cdb221f1aac63d43d6`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\04_valores.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 4
- Candidatas a arquivar: 3
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -04_valores.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO 2.5 -04_valores.md` [moved]
  - `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -04_valores.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -04_valores.md` [moved]
  - `HOME\Clones\_ECO\ECO V3\prompt_parts\04_valores.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V3\prompt_parts\04_valores.md` [moved]
- Revisao humana:
  - `HOME\Clones\ECO - Contexto Completo\04_valores.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 9: hash `28154a64414500832546b35b3be0d94f7ddf318ff80b0f278a774e1b451f2521`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\03_eneagrama.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 4
- Candidatas a arquivar: 3
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -03_eneagrama.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO 2.5 -03_eneagrama.md` [moved]
  - `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -03_eneagrama.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -03_eneagrama.md` [moved]
  - `HOME\Clones\_ECO\ECO V3\prompt_parts\03_eneagrama.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V3\prompt_parts\03_eneagrama.md` [moved]
- Revisao humana:
  - `HOME\Clones\ECO - Contexto Completo\03_eneagrama.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 10: hash `8eed28a405e356b665cec6958f9cf52bdcecc735acc9a1e4ac36c94305a9f58d`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 15.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 4
- Candidatas a arquivar: 0
- Exigem revisao: 4
- Revisao humana:
  - `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 15.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 20.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 15.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 20.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 11: hash `115464c1a2719180b417c483697560bb448780e8ebc7762d566710ca0efd3b91`
- Canonico sugerido: `HOME\Segundo Cérebro\Glow.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 4
- Candidatas a arquivar: 0
- Exigem revisao: 4
- Revisao humana:
  - `HOME\Segundo Cérebro\Glow.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\M04A10 Efeito Glow.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Segundo Cérebro\SC\Glow.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Segundo Cérebro\SC\M04A10 Efeito Glow.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 12: hash `ae7c2b7346d37dfb20b9260e7f7c635ee03cb738228e03340e7ac39cdb8afb16`
- Canonico sugerido: `ACIRV\Notas\Kevyn vs. Renata - Uma Mudança.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 3
- Candidatas a arquivar: 0
- Exigem revisao: 3
- Revisao humana:
  - `ACIRV\Notas\Kevyn vs. Renata - Uma Mudança.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Kevyn vs. Renata - Uma Mudança.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Kevyn Lucas\Outros\Não integrados\Kevyn vs. Renata - Uma Mudança.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 13: hash `5431094fedb841a2881c6528dd769df895aa25438e61fb5c49416f9499955a81`
- Canonico sugerido: `HOME\Obsidian doc\Final\09_Integrações.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 3
- Candidatas a arquivar: 0
- Exigem revisao: 3
- Revisao humana:
  - `HOME\Obsidian doc\Final\09_Integrações.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Obsidian doc\tudo em um lugar\09_Integrações.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Ágora\Ágora Obsidian\Finalizados\09_Integrações.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 14: hash `dec38eb23170c708a82a62e146a78e03b2ac9a8502658e634258e8f0342d8e91`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\eco 2.5 - Mais ou menos como o ECO V2.5 deve funcionar.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 3
- Candidatas a arquivar: 2
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\Mais ou menos como o ECO V2.5 deve funcionar.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\Mais ou menos como o ECO V2.5 deve funcionar.md` [moved]
  - `HOME\Clones\_ECO\ECO V2.5\eco 2.5 - Mais ou menos como o ECO V2.5 deve funcionar.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V2.5\eco 2.5 - Mais ou menos como o ECO V2.5 deve funcionar.md` [moved]
- Revisao humana:
  - `HOME\Clones\ECO - Contexto Completo\eco 2.5 - Mais ou menos como o ECO V2.5 deve funcionar.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 15: hash `9629e0ae0883ae6da5b1dcf6cc137ef1a4699d36f86c06ae247651325c507ba6`
- Canonico sugerido: `HOME\Obsidian doc\Final\03_Estrutura do Banco de Dados Ágora.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 3
- Candidatas a arquivar: 0
- Exigem revisao: 3
- Revisao humana:
  - `HOME\Obsidian doc\Final\03_Estrutura do Banco de Dados Ágora.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Obsidian doc\tudo em um lugar\03_Estrutura do Banco de Dados Ágora.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Ágora\Ágora Obsidian\Finalizados\03_Estrutura do Banco de Dados Ágora.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 16: hash `710f4cdcf7ccd2c9711b7aa2cffa844ff7778ef32c48c20dcb64569dc309a784`
- Canonico sugerido: `HOME\Obsidian doc\Final\06_Fluxos Críticos.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 3
- Candidatas a arquivar: 0
- Exigem revisao: 3
- Revisao humana:
  - `HOME\Obsidian doc\Final\06_Fluxos Críticos.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Obsidian doc\tudo em um lugar\06_Fluxos Críticos.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Ágora\Ágora Obsidian\Finalizados\06_Fluxos Críticos.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 17: hash `8484556242d3445d54704c31ec440e5552d33609e7341cba9e45b1dd6a13383c`
- Canonico sugerido: `HOME\Obsidian doc\Final\10_Segurança e Governança de Dados.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 3
- Candidatas a arquivar: 0
- Exigem revisao: 3
- Revisao humana:
  - `HOME\Obsidian doc\Final\10_Segurança e Governança de Dados.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Obsidian doc\tudo em um lugar\10_Segurança e Governança de Dados.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Ágora\Ágora Obsidian\Finalizados\10_Segurança e Governança de Dados.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 18: hash `5621074ebc140cfe016bb0201b8846ca15a1dc2a3f36040c0ff9f96108b0cde3`
- Canonico sugerido: `HOME\Obsidian doc\Final\08_Regras e Permissões.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 3
- Candidatas a arquivar: 0
- Exigem revisao: 3
- Revisao humana:
  - `HOME\Obsidian doc\Final\08_Regras e Permissões.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Obsidian doc\tudo em um lugar\08_Regras e Permissões.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Ágora\Ágora Obsidian\Finalizados\08_Regras e Permissões.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 19: hash `8b78b6af75fb5852bb4ae53048f570b4773b9f626ee05e3f0a40dd867a5128c1`
- Canonico sugerido: `HOME\Obsidian doc\Final\02_Entidades do Sistema (Data Model).md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 3
- Candidatas a arquivar: 0
- Exigem revisao: 3
- Revisao humana:
  - `HOME\Obsidian doc\Final\02_Entidades do Sistema (Data Model).md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Obsidian doc\tudo em um lugar\02_Entidades do Sistema (Data Model).md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
  - `HOME\Ágora\Ágora Obsidian\Finalizados\02_Entidades do Sistema (Data Model).md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 20: hash `0ddbdcf8c37c367eeac412dfac5a76f320b4d0a9ae8b90b1a5f71f8c2a0e226e`
- Canonico sugerido: `HOME\SaaS com Kelvyn\TPM\Arquivos\Pitch Deck.pdf`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\SaaS com Kelvyn\TPM\Arquivos\Tudo-Para-Mulheres-TPM.pdf` -> `_archive_review\exact-dupes\HOME\SaaS com Kelvyn\TPM\Arquivos\Tudo-Para-Mulheres-TPM.pdf` [moved]
- Revisao humana:
  - `HOME\SaaS com Kelvyn\TPM\Arquivos\Pitch Deck.pdf`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 21: hash `272b52303d76563a5ee78c570715cf050ff5879fbc21411a1246104ce3afb1e0`
- Canonico sugerido: `HOME\Neuron\ARQUIVOS\Neuron - Pitch Deck.pdf`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Neuron\ARQUIVOS\Neuron.pdf` -> `_archive_review\exact-dupes\HOME\Neuron\ARQUIVOS\Neuron.pdf` [moved]
- Revisao humana:
  - `HOME\Neuron\ARQUIVOS\Neuron - Pitch Deck.pdf`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 22: hash `e56ed899b37f6b2b2d7e133296f921af3dad1568e33ad797cc231eeaa18be05f`
- Canonico sugerido: `ACIRV\Notas\Lista de associados em JSON.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Lista de associados em JSON.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Lista de associados em JSON.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 23: hash `d51919317c633e9af7b6a42c85f55e3e400d1efaf0bb302c87de9f751d725eda`
- Canonico sugerido: `HOME\Segundo Cérebro\Conversa sobre meu Segundo Cérebro.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Conversa sobre meu Segundo Cérebro.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Conversa sobre meu Segundo Cérebro.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 24: hash `caf1a5f3e1a623b4c1638398ffdce36eeddaadc8fb45cfa9d3658a252ef0556b`
- Canonico sugerido: `HOME\Clones\_ECO\ECO V2.3.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO V2.3.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO V2.3.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\ECO V2.3.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 25: hash `26fb191edfb19eb018b1e046f44a2c12fbb422ef64430396556506a38d7fcddf`
- Canonico sugerido: `HOME\Clones\_ECO\ECO V3.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO V3.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO V3.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\ECO V3.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 26: hash `57206828377eebb8557f17c62e5d6ed1e0fa65735d2ac1c370b967314887242d`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração completa.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração completa.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração completa.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 27: hash `06a8ca47e5c7e924e93f7d03712382835821798f7842a3c7e10b7b8ffc8a21ff`
- Canonico sugerido: `ACIRV\Notas\Responsabilidades do Social Media ACIRV - Com comentários.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Responsabilidades do Social Media ACIRV - Com comentários.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Responsabilidades do Social Media ACIRV - Com comentários.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 28: hash `1054f1d9ff4da29972a03c3ecc17090dce4aca66085620004af10e6df38e048a`
- Canonico sugerido: `HOME\Clones\_ECO\Como criar o ECO V3.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\Como criar o ECO V3.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\Como criar o ECO V3.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\Como criar o ECO V3.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 29: hash `d50a2d700d1ef5d8ca958a1f12e60d2be884f3490dc1d151b90540c365fc4c83`
- Canonico sugerido: `ACIRV\Notas\DADOS sobre a inauguração da reestruturação e reforma da quarta companhia do batalhão de Polícia Militar Rural.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\DADOS sobre a inauguração da reestruturação e reforma da quarta companhia do batalhão de Polícia Militar Rural.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\DADOS sobre a inauguração da reestruturação e reforma da quarta companhia do batalhão de Polícia Militar Rural.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 30: hash `c91f146e6f8dfaa8d4afded107bd9d1359f741eb04c0a69855e02d32622bfd22`
- Canonico sugerido: `HOME\Clones\_ECO\ECO V2.1.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO V2.1.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO V2.1.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\ECO V2.1.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 31: hash `7346b544e384d9b1b2c13070493c34d8389c92237ecb7ff0465affa0dbda8132`
- Canonico sugerido: `HOME\Clones\_ECO\Construindo ECO V3.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\Construindo ECO V3.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\Construindo ECO V3.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\Construindo ECO V3.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 32: hash `3cd4395b085abca19c86be3f3ca554c5a41195f41122ac7edda24a9811d126fd`
- Canonico sugerido: `ACIRV\Notas\Dados Corrida Corre MOPORV.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Dados Corrida Corre MOPORV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Dados Corrida Corre MOPORV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 33: hash `370ced357a296f4fad7c6a3f2f4ff8f0ff4e4bf372c6207f00be34bc120c5fee`
- Canonico sugerido: `HOME\Obsidian doc\Final\00_Motor Multi-Agentes Ágora.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Obsidian doc\Final\00_Motor Multi-Agentes Ágora.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Ágora\Ágora Obsidian\Finalizados\00_Motor Multi-Agentes Ágora.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 34: hash `b372b26e1d286822b1c363097b4cbbd3b7a6597ebe839cf116dd5388da7c7903`
- Canonico sugerido: `HOME\Clones\_ECO\Análise da Engenharia do ECO V2.3.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\Análise da Engenharia do ECO V2.3.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\Análise da Engenharia do ECO V2.3.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\Análise da Engenharia do ECO V2.3.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 35: hash `a5981c7bec27163d2458d921ed3f81b1d94149d849012b566d87a2326bb77822`
- Canonico sugerido: `ACIRV\Notas\Guia Estratégico para Gestão da Comunidade ACIRV.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Guia Estratégico para Gestão da Comunidade ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Guia Estratégico para Gestão da Comunidade ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 36: hash `d7afa15caa7afd8c4972aa9aa1e278eeb91bb8e1bc8acc08a8700651f3e74eec`
- Canonico sugerido: `ACIRV\Notas\(PLANEJAMENTO ANUAL) CONECTA ACIRV 2026.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\(PLANEJAMENTO ANUAL) CONECTA ACIRV 2026.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\(PLANEJAMENTO ANUAL) CONECTA ACIRV 2026.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 37: hash `76f98f4b04edc2d7467fc4e9b330baa6ede94548b03ff0763649648199daf249`
- Canonico sugerido: `ACIRV\Notas\Dados Sorriso Verdadeiro.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Dados Sorriso Verdadeiro.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Dados Sorriso Verdadeiro.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 38: hash `d5ac3e0bfb518095c622e5865c915d9916a370bdc0060fdb8bbb085b7b696b8a`
- Canonico sugerido: `HOME\Clones\_ECO\ECO por Hoor Digital - Com regras de usuário.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO por Hoor Digital - Com regras de usuário.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO por Hoor Digital - Com regras de usuário.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\ECO por Hoor Digital - Com regras de usuário.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 39: hash `a383790eea987862e122a54493c05540aaf0301af50c89a81eef55f7edada3ab`
- Canonico sugerido: `HOME\Clones\_ECO\ECO V2 por Hoor Digital.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO V2 por Hoor Digital.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO V2 por Hoor Digital.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\ECO V2 por Hoor Digital.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 40: hash `545c5860f556893835e7c3e210deed7dfb697a971e2e6cd5906ddb663f23f5a4`
- Canonico sugerido: `ACIRV\Notas\00_rascunho.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\00_rascunho.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\00_rascunho.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 41: hash `e94254293c7cfde57caac356c9469bf34369c19898e1f95f24a5bfc91ee33751`
- Canonico sugerido: `HOME\Segundo Cérebro\Quero ler.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Quero ler.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Quero ler.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 42: hash `05defcbd3dee97d3af5eeeead91bc1bce40b1be0e015770d7bb60517e3f5beb7`
- Canonico sugerido: `HOME\Obsidian doc\tudo em um lugar\Fluxos de telas desenvolvido pelo Henrique.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Obsidian doc\tudo em um lugar\Fluxos de telas desenvolvido pelo Henrique.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Ágora\Ágora Obsidian\Para roadmap\Fluxos de telas desenvolvido pelo Henrique.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 43: hash `ff62e71cd39ddc520b8699188e959784b32cca6ada650f2f1f6cad36b529f4db`
- Canonico sugerido: `ACIRV\Notas\Timeline Instagram ACIRV.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Timeline Instagram ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Timeline Instagram ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 44: hash `4cf824d4b23c2492056deec590502ff618d2c3d782e59a9453eb8c3986da9e0f`
- Canonico sugerido: `HOME\Obsidian doc\tudo em um lugar\Manual de integração das APIs.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Obsidian doc\tudo em um lugar\Manual de integração das APIs.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Ágora\Ágora Obsidian\Para roadmap\Manual de integração das APIs.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 45: hash `d13be1a79d36d05df6db607ceeecaca4b1ee5a806e2b24565e936aa281de1676`
- Canonico sugerido: `HOME\Segundo Cérebro\CEVC - Cinema 4D.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\CEVC - Cinema 4D.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\CEVC - Cinema 4D.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 46: hash `2d1e73167a3863422af687053c4fc5e9da6ae393ee7dec027f396139147703e0`
- Canonico sugerido: `HOME\Clones\_ECO\ECO V2.2.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO V2.2.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO V2.2.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\ECO V2.2.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 47: hash `a13f095648ead98acde248dd3105c050e6341067620f8224ab5ec90584affb80`
- Canonico sugerido: `HOME\Ágora\Ágora Obsidian\A.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Ágora\Ágora Obsidian\A.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
  - `HOME\Ágora\Ágora Obsidian\Finalizados\11A_Estrutura de telas em tags - ChatGPT.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 48: hash `9ab2d0e410ab160d2bb224b5194e7d8381ef3078afeff04d068b5327d344f6a3`
- Canonico sugerido: `ACIRV\Notas\Dados sobre a CAM ACIRV.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Dados sobre a CAM ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Dados sobre a CAM ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 49: hash `52d3911c161734494196dba01f544b0415c13b8fff48ab0c3a0411de24f1fb15`
- Canonico sugerido: `ACIRV\Notas\Sorriso Verdadeiro.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Sorriso Verdadeiro.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Sorriso Verdadeiro.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 50: hash `faa72a74766eac1db7914c080db4935515cb0ccc80fc06834282a2d506551e14`
- Canonico sugerido: `ACIRV\Notas\Dados sobre o Conecta Saúde.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Dados sobre o Conecta Saúde.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Dados sobre o Conecta Saúde.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 51: hash `e9ee4028f61bf89c58b291cf9968096dd16e7d17dc5e6acc4354655598fa2f05`
- Canonico sugerido: `HOME\Obsidian doc\tudo em um lugar\Ágora — Marketing Baseado em Dados.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Obsidian doc\tudo em um lugar\Ágora — Marketing Baseado em Dados.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Ágora\Ágora Obsidian\Para roadmap\Ágora — Marketing Baseado em Dados.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 52: hash `de6b3b5c51d5d69506004e24b824d5e097f55df14ce9e574a44e4824f3627b90`
- Canonico sugerido: `HOME\Segundo Cérebro\Conversa com Thoth sobre a Escada do Aeon.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Conversa com Thoth sobre a Escada do Aeon.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Conversa com Thoth sobre a Escada do Aeon.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 53: hash `c1ae5e5c21ac492f00ed5f913f9366c983afc3809e30c350e95f4d4874e4645e`
- Canonico sugerido: `ACIRV\Notas\Picanha dos depoimentos do Fórum de IA.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Picanha dos depoimentos do Fórum de IA.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Picanha dos depoimentos do Fórum de IA.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 54: hash `4ef78ed937710a4182c1f180b9ddfb4b361db252f3b6b62530a21074a739b1aa`
- Canonico sugerido: `ACIRV\Notas\Dados sobre a vinda do Vanderlan ao Rio Verde no IF Goiano.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Dados sobre a vinda do Vanderlan ao Rio Verde no IF Goiano.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Dados sobre a vinda do Vanderlan ao Rio Verde no IF Goiano.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 55: hash `09e0b9f3fb867f87b94eea19bea2b14aa9d8f944ae789991a382e4b064cd2377`
- Canonico sugerido: `HOME\Segundo Cérebro\CEVC - Adobe Premier.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\CEVC - Adobe Premier.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\CEVC - Adobe Premier.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 56: hash `aae2e1beb2aa1bd4a6eb2eecd244e65d65344fb9c68d58ae76ce520beb415162`
- Canonico sugerido: `HOME\Clones\_ECO\Análises sobre o ECO V3.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\Análises sobre o ECO V3.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\Análises sobre o ECO V3.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\Análises sobre o ECO V3.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 57: hash `0fa8109dd20ab1592a97dc6b7723a2dbbd39a8a0d852ee02c4542c3c3f2e4711`
- Canonico sugerido: `ACIRV\Notas\Dados sobre o Happy Hour do dia da mulher da ACIRV.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Dados sobre o Happy Hour do dia da mulher da ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Dados sobre o Happy Hour do dia da mulher da ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 58: hash `d702c177148ca43562af473f4cf71e2cf0ff24a541d2c3a95bce66124c28c3fa`
- Canonico sugerido: `HOME\Segundo Cérebro\Como fazer amigos e influenciar pessoas.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Como fazer amigos e influenciar pessoas.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Como fazer amigos e influenciar pessoas.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 59: hash `4ab29c4e8db9ea6a15b4c579f98668b7824b14ce42d7f49d4ca66203d502ef9f`
- Canonico sugerido: `HOME\Segundo Cérebro\Prazer, eu me chamo Kevyn..md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Prazer, eu me chamo Kevyn..md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Prazer, eu me chamo Kevyn..md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 60: hash `91fa2cfd297b89d7b6a9264ae47518733727a277b5c5a264d182b1d3f01e3530`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Carrossel Retrospectiva.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Carrossel Retrospectiva.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Carrossel Retrospectiva.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 61: hash `61ac177b96549de6c677be5b69f8a2aee131f68f5c24ca200eccfaa8e2253c88`
- Canonico sugerido: `ACIRV\Notas\JOBS - Picanha dos depoimentos do Fórum de IA.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\JOBS - Picanha dos depoimentos do Fórum de IA.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\JOBS - Picanha dos depoimentos do Fórum de IA.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 62: hash `e269fd1632ebed0bc12f034ec0068c179c9103980c9f56c8b0db806dd5124730`
- Canonico sugerido: `HOME\Segundo Cérebro\Prompt inicial EdA.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Prompt inicial EdA.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Prompt inicial EdA.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 63: hash `9dda820854d1b14ca22da050e917c1d586258127762afd132c883e56030cf2c8`
- Canonico sugerido: `ACIRV\Notas\Planejamento Social Media - Primeiro Conecta Saúde.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Planejamento Social Media - Primeiro Conecta Saúde.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Planejamento Social Media - Primeiro Conecta Saúde.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 64: hash `199e335332f94bbef8cf806be858975cc1e10b391149a2385a38f4fbb6a076f7`
- Canonico sugerido: `ACIRV\Notas\BRIEFING COMPLETO – PASTA ENVELOPE INSTITUCIONAL ACIRV.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\BRIEFING COMPLETO – PASTA ENVELOPE INSTITUCIONAL ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\BRIEFING COMPLETO – PASTA ENVELOPE INSTITUCIONAL ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 65: hash `eefddaa321bd15b4ac5825cf41b316048eb3deb2488ccb59a63836f89e303139`
- Canonico sugerido: `ACIRV\Notas\CONECTA SAÚDE - Campanha de Guerra.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\CONECTA SAÚDE - Campanha de Guerra.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\CONECTA SAÚDE - Campanha de Guerra.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 66: hash `c7724ed3cf3245b37046522a2fe18c1926cb79f6324efc1627373e11e83bd29f`
- Canonico sugerido: `ACIRV\Notas\PLANEJAMENTO - Janeiro de 2026.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\PLANEJAMENTO - Janeiro de 2026.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\PLANEJAMENTO - Janeiro de 2026.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 67: hash `153db6708afe1941b8d705446ebe96e13ee3d4d47b515cabda49918c33abcd13`
- Canonico sugerido: `ACIRV\Notas\1º Fórum de IA da ACIRV - Planejamento Social Media.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\1º Fórum de IA da ACIRV - Planejamento Social Media.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\1º Fórum de IA da ACIRV - Planejamento Social Media.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 68: hash `bb3c082988e45f213cdb60c3dc3baf39f0ea1091e2d238bdee3053aebb4b9b10`
- Canonico sugerido: `HOME\Muad’Dib\00_Cérebro Operacional\00_notas_do_cofre.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Muad’Dib\00_Cérebro Operacional\00_notas_do_cofre.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Muad’Dib\00_Dataview e Tasks\Json Limpo.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 69: hash `3a60467a66cfe783883bd7bc113f6bb05d6e27550b3f72013f40decc597a4843`
- Canonico sugerido: `HOME\Cérebro Profissional\Notas\Live semanal - Semana 01 - Por Hormozi.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Cérebro Profissional\Notas\Live semanal - Semana 01 - Por Hormozi.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Cérebro Profissional\Notas\Live semanal - Semana 01 - Por Nicolas.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 70: hash `696e5fa0eaa7f52f42c96dc3bd4fcd1298be8dc58779936c72f16dffcb704b92`
- Canonico sugerido: `ACIRV\Notas\GESTÃO DA ATENÇÃO - Café entre amigos 01.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\GESTÃO DA ATENÇÃO - Café entre amigos 01.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\GESTÃO DA ATENÇÃO - Café entre amigos 01.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 71: hash `bd004423a9871d69466a0afbf71bb62513af7411c2cf4afdf45c9305017e552b`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -01_disc.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -01_disc.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -01_disc.md` [moved]
- Revisao humana:
  - `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -01_disc.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 72: hash `ed6467da7523327b0cb2bf686d8e1c652c1356858ecf4228c97a108d6a6341cd`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\02_disc.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\_ECO\ECO V3\prompt_parts\02_disc.md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V3\prompt_parts\02_disc.md` [moved]
- Revisao humana:
  - `HOME\Clones\ECO - Contexto Completo\02_disc.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 73: hash `f5f388edf24c24c7123c9c021590e2e520fb72c7a3c85bb2551768f715579d45`
- Canonico sugerido: `ACIRV\Notas\Responsabilidades do Social Media da ACIRV.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Responsabilidades do Social Media da ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Responsabilidades do Social Media da ACIRV.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 74: hash `135b0b6baff64cca08e3081e51f80266a34c0cb41283ad0642d6cacdeaef6164`
- Canonico sugerido: `HOME\Clones\_ECO\ECO V1.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\ECO V1.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\ECO V1.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\ECO V1.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 75: hash `9952a847894d026d0a29095d14ab90c74909bf836ed09eb35de7843345bd115e`
- Canonico sugerido: `ACIRV\Notas\José Carlos Cintra.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\José Carlos Cintra.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\José Carlos Cintra.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 76: hash `d1af16a2887665c9cbb40cf87cef1b911cd4c1dd0b6aaf64cff2696e5b0c75b7`
- Canonico sugerido: `ACIRV\Notas\(MÉTRICAS) - 2025.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\(MÉTRICAS) - 2025.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\(MÉTRICAS) - 2025.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 77: hash `93b36dda5a6128cde5156e471ce413b78cdfd1b2a870a9ca4e8abfb66e0c52d4`
- Canonico sugerido: `ACIRV\Notas\Pasta de Idéias da VIVI.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Pasta de Idéias da VIVI.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Pasta de Idéias da VIVI.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 78: hash `ff68304896ba25e6a429e72926d2837167076c6e832dee3f660acdf2f7c267a6`
- Canonico sugerido: `HOME\Clones\_ECO\Reorganizar V2.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\Reorganizar V2.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\Reorganizar V2.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\Reorganizar V2.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 79: hash `f5395b68ccb9cdd75c24eb2970828576835f448261c4c269c9ce9d4433301bfe`
- Canonico sugerido: `ACIRV\Notas\250226 - ROTEIRO DE CERIMONIAL CAFÉ ENTRE AMIGOS - Reforma tributária.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\250226 - ROTEIRO DE CERIMONIAL CAFÉ ENTRE AMIGOS - Reforma tributária.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\250226 - ROTEIRO DE CERIMONIAL CAFÉ ENTRE AMIGOS.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 80: hash `29e6b38480859762a8bd1ebf2f2f3329a03fb2acce6f820eb76ba1f5d9bda20f`
- Canonico sugerido: `HOME\Segundo Cérebro\Imersão de edição de vídeos com IA - Tales Ramiro.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Imersão de edição de vídeos com IA - Tales Ramiro.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Imersão de edição de vídeos com IA - Tales Ramiro.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 81: hash `ed4551529df4461add1d3a351d5000213a71bc5de256e765c46ddda27b453be0`
- Canonico sugerido: `ACIRV\Notas\CERIMONIAL - Café entre amigos 27.11.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\CERIMONIAL - Café entre amigos 27.11.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\CERIMONIAL - Café entre amigos 27.11.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 82: hash `0b0621e990733efe21aba281d0cfd77dbc304d9a1e519919d5f406b8227c47c6`
- Canonico sugerido: `HOME\Clones\_ECO\Reorganizar V2.3.md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\ECO - Contexto Completo\Reorganizar V2.3.md` -> `_archive_review\exact-dupes\HOME\Clones\ECO - Contexto Completo\Reorganizar V2.3.md` [moved]
- Revisao humana:
  - `HOME\Clones\_ECO\Reorganizar V2.3.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 83: hash `09870197c8c8314ec55edde971a5e4910feb2f66d6358e62edf6291cf6423799`
- Canonico sugerido: `HOME\Segundo Cérebro\Os segredos da mente milionária - T. Harv Eker.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Os segredos da mente milionária - T. Harv Eker.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Os segredos da mente milionária - T. Harv Eker.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 84: hash `2f0fcfc02f32672de19e0e24dc8c72d2bc47eb833e6002a1a20f0dc4e7e9af39`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\Lembrar (Contradições finalizados).md`
- Motivo do canonico: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 1
- Exigem revisao: 1
- Arquivadas nesta rodada:
  - `HOME\Clones\_ECO\ECO V3\Lembrar (Contradições finalizados).md` -> `_archive_review\exact-dupes\HOME\Clones\_ECO\ECO V3\Lembrar (Contradições finalizados).md` [moved]
- Revisao humana:
  - `HOME\Clones\ECO - Contexto Completo\Lembrar (Contradições finalizados).md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Classificado como `mirror` por heuristica de caminho. Arquivo canonico nunca e movido automaticamente.
### Grupo 85: hash `4d93428cf13d32244278ff009385025b6d03475a4f4fd500bf59e916b3878bd7`
- Canonico sugerido: `ACIRV\Notas\Oficina VITRINE QUE VENDE.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Oficina VITRINE QUE VENDE.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Oficina VITRINE QUE VENDE.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 86: hash `3f932ecc60ecc735519a42303b0ba990f77c2cc0777026aad0677762cc62a8a3`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 01.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 01.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 01.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 87: hash `8ecf3f5ffdf112a8743131c3ac44b7dd12db41efd71eeacbadf1dfc1d8341e37`
- Canonico sugerido: `HOME\Segundo Cérebro\M06 Character Animation.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\M06 Character Animation.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\M06 Character Animation.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 88: hash `e7a4b15953c636b38ed15b719ccf39b8eb9fe2ccefb1e09420d08b79c0a9e500`
- Canonico sugerido: `HOME\Segundo Cérebro\Expressões AE.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Expressões AE.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Expressões AE.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 89: hash `2b345b82e6bb08d096f08ef084107f7d97801f0fed3d56441949a5b6cc7ec00d`
- Canonico sugerido: `HOME\Muad’Dib\00_Cérebro Operacional\00_SCRIPT_PYTHON.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Muad’Dib\00_Cérebro Operacional\00_SCRIPT_PYTHON.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\O Professor\00_Cérebro Operacional\V2\00_SCRIPT_PYTHON.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 90: hash `7b6360f716f9ea9da8623cde7c24463072dc4aec77b84071d7c48f31d3d5176d`
- Canonico sugerido: `HOME\Segundo Cérebro\Script de Vendas.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Script de Vendas.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Script de Vendas.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 91: hash `db952401d273f0449fb726a3073cfa782ad3bd00110e1ee2d4a018b8e035f8a4`
- Canonico sugerido: `HOME\Segundo Cérebro\Dicas Adicionais do AE.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Dicas Adicionais do AE.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Dicas Adicionais do AE.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 92: hash `9daac28eb283188d4ceef18d502877fc99c49ee637df6b8512367daa6d60ddf2`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 05.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 05.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 05.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 93: hash `befd48edf0e46e2b2abd002d30858efe55e6c7248d9c77705345bb04556c4688`
- Canonico sugerido: `HOME\O Professor\00_Aleatórios\como fraqueza dá dinheiro.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\O Professor\00_Aleatórios\como fraqueza dá dinheiro.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Kevyn Lucas\Outros\Integrados\Como fraqueza dá dinheiro.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Esta em sub-vault aninhado; nao mover automaticamente para nao cruzar fronteiras.
### Grupo 94: hash `e14256c75df9055a717bbe70c4a28d333601414a41509e0e6b7d71f919c715e0`
- Canonico sugerido: `ACIRV\Notas\PLAYBOOK Cerimonial Café entre Amigos.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\PLAYBOOK Cerimonial Café entre Amigos.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\PLAYBOOK Cerimonial Café entre Amigos.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 95: hash `a3992673e9d8e7ccb80a435d9ad5ff7f4aebc7b8e64b8cb5a917a2c460bc4cbc`
- Canonico sugerido: `HOME\Segundo Cérebro\Capítulo 01 - No qual Marcos teve o sono roubado..md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Capítulo 01 - No qual Marcos teve o sono roubado..md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Capítulo 01 - No qual Marcos teve o sono roubado..md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 96: hash `c49e6d0aba71e1787d7ec98ffcfb209ddb2b0e92e8842e2e05d6a86938a1ac42`
- Canonico sugerido: `ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V2.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V2.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V2.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 97: hash `fecdf05fd3c281e91d6bfe422e6fbaa2214840796a7d6a9890ab2f8aeb5d02cf`
- Canonico sugerido: `HOME\Segundo Cérebro\Mostre seu trabalho - Austin Kleon.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Mostre seu trabalho - Austin Kleon.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Mostre seu trabalho - Austin Kleon.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 98: hash `0963c76e1f6cce281fd6e8ca038a623856e436b6ae1d8baecf1b5e46258090dd`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 17.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 17.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 17.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 99: hash `100f7498d2afe9a8b7111e4e0dd37616d0710d58e2f5803841357997001dbc49`
- Canonico sugerido: `HOME\Segundo Cérebro\Notas gerais PS - Original.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `HOME\Segundo Cérebro\Notas gerais PS - Original.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\Segundo Cérebro\SC\Notas gerais PS - Original.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
### Grupo 100: hash `07b1e7dc556d024b5c4451949a2f797113a6c1f94ae859dc155d18eb0ad632a9`
- Canonico sugerido: `ACIRV\Notas\GALPÃO DE TAREFAS.md`
- Motivo do canonico: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Duplicatas no grupo: 2
- Candidatas a arquivar: 0
- Exigem revisao: 2
- Revisao humana:
  - `ACIRV\Notas\GALPÃO DE TAREFAS.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Arquivo canonico nunca e movido automaticamente.
  - `HOME\ACIRV\Notas\GALPÃO DE TAREFAS.md`: Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao permanece como candidato secundario do grupo. Sem sinal forte de `mirror` ou `noise`; manter apenas para revisao humana.
