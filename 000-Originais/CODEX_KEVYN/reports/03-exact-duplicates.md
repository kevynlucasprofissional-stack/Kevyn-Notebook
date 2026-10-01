# Exact Duplicates 03

- Gerado em: 2026-04-04T11:37:08.335794-03:00
- Objetivo: Identificar duplicatas exatas por hash de conteudo sem apagar, fundir ou mover arquivos.

## Método

- Hash SHA-256 calculado para cada arquivo fora das areas operacionais.
- Agrupamento apenas quando o hash do conteudo e identico.
- Escolha de arquivo canonico sugerido por heuristica conservadora, sem executar qualquer acao no vault.

## Critérios

- Apenas duplicatas exatas entram no agrupamento.
- Nenhum arquivo e alterado.
- Nao ha delete, merge ou move automatico.
- A sugestao de canonico e revisavel e nao executa deduplicacao.

## Arquivos afetados

- `reports/03-exact-duplicates.json`
- `reports/03-exact-duplicates.md`
- `logs/03-exact-duplicates.md`

## Riscos

- Arquivos com conteudo muito parecido, mas nao identico, ficam fora deste relatorio.
- A escolha de canonico usa heuristica estrutural, nao julgamento semantico.

## Próximos passos

- Revisar primeiro os grupos em areas espelho/import e em sub-vaults aninhados.
- Se fizer sentido, usar este relatorio como base para um manifesto manual de quarentena ou consolidacao futura.

## Resumo

- Arquivos auditados: 3656
- Grupos de duplicata exata: 922
- Arquivos duplicados envolvidos: 2100
- Arquivos seguros para revisao manual: 1178

## Maiores Grupos

- `ACIRV\Notas\Regulamento da postagem e captura de material de eventos da ACIRV.md`: 227 arquivos, hash `e3b0c44298fc`
- `ACIRV\Diário\Diário.md`: 7 arquivos, hash `57cebb7f4a9c`
- `HOME\Clones\ECO - Contexto Completo\07_metodologias.md`: 4 arquivos, hash `5547479dcb1d`
- `HOME\Clones\ECO - Contexto Completo\09_contradicoes.md`: 4 arquivos, hash `dd9b8848b7d2`
- `HOME\Clones\ECO - Contexto Completo\06_metaprogramas.md`: 4 arquivos, hash `2a3e590264fe`
- `HOME\Clones\ECO - Contexto Completo\05_heuristicas.md`: 4 arquivos, hash `8206c0af2658`
- `HOME\Clones\ECO - Contexto Completo\08_moduladores.md`: 4 arquivos, hash `3af6f81b4604`
- `HOME\Clones\ECO - Contexto Completo\04_valores.md`: 4 arquivos, hash `0edbab451f2c`
- `HOME\Clones\ECO - Contexto Completo\03_eneagrama.md`: 4 arquivos, hash `28154a644145`
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 15.md`: 4 arquivos, hash `8eed28a405e3`
- `HOME\Segundo Cérebro\Glow.md`: 4 arquivos, hash `115464c1a271`
- `ACIRV\Notas\Kevyn vs. Renata - Uma Mudança.md`: 3 arquivos, hash `ae7c2b7346d3`
- `HOME\Obsidian doc\Final\09_Integrações.md`: 3 arquivos, hash `5431094fedb8`
- `HOME\Clones\ECO - Contexto Completo\eco 2.5 - Mais ou menos como o ECO V2.5 deve funcionar.md`: 3 arquivos, hash `dec38eb23170`
- `HOME\Obsidian doc\Final\03_Estrutura do Banco de Dados Ágora.md`: 3 arquivos, hash `9629e0ae0883`
- `HOME\Obsidian doc\Final\06_Fluxos Críticos.md`: 3 arquivos, hash `710f4cdcf7cc`
- `HOME\Obsidian doc\Final\10_Segurança e Governança de Dados.md`: 3 arquivos, hash `8484556242d3`
- `HOME\Obsidian doc\Final\08_Regras e Permissões.md`: 3 arquivos, hash `5621074ebc14`
- `HOME\Obsidian doc\Final\02_Entidades do Sistema (Data Model).md`: 3 arquivos, hash `8b78b6af75fb`
- `HOME\SaaS com Kelvyn\TPM\Arquivos\Pitch Deck.pdf`: 2 arquivos, hash `0ddbdcf8c37c`
- `HOME\Neuron\ARQUIVOS\Neuron - Pitch Deck.pdf`: 2 arquivos, hash `272b52303d76`
- `ACIRV\Notas\Lista de associados em JSON.md`: 2 arquivos, hash `e56ed899b37f`
- `HOME\Segundo Cérebro\Conversa sobre meu Segundo Cérebro.md`: 2 arquivos, hash `d51919317c63`
- `HOME\Clones\_ECO\ECO V2.3.md`: 2 arquivos, hash `caf1a5f3e1a6`
- `HOME\Clones\_ECO\ECO V3.md`: 2 arquivos, hash `26fb191edfb1`

## Grupos Detalhados

### Grupo 1: hash `e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855`
- Canonico sugerido: `ACIRV\Notas\Regulamento da postagem e captura de material de eventos da ACIRV.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Gestão de Tempo\Gestão de tempo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\202506020353.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\202506020410.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\@@@AAA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\Another Brick In The Wall.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\Como atender melhor seu cliente - Senai Shego.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\DJ Thiago MD.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\Estudar Hegel.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\Lucia Alcantra Divina.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\Lâmpada de Lava - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\Manipulação com AI no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\Mentalidade para Afiliados.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\Por finalizar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\Use o tempo, e não deixe o tempo usar você..md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Cérebro Profissional\Notas\(PLANO 10K EM 15 DIAS) -.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Cérebro Profissional\Notas\Leia Charles Dickens.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Cérebro Profissional\Notas\Reunião com o André.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Cérebro Profissional\Notas\Sem título.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\202506020353.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\202506020410.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\@@@AAA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\Another Brick In The Wall.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\Como atender melhor seu cliente - Senai Shego.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\DJ Thiago MD.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\Estudar Hegel.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\Lucia Alcantra Divina.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\Lâmpada de Lava - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\Manipulação com AI no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\Mentalidade para Afiliados.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\Por finalizar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\Use o tempo, e não deixe o tempo usar você..md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -10_trajetoria.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Gestão de Tempo\Gestão de tempo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\202506020353.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\202506020410.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\@@@AAA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Another Brick In The Wall.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Como atender melhor seu cliente - Senai Shego.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\DJ Thiago MD.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Estudar Hegel.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Lucia Alcantra Divina.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Lâmpada de Lava - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Manipulação com AI no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Mentalidade para Afiliados.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Por finalizar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\Use o tempo, e não deixe o tempo usar você..md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\TODAS AS NOTAS DA ACIRV\(RELATÓRIO MÉTRICAS) - Dezembro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\TODAS AS NOTAS DA ACIRV\12 - segunda-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\image1.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\03 - terça-feira 2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\04 - quarta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\08 - terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\09 - quarta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\17 - domingo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\2025 6-junho 03-terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\2025-08-17.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Imagens 2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\novo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Pitch Definitivo - Espaço Prema.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\S.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 1 11.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 1 5.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 1 6.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 12.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 15.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 16.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 17.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 25.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 31.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 34.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 37.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 39.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 40.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 41.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 42.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 43.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 46.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 47.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 48.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 50.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Untitled 1.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Untitled.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\(PLANO 10K EM 15 DIAS) -.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\Leia Charles Dickens.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\Reunião com o André.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\Sem título.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\03 - terça-feira 2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\04 - quarta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\08 - terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\09 - quarta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\17 - domingo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\2025 6-junho 03-terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\2025-08-17.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Imagens 2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\novo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 1 5.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 1 6.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 12.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 15.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 16.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 17.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 25.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 31.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 34.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 37.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 39.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título 40.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash\Sem título.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001\Obsidian Hormoziano\image1.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\2025-03-26.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\A piada do Macgyver.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Animação de Personagens.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\CEVC AE RASCUNHO.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\CEVC AE REVISADO.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Comissão por afiliação.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Cursos que quero fazer na área do Design.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Design Gráfico.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Estrutura Básica.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Expressões Ozi.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Expressõews AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\handbrake.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Livros.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\M01A01 Conheça Prof. Francisco Catão.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\M02A08 Como lidar com arquivos perdidos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\M03A14 Como animar máscaras máscaras.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Meus serviços como designer 2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Meus serviços como designer.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Notas gerais MA - Original.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\O segredo é brincar - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Portfólio.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Quero fazer 2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 1.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 10.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 3.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 4.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 5.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 6.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 7.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 8.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título 9.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sem título.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Sobre Victor, vulgo Gaúcho. 2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\techcell.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Tenha suas inspirações bem a vista.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Thelema.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Uma nova doutrina à vista..md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Ver depois.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\Wicca.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash\youworkforthem.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\202506020353.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\202506020410.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\@@@AAA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Another Brick In The Wall.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Como atender melhor seu cliente - Senai Shego.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\DJ Thiago MD.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Estudar Hegel.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Lucia Alcantra Divina.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Lâmpada de Lava - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Manipulação com AI no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Mentalidade para Afiliados.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Por finalizar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\SC\Use o tempo, e não deixe o tempo usar você..md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -10_trajetoria.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\Misc\Goodwill compounds faster than revenue.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\Misc\leading indicator.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\Misc\one channel.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Hormozi\mat\.md\Goodwill compounds faster than revenue.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Hormozi\mat\.md\leading indicator.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Hormozi\mat\.md\one channel.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\(PLANO 10K EM 15 DIAS) -.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\11 - novembro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\2) Princípios, crenças e estilo de comunicação da Barbara.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\202506020353.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\202506020410.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\@@@AAA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Another Brick In The Wall.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Como atender melhor seu cliente - Senai Shego.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\DJ Thiago MD.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Estudar Hegel.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Leia Charles Dickens.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Lucia Alcantra Divina.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Lâmpada de Lava - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Manipulação com AI no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Mentalidade para Afiliados.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Por finalizar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Reunião com o André.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Sem título.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Use o tempo, e não deixe o tempo usar você..md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\03 - terça-feira 2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\04 - quarta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\08 - terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\09 - quarta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\2025 6-junho 03-terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Imagens 2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\novo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 1 5.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 1 6.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 12.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 15.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 16.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 17.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 25.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 31.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 34.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 37.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001\Obsidian Hormoziano\Misc\Goodwill compounds faster than revenue.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001\Obsidian Hormoziano\Misc\leading indicator.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001\Obsidian Hormoziano\Misc\one channel.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Clones\_ECO\ECO V2.5\prompt_parts\10_trajetoria.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\04 Livros\Livro 100M Leads\Seção V Comece.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Transcrição da reunião de Análise do Lançamento Semente - Ocorrida no dia 22\09\25.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Esbelta\Sabedoria da Bárbara\Entrevista\2) Princípios, crenças e estilo de comunicação da Barbara\2) Princípios, crenças e estilo de comunicação da Barbara.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\ECO - Contexto Completo\eco 2.5 - main.py` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\ECO - Contexto Completo\main.py` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V2.5\eco 2.5 - main.py` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V3\main.py` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 2.canvas` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Clones\_ECO\ECO V2.5\main.py` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `Google Drive (Not synced)\Meu Drive\HOME\Clones\_ECO\ECO V3\main.py` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 2: hash `57cebb7f4a9c877b891acf72c38b5ec8fd823a11ead785d1ee27c369e7f90bc4`
- Canonico sugerido: `ACIRV\Diário\Diário.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\Diário.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\AULAS FGV - FUNDAÇÃO GETÚLIO VARGAS\Diário\Diário.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\BioVision\Diário\Diário.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Cérebro Criador\Diário\Diário.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Cérebro Profissional\Diário\Diário.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Nova Acrópole\Diário\Diário.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 3: hash `5547479dcb1de1fe9de4ecae09e50b93fd48c9754f0f4439127049b2c47e7a7b`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\07_metodologias.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -07_metodologias.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -07_metodologias.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V3\prompt_parts\07_metodologias.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 4: hash `dd9b8848b7d20514b3018fe8c5d67619c391975890d2e530694a536815f1a9a4`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\09_contradicoes.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -09_contradicoes.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -09_contradicoes.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V3\prompt_parts\09_contradicoes.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 5: hash `2a3e590264fe52ac50ae51a93f93d2203f40abd944c71b58cf05c4d74482a31d`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\06_metaprogramas.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -06_metaprogramas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -06_metaprogramas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V3\prompt_parts\06_metaprogramas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 6: hash `8206c0af2658433e36e3abae870d4a90b202edb2ad12233c0e840b0cac575c31`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\05_heuristicas.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -05_heuristicas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -05_heuristicas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V3\prompt_parts\05_heuristicas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 7: hash `3af6f81b46045b6c2c03710a8afa98a13b34ce4eb8f1ec985808accf245bd3a8`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\08_moduladores.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -08_moduladores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -08_moduladores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V3\prompt_parts\08_moduladores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 8: hash `0edbab451f2cd86fc8896cd6006f5dbc164cfe91efbb10cdb221f1aac63d43d6`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\04_valores.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -04_valores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -04_valores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V3\prompt_parts\04_valores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 9: hash `28154a64414500832546b35b3be0d94f7ddf318ff80b0f278a774e1b451f2521`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\03_eneagrama.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -03_eneagrama.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -03_eneagrama.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V3\prompt_parts\03_eneagrama.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 10: hash `8eed28a405e356b665cec6958f9cf52bdcecc735acc9a1e4ac36c94305a9f58d`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 15.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 20.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 15.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 20.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 11: hash `115464c1a2719180b417c483697560bb448780e8ebc7762d566710ca0efd3b91`
- Canonico sugerido: `HOME\Segundo Cérebro\Glow.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\M04A10 Efeito Glow.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\Glow.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Segundo Cérebro\SC\M04A10 Efeito Glow.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 12: hash `ae7c2b7346d37dfb20b9260e7f7c635ee03cb738228e03340e7ac39cdb8afb16`
- Canonico sugerido: `ACIRV\Notas\Kevyn vs. Renata - Uma Mudança.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Kevyn vs. Renata - Uma Mudança.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Kevyn Lucas\Outros\Não integrados\Kevyn vs. Renata - Uma Mudança.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 13: hash `5431094fedb841a2881c6528dd769df895aa25438e61fb5c49416f9499955a81`
- Canonico sugerido: `HOME\Obsidian doc\Final\09_Integrações.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Obsidian doc\tudo em um lugar\09_Integrações.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Ágora\Ágora Obsidian\Finalizados\09_Integrações.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 14: hash `dec38eb23170c708a82a62e146a78e03b2ac9a8502658e634258e8f0342d8e91`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\eco 2.5 - Mais ou menos como o ECO V2.5 deve funcionar.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\Mais ou menos como o ECO V2.5 deve funcionar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.); `HOME\Clones\_ECO\ECO V2.5\eco 2.5 - Mais ou menos como o ECO V2.5 deve funcionar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 15: hash `9629e0ae0883ae6da5b1dcf6cc137ef1a4699d36f86c06ae247651325c507ba6`
- Canonico sugerido: `HOME\Obsidian doc\Final\03_Estrutura do Banco de Dados Ágora.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Obsidian doc\tudo em um lugar\03_Estrutura do Banco de Dados Ágora.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Ágora\Ágora Obsidian\Finalizados\03_Estrutura do Banco de Dados Ágora.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 16: hash `710f4cdcf7ccd2c9711b7aa2cffa844ff7778ef32c48c20dcb64569dc309a784`
- Canonico sugerido: `HOME\Obsidian doc\Final\06_Fluxos Críticos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Obsidian doc\tudo em um lugar\06_Fluxos Críticos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Ágora\Ágora Obsidian\Finalizados\06_Fluxos Críticos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 17: hash `8484556242d3445d54704c31ec440e5552d33609e7341cba9e45b1dd6a13383c`
- Canonico sugerido: `HOME\Obsidian doc\Final\10_Segurança e Governança de Dados.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Obsidian doc\tudo em um lugar\10_Segurança e Governança de Dados.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Ágora\Ágora Obsidian\Finalizados\10_Segurança e Governança de Dados.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 18: hash `5621074ebc140cfe016bb0201b8846ca15a1dc2a3f36040c0ff9f96108b0cde3`
- Canonico sugerido: `HOME\Obsidian doc\Final\08_Regras e Permissões.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Obsidian doc\tudo em um lugar\08_Regras e Permissões.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Ágora\Ágora Obsidian\Finalizados\08_Regras e Permissões.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 19: hash `8b78b6af75fb5852bb4ae53048f570b4773b9f626ee05e3f0a40dd867a5128c1`
- Canonico sugerido: `HOME\Obsidian doc\Final\02_Entidades do Sistema (Data Model).md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Obsidian doc\tudo em um lugar\02_Entidades do Sistema (Data Model).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.); `HOME\Ágora\Ágora Obsidian\Finalizados\02_Entidades do Sistema (Data Model).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 20: hash `0ddbdcf8c37c367eeac412dfac5a76f320b4d0a9ae8b90b1a5f71f8c2a0e226e`
- Canonico sugerido: `HOME\SaaS com Kelvyn\TPM\Arquivos\Pitch Deck.pdf`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\SaaS com Kelvyn\TPM\Arquivos\Tudo-Para-Mulheres-TPM.pdf` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 21: hash `272b52303d76563a5ee78c570715cf050ff5879fbc21411a1246104ce3afb1e0`
- Canonico sugerido: `HOME\Neuron\ARQUIVOS\Neuron - Pitch Deck.pdf`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Neuron\ARQUIVOS\Neuron.pdf` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 22: hash `e56ed899b37f6b2b2d7e133296f921af3dad1568e33ad797cc231eeaa18be05f`
- Canonico sugerido: `ACIRV\Notas\Lista de associados em JSON.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Lista de associados em JSON.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 23: hash `d51919317c633e9af7b6a42c85f55e3e400d1efaf0bb302c87de9f751d725eda`
- Canonico sugerido: `HOME\Segundo Cérebro\Conversa sobre meu Segundo Cérebro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Conversa sobre meu Segundo Cérebro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 24: hash `caf1a5f3e1a623b4c1638398ffdce36eeddaadc8fb45cfa9d3658a252ef0556b`
- Canonico sugerido: `HOME\Clones\_ECO\ECO V2.3.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO V2.3.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 25: hash `26fb191edfb19eb018b1e046f44a2c12fbb422ef64430396556506a38d7fcddf`
- Canonico sugerido: `HOME\Clones\_ECO\ECO V3.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO V3.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 26: hash `57206828377eebb8557f17c62e5d6ed1e0fa65735d2ac1c370b967314887242d`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração completa.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração completa.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 27: hash `06a8ca47e5c7e924e93f7d03712382835821798f7842a3c7e10b7b8ffc8a21ff`
- Canonico sugerido: `ACIRV\Notas\Responsabilidades do Social Media ACIRV - Com comentários.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Responsabilidades do Social Media ACIRV - Com comentários.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 28: hash `1054f1d9ff4da29972a03c3ecc17090dce4aca66085620004af10e6df38e048a`
- Canonico sugerido: `HOME\Clones\_ECO\Como criar o ECO V3.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\Como criar o ECO V3.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 29: hash `d50a2d700d1ef5d8ca958a1f12e60d2be884f3490dc1d151b90540c365fc4c83`
- Canonico sugerido: `ACIRV\Notas\DADOS sobre a inauguração da reestruturação e reforma da quarta companhia do batalhão de Polícia Militar Rural.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\DADOS sobre a inauguração da reestruturação e reforma da quarta companhia do batalhão de Polícia Militar Rural.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 30: hash `c91f146e6f8dfaa8d4afded107bd9d1359f741eb04c0a69855e02d32622bfd22`
- Canonico sugerido: `HOME\Clones\_ECO\ECO V2.1.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO V2.1.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 31: hash `7346b544e384d9b1b2c13070493c34d8389c92237ecb7ff0465affa0dbda8132`
- Canonico sugerido: `HOME\Clones\_ECO\Construindo ECO V3.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\Construindo ECO V3.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 32: hash `3cd4395b085abca19c86be3f3ca554c5a41195f41122ac7edda24a9811d126fd`
- Canonico sugerido: `ACIRV\Notas\Dados Corrida Corre MOPORV.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Dados Corrida Corre MOPORV.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 33: hash `370ced357a296f4fad7c6a3f2f4ff8f0ff4e4bf372c6207f00be34bc120c5fee`
- Canonico sugerido: `HOME\Obsidian doc\Final\00_Motor Multi-Agentes Ágora.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Finalizados\00_Motor Multi-Agentes Ágora.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 34: hash `b372b26e1d286822b1c363097b4cbbd3b7a6597ebe839cf116dd5388da7c7903`
- Canonico sugerido: `HOME\Clones\_ECO\Análise da Engenharia do ECO V2.3.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\Análise da Engenharia do ECO V2.3.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 35: hash `a5981c7bec27163d2458d921ed3f81b1d94149d849012b566d87a2326bb77822`
- Canonico sugerido: `ACIRV\Notas\Guia Estratégico para Gestão da Comunidade ACIRV.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Guia Estratégico para Gestão da Comunidade ACIRV.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 36: hash `d7afa15caa7afd8c4972aa9aa1e278eeb91bb8e1bc8acc08a8700651f3e74eec`
- Canonico sugerido: `ACIRV\Notas\(PLANEJAMENTO ANUAL) CONECTA ACIRV 2026.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\(PLANEJAMENTO ANUAL) CONECTA ACIRV 2026.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 37: hash `76f98f4b04edc2d7467fc4e9b330baa6ede94548b03ff0763649648199daf249`
- Canonico sugerido: `ACIRV\Notas\Dados Sorriso Verdadeiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Dados Sorriso Verdadeiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 38: hash `d5ac3e0bfb518095c622e5865c915d9916a370bdc0060fdb8bbb085b7b696b8a`
- Canonico sugerido: `HOME\Clones\_ECO\ECO por Hoor Digital - Com regras de usuário.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO por Hoor Digital - Com regras de usuário.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 39: hash `a383790eea987862e122a54493c05540aaf0301af50c89a81eef55f7edada3ab`
- Canonico sugerido: `HOME\Clones\_ECO\ECO V2 por Hoor Digital.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO V2 por Hoor Digital.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 40: hash `545c5860f556893835e7c3e210deed7dfb697a971e2e6cd5906ddb663f23f5a4`
- Canonico sugerido: `ACIRV\Notas\00_rascunho.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\00_rascunho.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 41: hash `e94254293c7cfde57caac356c9469bf34369c19898e1f95f24a5bfc91ee33751`
- Canonico sugerido: `HOME\Segundo Cérebro\Quero ler.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Quero ler.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 42: hash `05defcbd3dee97d3af5eeeead91bc1bce40b1be0e015770d7bb60517e3f5beb7`
- Canonico sugerido: `HOME\Obsidian doc\tudo em um lugar\Fluxos de telas desenvolvido pelo Henrique.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Para roadmap\Fluxos de telas desenvolvido pelo Henrique.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 43: hash `ff62e71cd39ddc520b8699188e959784b32cca6ada650f2f1f6cad36b529f4db`
- Canonico sugerido: `ACIRV\Notas\Timeline Instagram ACIRV.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Timeline Instagram ACIRV.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 44: hash `4cf824d4b23c2492056deec590502ff618d2c3d782e59a9453eb8c3986da9e0f`
- Canonico sugerido: `HOME\Obsidian doc\tudo em um lugar\Manual de integração das APIs.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Para roadmap\Manual de integração das APIs.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 45: hash `d13be1a79d36d05df6db607ceeecaca4b1ee5a806e2b24565e936aa281de1676`
- Canonico sugerido: `HOME\Segundo Cérebro\CEVC - Cinema 4D.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\CEVC - Cinema 4D.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 46: hash `2d1e73167a3863422af687053c4fc5e9da6ae393ee7dec027f396139147703e0`
- Canonico sugerido: `HOME\Clones\_ECO\ECO V2.2.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO V2.2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 47: hash `a13f095648ead98acde248dd3105c050e6341067620f8224ab5ec90584affb80`
- Canonico sugerido: `HOME\Ágora\Ágora Obsidian\A.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Finalizados\11A_Estrutura de telas em tags - ChatGPT.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 48: hash `9ab2d0e410ab160d2bb224b5194e7d8381ef3078afeff04d068b5327d344f6a3`
- Canonico sugerido: `ACIRV\Notas\Dados sobre a CAM ACIRV.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Dados sobre a CAM ACIRV.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 49: hash `52d3911c161734494196dba01f544b0415c13b8fff48ab0c3a0411de24f1fb15`
- Canonico sugerido: `ACIRV\Notas\Sorriso Verdadeiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Sorriso Verdadeiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 50: hash `faa72a74766eac1db7914c080db4935515cb0ccc80fc06834282a2d506551e14`
- Canonico sugerido: `ACIRV\Notas\Dados sobre o Conecta Saúde.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Dados sobre o Conecta Saúde.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 51: hash `e9ee4028f61bf89c58b291cf9968096dd16e7d17dc5e6acc4354655598fa2f05`
- Canonico sugerido: `HOME\Obsidian doc\tudo em um lugar\Ágora — Marketing Baseado em Dados.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Para roadmap\Ágora — Marketing Baseado em Dados.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 52: hash `de6b3b5c51d5d69506004e24b824d5e097f55df14ce9e574a44e4824f3627b90`
- Canonico sugerido: `HOME\Segundo Cérebro\Conversa com Thoth sobre a Escada do Aeon.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Conversa com Thoth sobre a Escada do Aeon.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 53: hash `c1ae5e5c21ac492f00ed5f913f9366c983afc3809e30c350e95f4d4874e4645e`
- Canonico sugerido: `ACIRV\Notas\Picanha dos depoimentos do Fórum de IA.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Picanha dos depoimentos do Fórum de IA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 54: hash `4ef78ed937710a4182c1f180b9ddfb4b361db252f3b6b62530a21074a739b1aa`
- Canonico sugerido: `ACIRV\Notas\Dados sobre a vinda do Vanderlan ao Rio Verde no IF Goiano.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Dados sobre a vinda do Vanderlan ao Rio Verde no IF Goiano.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 55: hash `09e0b9f3fb867f87b94eea19bea2b14aa9d8f944ae789991a382e4b064cd2377`
- Canonico sugerido: `HOME\Segundo Cérebro\CEVC - Adobe Premier.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\CEVC - Adobe Premier.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 56: hash `aae2e1beb2aa1bd4a6eb2eecd244e65d65344fb9c68d58ae76ce520beb415162`
- Canonico sugerido: `HOME\Clones\_ECO\Análises sobre o ECO V3.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\Análises sobre o ECO V3.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 57: hash `0fa8109dd20ab1592a97dc6b7723a2dbbd39a8a0d852ee02c4542c3c3f2e4711`
- Canonico sugerido: `ACIRV\Notas\Dados sobre o Happy Hour do dia da mulher da ACIRV.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Dados sobre o Happy Hour do dia da mulher da ACIRV.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 58: hash `d702c177148ca43562af473f4cf71e2cf0ff24a541d2c3a95bce66124c28c3fa`
- Canonico sugerido: `HOME\Segundo Cérebro\Como fazer amigos e influenciar pessoas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Como fazer amigos e influenciar pessoas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 59: hash `4ab29c4e8db9ea6a15b4c579f98668b7824b14ce42d7f49d4ca66203d502ef9f`
- Canonico sugerido: `HOME\Segundo Cérebro\Prazer, eu me chamo Kevyn..md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Prazer, eu me chamo Kevyn..md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 60: hash `91fa2cfd297b89d7b6a9264ae47518733727a277b5c5a264d182b1d3f01e3530`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Carrossel Retrospectiva.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Carrossel Retrospectiva.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 61: hash `61ac177b96549de6c677be5b69f8a2aee131f68f5c24ca200eccfaa8e2253c88`
- Canonico sugerido: `ACIRV\Notas\JOBS - Picanha dos depoimentos do Fórum de IA.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\JOBS - Picanha dos depoimentos do Fórum de IA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 62: hash `e269fd1632ebed0bc12f034ec0068c179c9103980c9f56c8b0db806dd5124730`
- Canonico sugerido: `HOME\Segundo Cérebro\Prompt inicial EdA.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Prompt inicial EdA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 63: hash `9dda820854d1b14ca22da050e917c1d586258127762afd132c883e56030cf2c8`
- Canonico sugerido: `ACIRV\Notas\Planejamento Social Media - Primeiro Conecta Saúde.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Planejamento Social Media - Primeiro Conecta Saúde.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 64: hash `199e335332f94bbef8cf806be858975cc1e10b391149a2385a38f4fbb6a076f7`
- Canonico sugerido: `ACIRV\Notas\BRIEFING COMPLETO – PASTA ENVELOPE INSTITUCIONAL ACIRV.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\BRIEFING COMPLETO – PASTA ENVELOPE INSTITUCIONAL ACIRV.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 65: hash `eefddaa321bd15b4ac5825cf41b316048eb3deb2488ccb59a63836f89e303139`
- Canonico sugerido: `ACIRV\Notas\CONECTA SAÚDE - Campanha de Guerra.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\CONECTA SAÚDE - Campanha de Guerra.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 66: hash `c7724ed3cf3245b37046522a2fe18c1926cb79f6324efc1627373e11e83bd29f`
- Canonico sugerido: `ACIRV\Notas\PLANEJAMENTO - Janeiro de 2026.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\PLANEJAMENTO - Janeiro de 2026.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 67: hash `153db6708afe1941b8d705446ebe96e13ee3d4d47b515cabda49918c33abcd13`
- Canonico sugerido: `ACIRV\Notas\1º Fórum de IA da ACIRV - Planejamento Social Media.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\1º Fórum de IA da ACIRV - Planejamento Social Media.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 68: hash `bb3c082988e45f213cdb60c3dc3baf39f0ea1091e2d238bdee3053aebb4b9b10`
- Canonico sugerido: `HOME\Muad’Dib\00_Cérebro Operacional\00_notas_do_cofre.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Muad’Dib\00_Dataview e Tasks\Json Limpo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 69: hash `3a60467a66cfe783883bd7bc113f6bb05d6e27550b3f72013f40decc597a4843`
- Canonico sugerido: `HOME\Cérebro Profissional\Notas\Live semanal - Semana 01 - Por Hormozi.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Cérebro Profissional\Notas\Live semanal - Semana 01 - Por Nicolas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 70: hash `696e5fa0eaa7f52f42c96dc3bd4fcd1298be8dc58779936c72f16dffcb704b92`
- Canonico sugerido: `ACIRV\Notas\GESTÃO DA ATENÇÃO - Café entre amigos 01.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\GESTÃO DA ATENÇÃO - Café entre amigos 01.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 71: hash `bd004423a9871d69466a0afbf71bb62513af7411c2cf4afdf45c9305017e552b`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\ECO 2.5 -01_disc.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 -01_disc.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 72: hash `ed6467da7523327b0cb2bf686d8e1c652c1356858ecf4228c97a108d6a6341cd`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\02_disc.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\_ECO\ECO V3\prompt_parts\02_disc.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 73: hash `f5f388edf24c24c7123c9c021590e2e520fb72c7a3c85bb2551768f715579d45`
- Canonico sugerido: `ACIRV\Notas\Responsabilidades do Social Media da ACIRV.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Responsabilidades do Social Media da ACIRV.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 74: hash `135b0b6baff64cca08e3081e51f80266a34c0cb41283ad0642d6cacdeaef6164`
- Canonico sugerido: `HOME\Clones\_ECO\ECO V1.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\ECO V1.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 75: hash `9952a847894d026d0a29095d14ab90c74909bf836ed09eb35de7843345bd115e`
- Canonico sugerido: `ACIRV\Notas\José Carlos Cintra.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\José Carlos Cintra.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 76: hash `d1af16a2887665c9cbb40cf87cef1b911cd4c1dd0b6aaf64cff2696e5b0c75b7`
- Canonico sugerido: `ACIRV\Notas\(MÉTRICAS) - 2025.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\(MÉTRICAS) - 2025.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 77: hash `93b36dda5a6128cde5156e471ce413b78cdfd1b2a870a9ca4e8abfb66e0c52d4`
- Canonico sugerido: `ACIRV\Notas\Pasta de Idéias da VIVI.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Pasta de Idéias da VIVI.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 78: hash `ff68304896ba25e6a429e72926d2837167076c6e832dee3f660acdf2f7c267a6`
- Canonico sugerido: `HOME\Clones\_ECO\Reorganizar V2.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\Reorganizar V2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 79: hash `f5395b68ccb9cdd75c24eb2970828576835f448261c4c269c9ce9d4433301bfe`
- Canonico sugerido: `ACIRV\Notas\250226 - ROTEIRO DE CERIMONIAL CAFÉ ENTRE AMIGOS - Reforma tributária.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\250226 - ROTEIRO DE CERIMONIAL CAFÉ ENTRE AMIGOS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 80: hash `29e6b38480859762a8bd1ebf2f2f3329a03fb2acce6f820eb76ba1f5d9bda20f`
- Canonico sugerido: `HOME\Segundo Cérebro\Imersão de edição de vídeos com IA - Tales Ramiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Imersão de edição de vídeos com IA - Tales Ramiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 81: hash `ed4551529df4461add1d3a351d5000213a71bc5de256e765c46ddda27b453be0`
- Canonico sugerido: `ACIRV\Notas\CERIMONIAL - Café entre amigos 27.11.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\CERIMONIAL - Café entre amigos 27.11.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 82: hash `0b0621e990733efe21aba281d0cfd77dbc304d9a1e519919d5f406b8227c47c6`
- Canonico sugerido: `HOME\Clones\_ECO\Reorganizar V2.3.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\Reorganizar V2.3.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 83: hash `09870197c8c8314ec55edde971a5e4910feb2f66d6358e62edf6291cf6423799`
- Canonico sugerido: `HOME\Segundo Cérebro\Os segredos da mente milionária - T. Harv Eker.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Os segredos da mente milionária - T. Harv Eker.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 84: hash `2f0fcfc02f32672de19e0e24dc8c72d2bc47eb833e6002a1a20f0dc4e7e9af39`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\Lembrar (Contradições finalizados).md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\_ECO\ECO V3\Lembrar (Contradições finalizados).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 85: hash `4d93428cf13d32244278ff009385025b6d03475a4f4fd500bf59e916b3878bd7`
- Canonico sugerido: `ACIRV\Notas\Oficina VITRINE QUE VENDE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Oficina VITRINE QUE VENDE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 86: hash `3f932ecc60ecc735519a42303b0ba990f77c2cc0777026aad0677762cc62a8a3`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 01.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 01.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 87: hash `8ecf3f5ffdf112a8743131c3ac44b7dd12db41efd71eeacbadf1dfc1d8341e37`
- Canonico sugerido: `HOME\Segundo Cérebro\M06 Character Animation.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M06 Character Animation.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 88: hash `e7a4b15953c636b38ed15b719ccf39b8eb9fe2ccefb1e09420d08b79c0a9e500`
- Canonico sugerido: `HOME\Segundo Cérebro\Expressões AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Expressões AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 89: hash `2b345b82e6bb08d096f08ef084107f7d97801f0fed3d56441949a5b6cc7ec00d`
- Canonico sugerido: `HOME\Muad’Dib\00_Cérebro Operacional\00_SCRIPT_PYTHON.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\O Professor\00_Cérebro Operacional\V2\00_SCRIPT_PYTHON.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 90: hash `7b6360f716f9ea9da8623cde7c24463072dc4aec77b84071d7c48f31d3d5176d`
- Canonico sugerido: `HOME\Segundo Cérebro\Script de Vendas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Script de Vendas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 91: hash `db952401d273f0449fb726a3073cfa782ad3bd00110e1ee2d4a018b8e035f8a4`
- Canonico sugerido: `HOME\Segundo Cérebro\Dicas Adicionais do AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Dicas Adicionais do AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 92: hash `9daac28eb283188d4ceef18d502877fc99c49ee637df6b8512367daa6d60ddf2`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 05.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 05.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 93: hash `befd48edf0e46e2b2abd002d30858efe55e6c7248d9c77705345bb04556c4688`
- Canonico sugerido: `HOME\O Professor\00_Aleatórios\como fraqueza dá dinheiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Kevyn Lucas\Outros\Integrados\Como fraqueza dá dinheiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 94: hash `e14256c75df9055a717bbe70c4a28d333601414a41509e0e6b7d71f919c715e0`
- Canonico sugerido: `ACIRV\Notas\PLAYBOOK Cerimonial Café entre Amigos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\PLAYBOOK Cerimonial Café entre Amigos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 95: hash `a3992673e9d8e7ccb80a435d9ad5ff7f4aebc7b8e64b8cb5a917a2c460bc4cbc`
- Canonico sugerido: `HOME\Segundo Cérebro\Capítulo 01 - No qual Marcos teve o sono roubado..md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Capítulo 01 - No qual Marcos teve o sono roubado..md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 96: hash `c49e6d0aba71e1787d7ec98ffcfb209ddb2b0e92e8842e2e05d6a86938a1ac42`
- Canonico sugerido: `ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V2.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 97: hash `fecdf05fd3c281e91d6bfe422e6fbaa2214840796a7d6a9890ab2f8aeb5d02cf`
- Canonico sugerido: `HOME\Segundo Cérebro\Mostre seu trabalho - Austin Kleon.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Mostre seu trabalho - Austin Kleon.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 98: hash `0963c76e1f6cce281fd6e8ca038a623856e436b6ae1d8baecf1b5e46258090dd`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 17.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 17.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 99: hash `100f7498d2afe9a8b7111e4e0dd37616d0710d58e2f5803841357997001dbc49`
- Canonico sugerido: `HOME\Segundo Cérebro\Notas gerais PS - Original.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Notas gerais PS - Original.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 100: hash `07b1e7dc556d024b5c4451949a2f797113a6c1f94ae859dc155d18eb0ad632a9`
- Canonico sugerido: `ACIRV\Notas\GALPÃO DE TAREFAS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\GALPÃO DE TAREFAS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 101: hash `dfb488bd29624c10723490b1221a7b996a32091d44a705bf4e235e5c5dcceff9`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 14.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 14.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 102: hash `ce908cf4a37f7ef60e1a9a4418955bd745bb66ac961477283f88a2aae60b5614`
- Canonico sugerido: `HOME\Segundo Cérebro\Atalhos AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Atalhos AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 103: hash `a034c1fe1887ed40214d3f5a4919cc18305222f5cf85d8290b875ed2bb1cf716`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 16.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 16.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 104: hash `8d68b55d28355dd69cc0e4f8f75a74d7cac01cc5f26d26d93224d685c9fa5221`
- Canonico sugerido: `ACIRV\Notas\Dados sobre o Fórum.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Dados sobre o Fórum.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 105: hash `1df73ca7a1a6a717e2eff669702f885d23fe6343a947d34876b5904f1f9f41f4`
- Canonico sugerido: `ACIRV\Notas\Novo tom de voz 2026.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Novo tom de voz 2026.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 106: hash `2956d70f083e1d8658ec007b1ef9150b4517c7d5a916b0baea927c1cf2cff0ee`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 07.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 07.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 107: hash `403d57572335ca2f8718558f764f62eeed2cbd301e6ebcefb1960427a449c5d8`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Retrospectiva 2025 - Como extrair.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Retrospectiva 2025 - Como extrair.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 108: hash `6ad704b07106d72c28fad9fd6476e2edd04c554fc810fbeebcb4130737ee8c77`
- Canonico sugerido: `HOME\Segundo Cérebro\O que quero retratar com cada carta.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\O que quero retratar com cada carta.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 109: hash `b021eb5d87b67b06e954c81ea8da9744742471e43507c2f7910a216b28ea24a9`
- Canonico sugerido: `HOME\Segundo Cérebro\Arrume a sua cama.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Arrume a sua cama.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 110: hash `214ca4d57c9942ac0b3c29356d4209ce0735c72795d19c5ef39199a191666a55`
- Canonico sugerido: `ACIRV\Notas\(RELATÓRIO MÉTRICAS PARA DIRETORIA) - Janeiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\(RELATÓRIO MÉTRICAS PARA DIRETORIA) - Janeiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 111: hash `2d8f0b2b652c1717bfac9cdd87116163010439648ace5e2c612ea3625c85f420`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 18.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 18.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 112: hash `72a73bcd5405b86482b34bc49cb37dc285e5f59058ef61fba2284a17aff54f7d`
- Canonico sugerido: `HOME\Segundo Cérebro\Hefesto.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Hefesto.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 113: hash `01e607ab33a37e4fdb4ac29e5720ade5084a67c0f53f64ab6f8a45be25f12ee2`
- Canonico sugerido: `HOME\Segundo Cérebro\Cosmo - Software VR de aprendizado imersivo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Cosmo - Software VR de aprendizado imersivo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 114: hash `160dfa5dcc99717ba287bc8dc0094ec850565689f063edce6ca0e7ee85a4c92a`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 03.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 03.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 115: hash `adfe21ef1964a6d9f4c4de3bac557a96de7c62645f8e43d0b23439edcf1c28fd`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 13.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 13.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 116: hash `d5b7781e33b50eb368526a6f36e49c2d266a32c63d9600c56cd1460e11505b2a`
- Canonico sugerido: `HOME\Segundo Cérebro\Do meio fio ao volante.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Do meio fio ao volante.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 117: hash `8d824e9d73d4b955a80c5068805dbd824e2801136cb8c0f0ecc0196969608198`
- Canonico sugerido: `ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V1.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V1.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 118: hash `6e9d324e202e19c86f396c08c43f9e971569f77bc2ba5a3cd81920170429e201`
- Canonico sugerido: `ACIRV\Notas\RELEASE - Conecta Saúde (Pós Evento).md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\RELEASE - Conecta Saúde (Pós Evento).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 119: hash `7e58aed4432dfc1fe5c3cedd5c35eba79d51daffe2b8ee0c9d9d3eaf2160dc48`
- Canonico sugerido: `HOME\Obsidian doc\tudo em um lugar\Prompt Backend.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Para roadmap\Prompt Backend.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 120: hash `51e1d21ab69a3e415cc4d4737d73f9cd3fa2dc1dd026a76f13bbde021aeee74f`
- Canonico sugerido: `ACIRV\Notas\Releaser.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Releaser.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 121: hash `b66714995cc65b8a30a8997a765dfcdd82e635fda8fbd72f0398753f08d5d1c6`
- Canonico sugerido: `ACIRV\Notas\110326 - Insight completo sobre como estou usando meu tempo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\110326 - Insight completo sobre como estou usando meu tempo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 122: hash `1f86a0c02cbb4da3287335ed5e33d1b6608dff5bd81183d997abb1879ff012b9`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 06.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 06.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 123: hash `f216ce06e11caff7715633f122c89bcb677f15c7c08cf6ab1fcb87e8e0d91801`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 04.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 04.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 124: hash `b77b2faa9ab0e2411305bc85c45cbac0223e544f5c1c0d500a2c383f7d148068`
- Canonico sugerido: `HOME\Segundo Cérebro\Neuron - Plataforma de Aprendizado em Inteligência Artificial.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Neuron - Plataforma de Aprendizado em Inteligência Artificial.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 125: hash `3240507190d800f41df4a1511d1ca74d9615149432e992a437aefddc662557a0`
- Canonico sugerido: `HOME\Segundo Cérebro\Apresentação VTI C01 BDI.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Apresentação VTI C01 BDI.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 126: hash `47abfbd7f8fecffb26c394177316c44c3c8e5c513204c97823e15fdfbfb9f255`
- Canonico sugerido: `ACIRV\Notas\Playbook de Releases.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Playbook de Releases.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 127: hash `6c1d52663deee7eeb28b27d6d83fbd8f48a6d8f6b7e58dc41b2ab49d737f0392`
- Canonico sugerido: `ACIRV\Notas\Roteiro de Cerimonial - Seminário Multiplicadores de Sucesso.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Roteiro de Cerimonial - Seminário Multiplicadores de Sucesso.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 128: hash `9663e18439abbad1826e7f5e4c746f2ae9c9482faecdbc5c16d3da26c59f662e`
- Canonico sugerido: `HOME\Segundo Cérebro\Afazeres profissionais.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Afazeres profissionais.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 129: hash `3c837f55a9301468acfa0407696be2b2dd9249ef69e16c0e97417755e269c914`
- Canonico sugerido: `HOME\Segundo Cérebro\Tudo Para Mulheres (TPM).md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tudo Para Mulheres (TPM).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 130: hash `8555b4c5531eed0292e3dd1b0b48a0df0c7ab39fabe4ee1a38914939adffcbab`
- Canonico sugerido: `HOME\Segundo Cérebro\Atalhos Premier.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Atalhos Premier.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 131: hash `db400dbe9470e121ba3e18dd6391c82aead2b0010c5917272bcd3e44d57ce293`
- Canonico sugerido: `ACIRV\Notas\Conteúdos que precisam se repetir em 2026.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Conteúdos que precisam se repetir em 2026.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 132: hash `fb5cba26dffa30b5a181d89c6aae1981a4520a4fc7b4c3bf2a9e0e5f8a1f00a7`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 10.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 10.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 133: hash `7fbd1678a9aaa83496568f37bfe5ea202886378e1fcff341ea53927b4b62373c`
- Canonico sugerido: `HOME\Segundo Cérebro\Ágora.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ágora.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 134: hash `cc8d9051c22c896f2a143f13ea053ab792a4edd27ed36d43f9d1c6679af0ec8b`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Retrospectiva 2025 - DADOS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Retrospectiva 2025 - DADOS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 135: hash `d7d482bb4ff08d5da4551019e892a4317234ec79d3005aa8099443bfbcc27c14`
- Canonico sugerido: `HOME\Segundo Cérebro\ECO - Plataforma de Agentes IA insanamente ótimos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\ECO - Plataforma de Agentes IA insanamente ótimos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 136: hash `8f7e294889d073518874a38c12b81baeebe5e99a454be97a20ccb29e69d324de`
- Canonico sugerido: `HOME\Segundo Cérebro\O Segundo Cérebro Definitivo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\O Segundo Cérebro Definitivo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 137: hash `746539fcf99c1a32233cbe35b68588eab1375924bda08b895e2b50bf142d144b`
- Canonico sugerido: `HOME\Segundo Cérebro\Fale viral.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Fale viral.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 138: hash `7553e7cf11ae0e79b6e50e3e11d7ed5fdacf38473ef505a84b8efb65bf6fa20d`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 08.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 08.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 139: hash `fc11865421f1b7e6889132d02e1eff48c7186f62c04516bf9ca9a13f0dbda77b`
- Canonico sugerido: `HOME\Segundo Cérebro\Contexto.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Contexto.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 140: hash `2dfe24ca8cd3c509f59a4c59491c488375c30393d0ec4ae39fe119ac190c972c`
- Canonico sugerido: `HOME\Obsidian doc\tudo em um lugar\Fluxo MVP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Para roadmap\Fluxo MVP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 141: hash `79ce2ef58287900c0951062a45ab1a07f69704bdbfdd909349eb61410944e55a`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 19.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 19.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 142: hash `002af79c75e98da401f47542e62c421231a68537aa2c76ffed464466f8e04824`
- Canonico sugerido: `HOME\Segundo Cérebro\ReValor - Sistema de Coleta Inteligente de Lixo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\ReValor - Sistema de Coleta Inteligente de Lixo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 143: hash `846c6d2de9f9c1d39de4ecba8faacd012ff42ac0e31cc782b9e6d820f2bef3c3`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 09.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 09.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 144: hash `827c707f540cc0fa9d0a599ecb718ec3661a49a1d61d9effc7df5f0f2b06f76e`
- Canonico sugerido: `ACIRV\Notas\Como melhorar o relatório mensal.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Como melhorar o relatório mensal.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 145: hash `d19821449570de1bc33d557c8c127065416a5883253c37f7aa188662b2e24b55`
- Canonico sugerido: `HOME\Segundo Cérebro\BioVision IA.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\BioVision IA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 146: hash `80421fa7ef65012068e1e9107ee0a8472211fb759bad07bd564a9ac804b0ad07`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 11.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 11.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 147: hash `ab29e01831fe941b02ad49def0a5d5f91554d2ccc19c6447cdf34f38e28610e4`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 02.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 02.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 148: hash `bdfc4db1ec3ae6b97097673b2225c0ab2d1d332494c18472781e7e5448b3fd6f`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 12.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 12.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 149: hash `5635bd301ae75fd04d9a6498bd8ee79ad8555b2a23626f3675cf924512a2fe90`
- Canonico sugerido: `ACIRV\Notas\100226 - Gustavo Lacerda visita IF Goiano.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\100226 - Gustavo Lacerda visita IF Goiano.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 150: hash `039e37e5dbcfe49c4aa709e89640e20b5ed790a014549551dd998e2b51999779`
- Canonico sugerido: `HOME\Segundo Cérebro\Contexto cru.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Contexto cru.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 151: hash `bc948ec1ccf0d30fc659485a3fb63d2ebd587dd8e63168c99e4662eeccbb2375`
- Canonico sugerido: `HOME\Segundo Cérebro\José Ricardo, vulgo ZRD.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\José Ricardo, vulgo ZRD.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 152: hash `3cefdf436271cc6945f9bb12192f9ec2682cfa1ab03bca010db27b44a7dff122`
- Canonico sugerido: `ACIRV\Notas\RELEASE - Conecta Saúde (pré-evento).md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\RELEASE - Conecta Saúde (pré-evento).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 153: hash `00e314b243500a2b5a3e2f911edde422bda44f87a51df5c52cda39ac3c1dfb8c`
- Canonico sugerido: `ACIRV\Notas\Roteiro de Cerimonial - Workshop NR-01 na Prática.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Roteiro de Cerimonial - Workshop NR-01 na Prática.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 154: hash `8bd95de2f209cb1de17a4b8d9751de2d934e9b1443d89016ce2ae117435a05ff`
- Canonico sugerido: `ACIRV\Diário\2025\11 - novembro\25 - terça-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\11 - novembro\25 - terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 155: hash `a0775c8ef0f4713c024881b819524344cd61d7d0999bec832ddec274a6baf3d3`
- Canonico sugerido: `HOME\Segundo Cérebro\Leitura autoral - Escada do Aeon.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Leitura autoral - Escada do Aeon.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 156: hash `3d50077a7ea725df413c2f9134ce0ebf66c41794b96b1b0e62b73d680ddf8358`
- Canonico sugerido: `ACIRV\Diário\2025\11 - novembro\24 - segunda-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\11 - novembro\24 - segunda-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 157: hash `c0a6552268b7d3b03c60ee08371173206c57a4c53d5ff1f765fe60b5480a5458`
- Canonico sugerido: `ACIRV\Notas\Release Fórum de IA.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Release Fórum de IA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 158: hash `7b9f8f2773b97ef883a0eff249c832ff7ca290cbd0e277adc26518e8c7c44238`
- Canonico sugerido: `HOME\Segundo Cérebro\Estudo copas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Estudo copas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 159: hash `591153a090269ccebb1b86b87513093f380fb34836f2663adc7ad5db059e4235`
- Canonico sugerido: `ACIRV\Notas\Output padrão para briefing.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Output padrão para briefing.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 160: hash `2852f41b865602817ad6b21fd3cfac8c3fa10c0856c3e5886b6a85eee7c3a6de`
- Canonico sugerido: `HOME\Segundo Cérebro\Etiquetas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Etiquetas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 161: hash `6d318acfa1d7f954d098706876da91f835f7f39c3c487bbdea2a74beb48e0680`
- Canonico sugerido: `HOME\Obsidian doc\tudo em um lugar\Sugestão de Estrutura do Database.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Para roadmap\Sugestão de Estrutura do Database.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 162: hash `dd3e6077d56bfb159a6bdeeda861aef2bd27a5951e960491429ffe86832461de`
- Canonico sugerido: `HOME\Segundo Cérebro\Pai Rico Pai Pobre.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Pai Rico Pai Pobre.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 163: hash `20f660d712cf3d1581a6e4c3554209d341eb429389138cbd3c58a6d6cd21f786`
- Canonico sugerido: `HOME\Segundo Cérebro\Tarefas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tarefas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 164: hash `b7818fee847d545459b33b44c92386b71b060b5b15e84db6ab5b4f1bd6b6cef6`
- Canonico sugerido: `ACIRV\Diário\2025\12 - dezembro\12 - dezembro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\12 - dezembro\12 - dezembro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 165: hash `a641f69c9a7e6e836046ea9f7ff5f75ff80660bc8fefd1a7a71911e61f1ee646`
- Canonico sugerido: `HOME\Segundo Cérebro\VIDIA.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\VIDIA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 166: hash `e75c5d9f1829c573dfc4bba88412ed85f7b0fb29fa2b5f77265d7cba873d34c9`
- Canonico sugerido: `HOME\Segundo Cérebro\Meu objetivo com o ocultismo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Meu objetivo com o ocultismo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 167: hash `b5acc0d77076c7f981f3f5fbdaaf689ac07533e1e29249016c5998da274bc627`
- Canonico sugerido: `HOME\Obsidian doc\Final\07_Sprint de Produto Ágora.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Finalizados\07_Sprint de Produto Ágora.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 168: hash `490575c87933b799108262091b5ea4fdca88e749e82df0242042b05769e2b67b`
- Canonico sugerido: `HOME\Segundo Cérebro\Livros lidos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Livros lidos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 169: hash `2e7598658a5d81a468cccdf582448f255750abbdd81806b39a033c0e6a1f35eb`
- Canonico sugerido: `ACIRV\Notas\(RELEASE) Seminário Multiplicadores de Sucesso.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\(RELEASE) Seminário Multiplicadores de Sucesso.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 170: hash `9ab32ee16ca1ac3d286a68b8f9fa8033fc6aaa3b0567059f4be794a3db1bbf52`
- Canonico sugerido: `HOME\Obsidian doc\tudo em um lugar\Módulo de Integração com IBGE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Para roadmap\Módulo de Integração com IBGE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 171: hash `637c2c4fce7e5012db91b77fc6c7447b534eadbc92009af2a7b4324300695c0f`
- Canonico sugerido: `HOME\Cérebro Criador\Notas\Em busca da sabedoria.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Kevyn Lucas\Outros\Não integrados\Em busca da sabedoria.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 172: hash `8f42e1c4bc3a192be3f2918dbc53c09a7f7933eba9c565f89a1b6fe47edfdd51`
- Canonico sugerido: `ACIRV\Notas\12 possíveis indicações para o Núcleo de Esporte e Cultura.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\12 possíveis indicações para o Núcleo de Esporte e Cultura.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 173: hash `151b95d589990ded071a7b919f152d71d6a81293427345c21c7d42d1d0466f8f`
- Canonico sugerido: `HOME\Segundo Cérebro\Vídeo sobre rotina.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Vídeo sobre rotina.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 174: hash `d38f454ec919f48a7efe8857d3dd8ca3be5fe6f7e3083fd7959d9cf5a47dcf28`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\01_gestao_dados.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\_ECO\ECO V3\prompt_parts\01_gestao_dados.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 175: hash `37accbf1374ee11a7bfbabfd4205baaadcafc25980b44f95f316dea9c764ddb5`
- Canonico sugerido: `ACIRV\Diário\2025\12 - dezembro\02 - terça-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\12 - dezembro\02 - terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 176: hash `d011afc301622f06000d3b3175a744c5fee96660ee16f087dc8331a216818304`
- Canonico sugerido: `ACIRV\Diário\2025\12 - dezembro\12 - sexta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\12 - dezembro\12 - sexta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 177: hash `169319a2ef6447209d8027ed4e2d48ab853010bb44c6f19f0a08eee46fa9d464`
- Canonico sugerido: `HOME\Segundo Cérebro\Aula com José Amorim - Aula Secreta.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Aula com José Amorim - Aula Secreta.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 178: hash `02b50ff882a6b3cf98f475c885d0748416955b9ebddf2b122d1933b97fd8edd0`
- Canonico sugerido: `ACIRV\Diário\2026\02 - fevereiro\03 - terça-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2026\02 - fevereiro\03 - terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 179: hash `5280707a5b46b477ce0b7210a873481646326ad9aefc372f5b8175334b8df666`
- Canonico sugerido: `HOME\Segundo Cérebro\Storytelling.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Storytelling.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 180: hash `98ec59ed8bb198bbeb00ff1bd351ce86870ed8bcffaa363c8d6857a69eb34958`
- Canonico sugerido: `HOME\Segundo Cérebro\Campanha Panqueca Power.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Campanha Panqueca Power.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 181: hash `de61b696f569b6713b1028c32d7e6b4e6d59e15c0941d8ac9131a08645ba7079`
- Canonico sugerido: `ACIRV\Notas\cronograma otimizado para o dia 110326.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\cronograma otimizado para o dia 110326.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 182: hash `b4d9faa63ff6885d1edbb7ea748817b610ca40875cdabdae4034cfcbc7bc3ae0`
- Canonico sugerido: `HOME\Segundo Cérebro\Atalhos gerais.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Atalhos gerais.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 183: hash `df41e466ed5c50a18c170f159134967d63851269fdcf952a4400c3f41a1a0aad`
- Canonico sugerido: `HOME\Segundo Cérebro\Branding Hoor.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Branding Hoor.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 184: hash `e67e8e96af05603826340b2d8b431490154e29939cc6d8c349df0913278dbded`
- Canonico sugerido: `HOME\Segundo Cérebro\Wemerson Veículos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Wemerson Veículos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 185: hash `6e56b139ce8a56152817e9018ce6af5745c2368e7fddff6465065e650c7052b5`
- Canonico sugerido: `HOME\Segundo Cérebro\Motion V4.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Motion V4.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 186: hash `fe33a0bc4443b9ba25b46898a472a58d83e23595f3c80e37af5fadbaa7abc64c`
- Canonico sugerido: `HOME\Segundo Cérebro\Marcos e Viviane - La Máfia.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Marcos e Viviane - La Máfia.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 187: hash `400f2340966f09e3e4d29b191ae01cc9861aa62c381cf9a4b2592c6c8db261d9`
- Canonico sugerido: `HOME\Obsidian doc\Final\01_Funcionalidades.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Finalizados\01_Funcionalidades.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 188: hash `1f5283be22ea503770ca5554c14f1cc9b64c1ab6988e245718c2ea6720793785`
- Canonico sugerido: `ACIRV\Diário\2025\11 - novembro\17 - segunda-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\11 - novembro\17 - segunda-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 189: hash `41a55e94e0bb5f13c1a809bc6710c3f3a6102fae9995968a2a40fb2653d57fda`
- Canonico sugerido: `ACIRV\Notas\Dados SEMINÁRIO MULTICADORES DE SUCESSO - PARCEIROS DA PCGO (Edição ACIRV).md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Dados SEMINÁRIO MULTICADORES DE SUCESSO - PARCEIROS DA PCGO (Edição ACIRV).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 190: hash `2a7f3f6764e5758d2ca905f8389011330c9b916c67e98cf0400a75234627a3fc`
- Canonico sugerido: `HOME\Segundo Cérebro\A república de Sócrates.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\A república de Sócrates.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 191: hash `533aae1031d1f57ae37f8db214e48c061353a07cd9f6d9640c61c79d40773ac0`
- Canonico sugerido: `HOME\Segundo Cérebro\Ensaio sobre a nova doutrina.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ensaio sobre a nova doutrina.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 192: hash `7f9c8cc5c950408ea4879aaf77104923a4a9526001bd44fbaf5e47e588feb550`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Retrospectiva 2025 - Roteiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Retrospectiva 2025 - Roteiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 193: hash `1c5d5027d8af6075e3f9005da3d725dea504f4e0e776fedfdc1b85024b09b9ea`
- Canonico sugerido: `ACIRV\Diário\2025\12 - dezembro\10 - quarta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\12 - dezembro\10 - quarta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 194: hash `c4e0761d18a69a5ca63375ba4cc9e90576e184f61881cdf29b6d41960aec8f66`
- Canonico sugerido: `HOME\Segundo Cérebro\M02A04 Propriedades da Timeline.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M02A04 Propriedades da Timeline.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 195: hash `46077623f7a0cb451648e92db49494ec2ef47553430f487d483a500051273e60`
- Canonico sugerido: `ACIRV\Notas\Ideia de criativos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Ideia de criativos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 196: hash `6ba9d9b6a89e511d967b00e0ce3bf24c5d453cdb70725f111c73afe1bfd846c8`
- Canonico sugerido: `ACIRV\Diário\2025\12 - dezembro\05 - sexta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\12 - dezembro\05 - sexta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 197: hash `7937203aa9dcaa96068bd615e5d21ddee9cfec9bfa876a9a5a2af7b412314051`
- Canonico sugerido: `HOME\Segundo Cérebro\Pixel Glitch - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Pixel Glitch - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 198: hash `0a3ac682c92f9b49b1569eef32715f72042d5eedb513f37617bfb16f9ae538e7`
- Canonico sugerido: `HOME\Obsidian doc\Final\05_User Flow.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Finalizados\05_User Flow.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 199: hash `df089efaccbfa6dd955dddad5a705d9cc0342dd3ca7767409428b78360791755`
- Canonico sugerido: `ACIRV\Diário\2026\01 - janeiro\13 - terça-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2026\01 - janeiro\13 - terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 200: hash `9f999653cadc86ade3a6e29810d62bacf3e405a85da7951420754f89c97b2a77`
- Canonico sugerido: `HOME\Segundo Cérebro\Introdução a Mentoria do Brites.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Introdução a Mentoria do Brites.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 201: hash `6f7d2f2f3d20d4948c36d1085ba5f85c48eb9e836fbfea1c62b26ff60248c972`
- Canonico sugerido: `ACIRV\Notas\Sobre Certificado Digital.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Sobre Certificado Digital.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 202: hash `083e3417805f9a7a0440864a73f03298be174bd7f6bdfa345ef5672dc3873193`
- Canonico sugerido: `HOME\Segundo Cérebro\Criando um criativo do zero.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Criando um criativo do zero.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 203: hash `079161edc5af60426c25aead0049532d7f626a70d9a1ae93a5a67dd7b3568c2d`
- Canonico sugerido: `ACIRV\Notas\Principais ações da Gestão (6 primeiros meses).md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Principais ações da Gestão (6 primeiros meses).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 204: hash `0b874292395f98c3ac70f24606638a9e6f1faa0a48dbb73b8981cfa8d4f6eac3`
- Canonico sugerido: `ACIRV\Diário\2025\11 - novembro\19 - quarta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\11 - novembro\19 - quarta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 205: hash `f07333f4e7c5a79d103789bd2579c57f97c3c16efd21b4bc3271c1853d779eba`
- Canonico sugerido: `ACIRV\Diário\2025\11 - novembro\21 - sexta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\11 - novembro\21 - sexta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 206: hash `74e2988d521dfbfa9fd8ba8ee835b397c801443c3895c44bf9cff31728bd0b6c`
- Canonico sugerido: `HOME\Segundo Cérebro\Lucas - Só Vidros RV.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Lucas - Só Vidros RV.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 207: hash `bf1f2e48fd5a6463f6a4ebe43c25e9de8a4aabcd88cc1257e3de5439909edafd`
- Canonico sugerido: `HOME\Segundo Cérebro\Tabela de Valores.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tabela de Valores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 208: hash `18cbb16f1f9034ccec380699219840863189fb05b0f3203911526e3de4f5e38a`
- Canonico sugerido: `HOME\Segundo Cérebro\Do sagrado.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Do sagrado.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 209: hash `cd2605bc493d030c4254978d5a6f6569daf7b11f979b3a3fbb7f9762a406320c`
- Canonico sugerido: `ACIRV\Notas\DADOS SOBRE LOCAÇÃO DE AUDITÓRIO.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\DADOS SOBRE LOCAÇÃO DE AUDITÓRIO.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 210: hash `8891d551ebf448e49eb874b593914453d7a396f2f81884a67832dd6498381cc3`
- Canonico sugerido: `ACIRV\Diário\2025\12 - dezembro\03 - quarta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\12 - dezembro\03 - quarta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 211: hash `3eb6998d299fde72c7d2041d8ab2dacc2a9519b3daa84d97bfb8c70627ced538`
- Canonico sugerido: `HOME\Segundo Cérebro\Estrátegias de vendas por AFILIAÇÃO.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Estrátegias de vendas por AFILIAÇÃO.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 212: hash `55ccceeefcf50dada4cce2a618031b4bf6b64d13f410c16e49d5106caee6cf33`
- Canonico sugerido: `HOME\Segundo Cérebro\Gradientes orgânicos - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Gradientes orgânicos - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 213: hash `ac8e902e2281fd5bf86406f28e7c57b4071dd6d87adadca1c6c30e6839d76f90`
- Canonico sugerido: `HOME\Segundo Cérebro\Victor Barros, vulgo Gaúcho.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Victor Barros, vulgo Gaúcho.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 214: hash `69ef4fa1e4c57652db4a5781b4d94494c29e1ed2633012bb163210ab1f061978`
- Canonico sugerido: `HOME\Segundo Cérebro\Repetição Espaçada.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Repetição Espaçada.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 215: hash `02e4bd28d71e8b5144260e06f6da4499c0b5be7c726e369488bc0741c138dda0`
- Canonico sugerido: `HOME\Segundo Cérebro\Acompanhamento de Clientes.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Acompanhamento de Clientes.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 216: hash `9c09d5a600254f022a8fa30325ba1709a74feeecc87e7e04a363648d389ea903`
- Canonico sugerido: `ACIRV\Diário\2026\01 - janeiro\08 - quinta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2026\01 - janeiro\08 - quinta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 217: hash `9a78d19abf0a807a7af8ffdfc4f78d26ecbe06b16c3f16e19032e6040bbb6bb7`
- Canonico sugerido: `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Carrossel Retrospectiva - Simplificado.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Carrossel Retrospectiva - Simplificado.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 218: hash `144fba0cac1c99eabcff411f322456ea9560d0f2b8acaed578f2d6d08f46fe8f`
- Canonico sugerido: `HOME\Segundo Cérebro\O mapa do Faz Mil e Dorme.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\O mapa do Faz Mil e Dorme.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 219: hash `731c1c6c3f6c8ea1780823069f2fb297620bab4174ad263b4bf77db3db05ba70`
- Canonico sugerido: `ACIRV\Diário\2025\12 - dezembro\04 - quinta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\12 - dezembro\04 - quinta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 220: hash `a3c9838ebeda6c38b46af6bc4267f2b06b8b60a476da9d0b440df6910433abfb`
- Canonico sugerido: `HOME\Segundo Cérebro\Minhas 72 faces.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Minhas 72 faces.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 221: hash `910211bf6cbf8bd7ae87b9553dc348411ec458cca5e3d161f0db708a9957751a`
- Canonico sugerido: `HOME\Segundo Cérebro\Aula 02 - Mentoria Brites.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Aula 02 - Mentoria Brites.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 222: hash `ce824e7b78d34b31608fb23d44b9e9ddb40a5fc93c45ab008eef18805d08a591`
- Canonico sugerido: `ACIRV\Diário\2025\11 - novembro\27 - quinta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\11 - novembro\27 - quinta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 223: hash `69eb643de55218bb739b855e2ec6c7eb9d86794c5af5730526528654017299bb`
- Canonico sugerido: `HOME\Segundo Cérebro\Análise de métricas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Análise de métricas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 224: hash `a84a34073afc78cfdb69292d773155c81faed9d3acbf3e0a52198f6bdeb4f31e`
- Canonico sugerido: `HOME\Segundo Cérebro\Roteiro básico dos Hinos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Roteiro básico dos Hinos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 225: hash `54e29d517158e19910c49b38817bb062f14a1b5a02bddd79dda4e44979fca2a7`
- Canonico sugerido: `ACIRV\Diário\2026\01 - janeiro\07 - quarta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2026\01 - janeiro\07 - quarta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 226: hash `562f7048067308faa7c6e914d6da183787f62e6b2fd40a8d0d6189fa06bcae8b`
- Canonico sugerido: `HOME\Segundo Cérebro\Victor Barbosa, vulgo Vitão.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Victor Barbosa, vulgo Vitão.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 227: hash `9c7fbf2cb7304a1df1b098967f449442db8b36e80217334ab5df440c5182bdb8`
- Canonico sugerido: `ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Janeiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Janeiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 228: hash `96760af823751d7146b911d64bdda9c2e4daf227410154a161625905e9506190`
- Canonico sugerido: `ACIRV\Notas\Dados sobre o workshop NR-01 na prática - 120226.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Dados sobre o workshop NR-01 na prática - 120226.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 229: hash `a52f12f81e08c8ebf7d75e1870750dbb107cf11f8e74df5c96af663829ab2d9d`
- Canonico sugerido: `ACIRV\Diário\2026\01 - janeiro\15 - quinta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2026\01 - janeiro\15 - quinta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 230: hash `f690929b17be987bf4bdb66420a181ed0623243998296d5dc64d33c9347a14df`
- Canonico sugerido: `ACIRV\Diário\2025\12 - dezembro\09 - terça-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\12 - dezembro\09 - terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 231: hash `67b0fff6f57d4c6327957ac12c3042a8bc6823a51f149abf3308f37b13e93eff`
- Canonico sugerido: `ACIRV\Notas\Blocos de foco\170326 - Bloco de foco tipo operacional.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Blocos de foco\170326 - Bloco de foco tipo operacional.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 232: hash `b9ff09edcbd31e9ffb506447bdfba43211167cc911cfe124bcd6d61e63b18a29`
- Canonico sugerido: `HOME\Segundo Cérebro\As invocações ao Deus e a Deusa.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\As invocações ao Deus e a Deusa.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 233: hash `7aa905faa39eb7bf952af4d9cda110d394a2f3db901bdf71941a1408ce411416`
- Canonico sugerido: `HOME\Segundo Cérebro\Resposta a Freud.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Resposta a Freud.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 234: hash `a4c685297588a4d5281d1159b304014a1aaa3049e9ad6d4092f3b3192c106c91`
- Canonico sugerido: `ACIRV\Diário\2025\12 - dezembro\08 - segunda-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\12 - dezembro\08 - segunda-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 235: hash `c510decf9e74ead49e1d893f76e3ec9087d73fa1c2eef66dc46186320c5c0c90`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\ECO 2.5 - 00_identidade.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\_ECO\ECO V2.5\prompt_parts\ECO 2.5 - 00_identidade.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 236: hash `0d214418109c089d92b5507a37b59acaf1ed59a20c10e35b78996c1f2517495e`
- Canonico sugerido: `HOME\Segundo Cérebro\CEVC - Rubberhose.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\CEVC - Rubberhose.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 237: hash `c4eb212e8979f8664b90037b02fbbeac614cd31d890327bd6b822832f78b8539`
- Canonico sugerido: `ACIRV\Diário\2025\11 - novembro\11 - terça-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\11 - novembro\11 - terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 238: hash `c3f4d846a5e730d9cd0cb9b740da0ec2ead3819d8e60ff9e5b5ca86a6fac3a06`
- Canonico sugerido: `HOME\Segundo Cérebro\Flávio e Fabiane - Rio Café.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Flávio e Fabiane - Rio Café.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 239: hash `20a10aa5b72ab2a1f97a187278d75231a0c7c947a6ab7dcb209cfbee8aea7fcf`
- Canonico sugerido: `ACIRV\Diário\2025\11 - novembro\14 - sexta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\11 - novembro\14 - sexta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 240: hash `c458d5b508ef5c81daedb3704d2f1de8308a99aa8b3e3098f2170e4f4b78ba2d`
- Canonico sugerido: `ACIRV\Diário\2025\12 - dezembro\29 - segunda-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\12 - dezembro\29 - segunda-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 241: hash `3b2039775320b8556c93e0f8489d5b2038f2e413673a07cf0547d80e5d565e9b`
- Canonico sugerido: `HOME\Clones\ECO - Contexto Completo\00_identidade.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\_ECO\ECO V3\prompt_parts\00_identidade.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 242: hash `54cb0a88b5717c7d52cb7527a3d0fa4d52e5fae12749ef797b4eede74c693564`
- Canonico sugerido: `ACIRV\Diário\2026\01 - janeiro\16 - sexta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2026\01 - janeiro\16 - sexta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 243: hash `957e8493cc2d69e83c4ba392765ffbcc7e3dc6833940898616b00b67275ce6c9`
- Canonico sugerido: `HOME\Segundo Cérebro\Só Notebook.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Só Notebook.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 244: hash `af9e96758229f1cbed2107edab856f38464a40f3136d17ec74602d85c661e94d`
- Canonico sugerido: `HOME\Segundo Cérebro\Luis Barbosa - Lojão do Povo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Luis Barbosa - Lojão do Povo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 245: hash `ac02635d122a817f7c09593510e0f2382776935dd79a272db708960e766f57f8`
- Canonico sugerido: `HOME\Segundo Cérebro\Quero estudar.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Quero estudar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 246: hash `81a260082d31e1e387480178421ecbda7b54b8439ad3da6d17c8675c51418962`
- Canonico sugerido: `ACIRV\Diário\2026\02 - fevereiro\18 - quarta-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2026\02 - fevereiro\18 - quarta-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 247: hash `3ff063eb7b8d8efea5d1a35dca1089e682a70a97907a2135e1e9ebe33f1fea46`
- Canonico sugerido: `ACIRV\Diário\2025\11 - novembro\11 - novembro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\11 - novembro\11 - novembro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 248: hash `2aba8a196943c95b5e7cdeea6d63f2126418516a1d1bc8d2bb88ff3b16bafefd`
- Canonico sugerido: `ACIRV\Diário\2026\02 - fevereiro\02 - fevereiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2026\02 - fevereiro\02 - fevereiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 249: hash `a289ae4c71f097cf32f165a6eb8d40897bdf8e98a9a5305ab912181ccdf235b8`
- Canonico sugerido: `ACIRV\Diário\2026\01 - janeiro\01 - janeiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2026\01 - janeiro\01 - janeiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 250: hash `9f9dba69301ce0852703e405f351aec3a8921135893fb5fa80e55d1fb6fd3c29`
- Canonico sugerido: `ACIRV\Diário\2026\03 - março\03 - março.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2026\03 - março\03 - março.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 251: hash `6213245a51684b7bb35b68143c67452a29e9d756eec826f0eb9ff3b6b4af0ba2`
- Canonico sugerido: `ACIRV\Diário\2025\2025.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\2025.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 252: hash `dad39485def4ab2e900f6ea2874ae2ecb329efe6198ae66313a28aa9639ac2f2`
- Canonico sugerido: `ACIRV\Diário\2026\2026.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2026\2026.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 253: hash `6d732062e15308ae6ddf12befd65ae55407b0bd97b4060515e39dd5b1d16ccaa`
- Canonico sugerido: `HOME\Segundo Cérebro\Padrões de linha orgânica - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Padrões de linha orgânica - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 254: hash `9051253456e65d5308bf3932182f8474bfd48d296d3db9f058b031dd75b55187`
- Canonico sugerido: `HOME\Segundo Cérebro\Como ganhar dinheiro pela internet.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Como ganhar dinheiro pela internet.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 255: hash `302daf47d83d4883ea47030e7e3300d1413d49d21589978844ad467004796404`
- Canonico sugerido: `ACIRV\Notas\Resumo Executivo da Campanha de Indicação ACIRV.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Resumo Executivo da Campanha de Indicação ACIRV.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 256: hash `711e671e3c45de60254b0c38225fd1a58ba9cf3d62719209d935cfd7c564caf4`
- Canonico sugerido: `HOME\Segundo Cérebro\Método Ultra Foco.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Método Ultra Foco.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 257: hash `765e5d9405c5a2f5291f6d36c87255f08f46d94807f6e7d303dec6f4eb310319`
- Canonico sugerido: `HOME\Segundo Cérebro\Latte Art.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Latte Art.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 258: hash `e7bc283901696c1e53a441e364d743ea1847c748e2d42317bfb36d50b1e0b19e`
- Canonico sugerido: `HOME\Segundo Cérebro\Se razão pergunta porquê, a resposta é.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Se razão pergunta porquê, a resposta é.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 259: hash `28d8b2856d7c80a32ad0f6c99519401e0a28fbc1d0068e6f21994d651383fa38`
- Canonico sugerido: `HOME\Segundo Cérebro\Gradientes RGB - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Gradientes RGB - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 260: hash `c4c597a58b0f5b0f3bc54463cac962d2b5a639eb8a71746cb399807d8b616bc2`
- Canonico sugerido: `HOME\Segundo Cérebro\Estrutura de uma Agência de Marketing.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Estrutura de uma Agência de Marketing.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 261: hash `acc3657c507ae14f3ae36a927240ea08ee6be27b0eb46a45c49a23efe9d771d6`
- Canonico sugerido: `ACIRV\Notas\Pedido de criativo de adiamento do projeto sorriso verdadeiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Pedido de criativo de adiamento do projeto sorriso verdadeiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 262: hash `161954208e37054cb9c59c3e715f05fa50efe90d0a1e26d2fc0ab30fe43d797a`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre vendas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre vendas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 263: hash `5038ab758baae3fdfe790590cf6633e2136cb93c82e0231b073065cf649aed83`
- Canonico sugerido: `HOME\Segundo Cérebro\O caminho do Magus.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\O caminho do Magus.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 264: hash `eb89b2df484dc9bbdd33a29aa7972b6e6a423efae1e0f241577b582b8b379e0a`
- Canonico sugerido: `HOME\Segundo Cérebro\Estudo sobre a ritualística Wicca.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Estudo sobre a ritualística Wicca.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 265: hash `62a6cb62a80062b7b442823b46271e21461b0cfddf78e79e17c26212b75e7a2b`
- Canonico sugerido: `ACIRV\Notas\TAREFAS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\TAREFAS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 266: hash `31407a232e3c434005a0abac97d9f02d84d55ba8aef2bbe7c6a1af6caba464e5`
- Canonico sugerido: `HOME\Segundo Cérebro\Bullet Tags.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bullet Tags.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 267: hash `5ba3773a55036fe14f48d9ec9948ea39655a9751ce5d130d573b15f2856dc6b1`
- Canonico sugerido: `HOME\Segundo Cérebro\Bruno Sousa.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bruno Sousa.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 268: hash `67a2f23fc5e373beece25d9f29a50f20980b2dace9eb9dae28fb316ee8e454a3`
- Canonico sugerido: `HOME\Segundo Cérebro\Inspirações artísticas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Inspirações artísticas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 269: hash `5a7be560bcae4eed4fbb88e96edcf9788fedac2aba3584fc482586b4f2f9530f`
- Canonico sugerido: `ACIRV\Notas\181125 - Roteiro Minuto ACIRV.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\181125 - Roteiro Minuto ACIRV.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 270: hash `3d282e24c210a703ca37b1a2704a3d0d3216588c179b2e920ffad7a57a89fc68`
- Canonico sugerido: `HOME\Segundo Cérebro\Atalhos Photoshop.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Atalhos Photoshop.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 271: hash `36342b3e829409db6e70c53c3871446e90db5eb6f92b0fb4cd47a118908dad64`
- Canonico sugerido: `HOME\Segundo Cérebro\Whiteboard.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Whiteboard.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 272: hash `1197899c8ae7caf81a60001a68afe677c7a536f07df869fa23b91cb99b3a4782`
- Canonico sugerido: `HOME\Segundo Cérebro\Como levantar dinheiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Como levantar dinheiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 273: hash `ca6ede986c6608a7e18d3effeb711ecb7d3e6a3f5aa63cb9df164be4fd2ba31a`
- Canonico sugerido: `HOME\Obsidian doc\Final\04B - Mapa de conteúdo USER FIRST.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Finalizados\04B - Mapa de conteúdo USER FIRST.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 274: hash `4f7e6f1ef517e1e9a17836a675f0870503dea9f33984b58f6c25ce6ba810a77c`
- Canonico sugerido: `HOME\Segundo Cérebro\As perguntas do Programa Centelha 3.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\As perguntas do Programa Centelha 3.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 275: hash `4d84260884dc2f6144ea9f99e664ea262903d5e9583a3412916df4689da893a2`
- Canonico sugerido: `HOME\Segundo Cérebro\Links Onion, Torrents e Telegram.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Links Onion, Torrents e Telegram.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 276: hash `b0664024f553327eeb58ec47b3a6a30e4c1bf9322fb39f6d26077032bf50d62e`
- Canonico sugerido: `HOME\Segundo Cérebro\Guia de tarefas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Guia de tarefas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 277: hash `a47657eedad1448bd146a146e675acfd7d3101f19eefdea76aed9cbe489d5bb2`
- Canonico sugerido: `HOME\Segundo Cérebro\Ajustes Essenciais de Cor no Premiere.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ajustes Essenciais de Cor no Premiere.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 278: hash `2eb0f7dbfbbee44e2a8e678fedf38826e501f1d553caa323cf5a90a61be281c3`
- Canonico sugerido: `ACIRV\Notas\251125 - Minuto ACIRV sobre o Conecta Saúde.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\251125 - Minuto ACIRV sobre o Conecta Saúde.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 279: hash `1cbbac40721326732b42da50a0af196b0e418a4f5fe2f6d8eb2b8bbfb310c599`
- Canonico sugerido: `HOME\Segundo Cérebro\Jornada do cliente.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Jornada do cliente.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 280: hash `9e289de1a4b66beeea309f4eaa7f7e10f0a4573ae9c00fe74926dd7b09fd1616`
- Canonico sugerido: `HOME\Segundo Cérebro\Invocação de Cernuno.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Invocação de Cernuno.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 281: hash `334c1f87bc54188433b159ace7ab9cfc43e19b587bc9551af46d58e04e2b73c5`
- Canonico sugerido: `ACIRV\Notas\Como é realizado a reunião de apresentação de Métricas de todo dia 30 - Modelo da Vivi.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Como é realizado a reunião de apresentação de Métricas de todo dia 30 - Modelo da Vivi.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 282: hash `7e0a0796dc19d8891f30416c78e628f4bcde9ab9b412962181115c1913db76c7`
- Canonico sugerido: `HOME\Segundo Cérebro\Gabriele (Solara).md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Gabriele (Solara).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 283: hash `5590f86667e6554bf017ecea451cb4b6a9bf7eff93f2c73a02d00bb39c17c09e`
- Canonico sugerido: `HOME\Segundo Cérebro\Motivo e Estrutura básica.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Motivo e Estrutura básica.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 284: hash `055c7f79003ecaa809ed15b19488607d34a5dd8ccd753f2a4722dea645e37597`
- Canonico sugerido: `ACIRV\Notas\(Desatualizado) Padrão de qualidade do novo tom de voz.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\(Desatualizado) Padrão de qualidade do novo tom de voz.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 285: hash `a612ec6cda2c319870ebd2fa6fdbab1f18c40bdcd6537ad719a259020547c375`
- Canonico sugerido: `ACIRV\Notas\Sonhos de consumo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Sonhos de consumo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 286: hash `f614335ad0a00bc2156e9c522e74033f3cc7b2a1dc3099f0305a5f89276a9ab0`
- Canonico sugerido: `ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Fevereiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Fevereiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 287: hash `c7620fae5f1ec047adffc7c1acb675dd96a91047b6691a73c3eaf42105a3a68a`
- Canonico sugerido: `HOME\Obsidian doc\tudo em um lugar\Insights da mentoria.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Para roadmap\Insights da mentoria.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 288: hash `2f24118056cf6a4942d874cc3fd7db80fed63e97111b2ef977eb1f3e2ab46ba4`
- Canonico sugerido: `HOME\Segundo Cérebro\Certa vez.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Certa vez.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 289: hash `87706156f87d03759ffa0f79a66706e717f02580efb65ef4651def03e8c043e9`
- Canonico sugerido: `HOME\Segundo Cérebro\Logo Thays.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Logo Thays.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 290: hash `1cd576af89a034e009f35485dd01ae425e2fbb1350a3951f496c6eade3bdda44`
- Canonico sugerido: `HOME\Segundo Cérebro\VSL.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\VSL.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 291: hash `e530a5de06af442024fbdebbf81ae78aa199ce069d56b314b7b41b111af288fa`
- Canonico sugerido: `HOME\Segundo Cérebro\Bounce.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bounce.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 292: hash `3c52b5aee7acb3eda704c111c2bf5d275ef7ef32a9f94bd2e8a687889a707fdd`
- Canonico sugerido: `HOME\Segundo Cérebro\M06A02 Organização do personagem no After.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M06A02 Organização do personagem no After.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 293: hash `327d473b29627ee87ab3854cb8eccc67c5865004f8768de1249d0a616d27e0f1`
- Canonico sugerido: `HOME\Segundo Cérebro\Textos, títulos e MOGRTs.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Textos, títulos e MOGRTs.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 294: hash `46d5b279bf3ceed8e03b042add7c899cbc9aef83df2667af7f228a07ecf62791`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre Designs Minimalistas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre Designs Minimalistas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 295: hash `f3a5682ebc883dbb676e3be60b21725487e8df6aedef30cb85135c0ea25a7325`
- Canonico sugerido: `HOME\Segundo Cérebro\OZI - Detonando no After Effects.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\OZI - Detonando no After Effects.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 296: hash `86ef3501a19fc31d1d403f344f17ee139d523e2fda812a55a64c512790119245`
- Canonico sugerido: `HOME\Segundo Cérebro\Advanced Spill Supressor.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Advanced Spill Supressor.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 297: hash `9982075449830c42a69ba6d6a800e25f5912639e786c4507f36ca82be5f0ef93`
- Canonico sugerido: `ACIRV\Notas\Sobre assessoria de imprensa.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Sobre assessoria de imprensa.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 298: hash `526973ba33e8619e30c9b037401b6633a95a17999bdf03c5e6f582b2bd1e0fa0`
- Canonico sugerido: `ACIRV\Notas\Planejamento Interno - Kevyn.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Planejamento Interno - Kevyn.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 299: hash `c6ac45dd1335b57d7823cf5687d964d890c2a0805ebc389faacf2f00d3f4c475`
- Canonico sugerido: `HOME\Segundo Cérebro\M06A05 Variações da puppet tool.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M06A05 Variações da puppet tool.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 300: hash `5e5f604c2d5540f0cbad5723c5481194b165218ef5d48c278a722d555007ed2d`
- Canonico sugerido: `HOME\Segundo Cérebro\I wish you where Here.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\I wish you where Here.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 301: hash `6021f9e439bb05429320faeb015de9124f8aa9fa42c7c9a196698a0e86656afc`
- Canonico sugerido: `ACIRV\Notas\Idéias de conteúdo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Idéias de conteúdo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 302: hash `2ad1939855df05197a82c00c2d5a75d555082451edafb56982e342db95cc8112`
- Canonico sugerido: `HOME\Segundo Cérebro\Explorando a Timeline.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Explorando a Timeline.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 303: hash `148edf4ef6b8c1032e3aaf75d31aa382a425c032b705f8957ae8d5b90015f491`
- Canonico sugerido: `HOME\Segundo Cérebro\Análise SWOT ou FOFA.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Análise SWOT ou FOFA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 304: hash `06d545b377f7cf6ea9c1e5ee0391b4b17a633cc068f6608df6d3dd7b5ba1fba0`
- Canonico sugerido: `HOME\Segundo Cérebro\Criando uma campanha simples para afiliados.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Criando uma campanha simples para afiliados.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 305: hash `aae841a65ac612b6417a88c15c5d4f597915271abc5c4e2999f09a0084bf4fe0`
- Canonico sugerido: `HOME\Segundo Cérebro\Gustavo Carletto, vulgo Gustavim, vulgo Guga.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Gustavo Carletto, vulgo Gustavim, vulgo Guga.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 306: hash `fc55381df39d617f5017a091de0ae3dda4561540fbdb710e809df847e9dcce30`
- Canonico sugerido: `HOME\Segundo Cérebro\Estudar e fazer isto 13.04.25.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Estudar e fazer isto 13.04.25.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 307: hash `90a5828f67d2b0722e419380be50d624a27015adf687808bb6b0414ffe3cd7b8`
- Canonico sugerido: `HOME\Segundo Cérebro\ELAMOR.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\ELAMOR.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 308: hash `16429e5c655c57054b275cf829b61f6cd18f6c1a165ecc23daccc2b92c84d20d`
- Canonico sugerido: `HOME\Segundo Cérebro\Conforto gera fraqueza, desconforto gera força..md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Conforto gera fraqueza, desconforto gera força..md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 309: hash `c48dde831bea0b5470a24bab29411ecb4707f721fbdb81d3bfc3ab62fcf456c8`
- Canonico sugerido: `ACIRV\Notas\MINUTO ACIRV - Lara Dutra faz chamada para o Conecta de Março de 2026.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\MINUTO ACIRV - Lara Dutra faz chamada para o Conecta de Março de 2026.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 310: hash `6b1852cfe292a6194db15207425aaf8d140122288ae6e23ad238bfe923fff58e`
- Canonico sugerido: `HOME\Segundo Cérebro\Cultura.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Cultura.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 311: hash `f9912e4cb5a5cea07a8e4d9395e3be69766b19e4f2b7499454122e22c5233d65`
- Canonico sugerido: `ACIRV\Notas\Dados solicitados pela Vivi.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Dados solicitados pela Vivi.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 312: hash `19f977deb081c2dd75bf5424cf79bf559d2491ef47dae08552e4b2784d78267d`
- Canonico sugerido: `HOME\Segundo Cérebro\Como configurar um PC para trabalhar.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Como configurar um PC para trabalhar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 313: hash `c22a736a28d5e7017937abab76d93d5d993c5b47d02133b65973b19464d0d93d`
- Canonico sugerido: `HOME\Segundo Cérebro\Efeitos visuais DAP 2.0.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Efeitos visuais DAP 2.0.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 314: hash `1ae44ea741b334c94c92dcb032e9d63d6306dc6a2eb3ad3d48a82c58e8f01d71`
- Canonico sugerido: `HOME\Segundo Cérebro\Cursos profissionais.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Cursos profissionais.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 315: hash `cde00309629b95f30c88e3dd99e065e33de1d6101691c2c22c258ba4bdeedeef`
- Canonico sugerido: `ACIRV\Notas\Lovable\Dashboard.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Lovable\Dashboard.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 316: hash `1021810e256f10c667f427afd2a3426f7f51d242d9edf78257b091b1e157a198`
- Canonico sugerido: `HOME\Segundo Cérebro\M02A03 Opções de Preview.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M02A03 Opções de Preview.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 317: hash `d860ee6c38d4fe3484ccd4e6f67487e8ec53dad200dd13daede3791432624552`
- Canonico sugerido: `HOME\Segundo Cérebro\Animação de Logo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Animação de Logo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 318: hash `9a0d0e0e12e8fb0fc1a90c873b157929a997d7402f422ba49cb9ec416bcdf56b`
- Canonico sugerido: `HOME\Segundo Cérebro\Infográficos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Infográficos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 319: hash `7c84ed4c5ad8cc27f29a72142498afc462651c3ee2a7e4161bfb27685d0b5faf`
- Canonico sugerido: `HOME\Segundo Cérebro\Multiplique a velocidade que você produz uma animação com o Plugin Motion.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Multiplique a velocidade que você produz uma animação com o Plugin Motion.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 320: hash `2d106ff91261951429168a31a73bbc41ebe773be5cc1f569fa8aa9342a9f6a1f`
- Canonico sugerido: `HOME\Segundo Cérebro\Afazer 05.05.25.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Afazer 05.05.25.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 321: hash `78d2cc0d9234c7b67d9ce0f29c38dff7eba532c64ea009c7c2453796c5e1acc5`
- Canonico sugerido: `HOME\Segundo Cérebro\Melhores LLMs para mim.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Melhores LLMs para mim.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 322: hash `d8195bcb87150c999d21404471fea31c974c800322f8554470de0850107293c1`
- Canonico sugerido: `HOME\Segundo Cérebro\Zettelkasten.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Zettelkasten.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 323: hash `26df42b565c143859ba77cf1cd5bbe7eedeaa8d4c21f15f880f8b46c26936f3c`
- Canonico sugerido: `HOME\Segundo Cérebro\Do meu livro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Do meu livro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 324: hash `9cfba9412f3d66a364372d86e5765cc564d671667bc8e00ed96db513d87026d5`
- Canonico sugerido: `HOME\Segundo Cérebro\Livro de Toth.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Livro de Toth.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 325: hash `77f4ec9a880bbe83199c62d856b5c6bc97c208a13a5e9383f7f9b5e90ce25465`
- Canonico sugerido: `HOME\Segundo Cérebro\Desenho de letras - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Desenho de letras - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 326: hash `e20e5a8bc7829067862648b50daa315c587694e03828aa701ae7afbfa492c661`
- Canonico sugerido: `HOME\Segundo Cérebro\Ensaio sobre Modus Operandi.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ensaio sobre Modus Operandi.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 327: hash `c71a541c5df5e627121a800f25be5f4a7c5d21280d7e4e5f42a2098afe26feaa`
- Canonico sugerido: `HOME\Muad’Dib\00_Dataview e Tasks\dataviewjs.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\O Professor\00_Dataview e Tasks\dataviewjs.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 328: hash `29da42af1f954ca767422c92f549bbf7601caa8ab889d44cc915e6cfb91f4af4`
- Canonico sugerido: `HOME\Segundo Cérebro\Segmentação RTQ.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Segmentação RTQ.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 329: hash `e6ba5cbd3d9152487863a0216318bf477598150f9f593a3ed92925299116ef86`
- Canonico sugerido: `HOME\Segundo Cérebro\Tarefas padrão do Dia 01.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tarefas padrão do Dia 01.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 330: hash `70c975ace674080f7455affb0bf4054a4a5a06725e436316f618e417ea5beeaa`
- Canonico sugerido: `HOME\Segundo Cérebro\Gráfico de Velocidade e Valores.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Gráfico de Velocidade e Valores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 331: hash `e529a0e105de30788ed72f5ae219b47dffda2a51d06c83b6d3816631ec39524c`
- Canonico sugerido: `HOME\Segundo Cérebro\Configurações e Boas Práticas de Render.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Configurações e Boas Práticas de Render.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 332: hash `15f467e77999440ce51fa6d7ae4d78081ac7c4008b0077c546315d576b065a90`
- Canonico sugerido: `HOME\Segundo Cérebro\Integração Pr x AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Integração Pr x AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 333: hash `b56ba14f2fbfa1237455f0a6d86bdc17a8bfde593c18ef43a722a53c219278c4`
- Canonico sugerido: `HOME\Segundo Cérebro\Introdução ao Liber Hoor.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Introdução ao Liber Hoor.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 334: hash `5cc610705b0d19a2218dcefe4a2ba87e4b272728fcfc3c513f4b181db5bb2666`
- Canonico sugerido: `HOME\Segundo Cérebro\Otimização do fluxo de trabalho no AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Otimização do fluxo de trabalho no AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 335: hash `68cfba939629046396d23512a3235ccb96a205b7d15aa48c3b47e42a8506cf24`
- Canonico sugerido: `HOME\Segundo Cérebro\Hoor, um sonho.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Hoor, um sonho.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 336: hash `9b013138e4ca04533ef82047cea799ae84bc8a0d6569f171b308d3c267436616`
- Canonico sugerido: `ACIRV\Diário\2025\11 - novembro\18 - terça-feira.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Diário\2025\11 - novembro\18 - terça-feira.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 337: hash `4d3ab5aa998d12ee1eca999b083057a76ca65168e631172b5a9706bd03062760`
- Canonico sugerido: `HOME\Segundo Cérebro\Anotações Gerais C4D.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Anotações Gerais C4D.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 338: hash `fb5c95cb47f44d8814db85dda591a7ab690d7536d8ebcc5d6812f8cc9e463f7d`
- Canonico sugerido: `HOME\Segundo Cérebro\Eu amo Vendas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Eu amo Vendas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 339: hash `a1be6a0d0b363a6126bea2c15725ba8f1c03799c68d0c531b368fa35d613dbc3`
- Canonico sugerido: `ACIRV\Notas\Sobre o Happy Hour do dia da mulher.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Sobre o Happy Hour do dia da mulher.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 340: hash `db33aa02c358ba46b021e7285a624fbfdc7084a53bf50fc0a0d3f6bdbf281401`
- Canonico sugerido: `HOME\Segundo Cérebro\Camilla.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Camilla.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 341: hash `fe062c12f04786c27772ad509f6004159c75e85820903b5b8e4c2ad328fbc10e`
- Canonico sugerido: `HOME\Segundo Cérebro\Alternar Modos com Enter.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Alternar Modos com Enter.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 342: hash `b2910c5676ef5ec9b1f7abbe42744b6436241778bc716dd227a97c0387ab03e6`
- Canonico sugerido: `HOME\Segundo Cérebro\Bruxaria Hoje.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bruxaria Hoje.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 343: hash `cdf0d7d4bae372d4a378294d78817b80c6098c8b7db1ccdb334bc10fd4788d79`
- Canonico sugerido: `HOME\Segundo Cérebro\Alpha Channel e HDRI Invisível.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Alpha Channel e HDRI Invisível.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 344: hash `67bb34bf4b49a012fde9dfdda3302211d0128073802c4a70c12ffbf440d08b1b`
- Canonico sugerido: `HOME\Segundo Cérebro\Como melhorar.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Como melhorar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 345: hash `7aaf8144a39336d7d4775102894587d8d55cdc1c5ffabf4bf10ece191757ddad`
- Canonico sugerido: `HOME\Segundo Cérebro\Insights sobre Google Ads e Afiliação.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Insights sobre Google Ads e Afiliação.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 346: hash `ae8895e3ce455804f629a70e53aea7017fb5805a35169c084050c854cb8d0d07`
- Canonico sugerido: `HOME\Segundo Cérebro\Aplicando uma textura que baixou da internet.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Aplicando uma textura que baixou da internet.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 347: hash `5f9151d507770576b8f74326bdbbdfe060bb6e109dfb175ff69ac64c26487e38`
- Canonico sugerido: `ACIRV\Notas\Dicas do José Carlos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Dicas do José Carlos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 348: hash `bc12c472969dfb4dfdb7184fde5c4a5d8cded6873d948ddc75e833e19dca408d`
- Canonico sugerido: `HOME\Segundo Cérebro\Efeitos visuais no PS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Efeitos visuais no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 349: hash `9be4c34e52d62ac2b8089160e8bbaed06b0c1106bfe350305cf4631d55e4c7d5`
- Canonico sugerido: `HOME\Segundo Cérebro\Técnicas e truques no PS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Técnicas e truques no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 350: hash `0e7650180d5eaee195289e73e40eb906e7f3703287a87a66480b0819d9209351`
- Canonico sugerido: `ACIRV\Notas\Lovable\Figma + Lovable.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Lovable\Figma + Lovable.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 351: hash `25346c93f4108b7833c072038fda24f4718ebd59fd3f2000c62ba9db8ecc1a4c`
- Canonico sugerido: `HOME\Segundo Cérebro\M02A07 Importação e Gerenciamento de Arquivos.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M02A07 Importação e Gerenciamento de Arquivos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 352: hash `09bd76f196ba9487d82f122b0da3b5f828c4193f44e943136db6dfa70720068a`
- Canonico sugerido: `HOME\Segundo Cérebro\Pendulum.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Pendulum.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 353: hash `9e5a16ffc484eb8f5149ee2001e15cce333bfb918c8a31426f8f16559397dce5`
- Canonico sugerido: `HOME\Segundo Cérebro\Ambient Oclusion (AO).md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ambient Oclusion (AO).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 354: hash `24daa8fd7f442168263122680485a31bea006e3f185714d1ee77c9a46f9b3fa9`
- Canonico sugerido: `HOME\Segundo Cérebro\Composição e elementos no PS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Composição e elementos no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 355: hash `cda90cc6e7cacb6e1b58c93ff65d687a19db8e92fda1508f2a6f9efe7ab1e30c`
- Canonico sugerido: `HOME\Segundo Cérebro\M03 Ferramentas básicas de animação.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03 Ferramentas básicas de animação.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 356: hash `435e2a22fd6744277afd09df68a8858dda2fa94d4343b4c652fba9228a7492be`
- Canonico sugerido: `HOME\Segundo Cérebro\Afazeres espirituais.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Afazeres espirituais.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 357: hash `6b101017cea66c8ec71d9445f480c8316339db8bdb7c2d45c38d789112f8903c`
- Canonico sugerido: `HOME\Segundo Cérebro\Personagem Básico.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Personagem Básico.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 358: hash `73e148dce59c471dfa9bd87b9d149ab09b367194b3bcc14f9a3a39c96236a6b5`
- Canonico sugerido: `HOME\Segundo Cérebro\Teoria do Bullet Journal.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Teoria do Bullet Journal.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 359: hash `c49b83897c807ebf96beb2b42fd2a26a5b2c88bdbc2835ea3178d5e36a4f8b14`
- Canonico sugerido: `HOME\Segundo Cérebro\Exportação em EXR.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Exportação em EXR.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 360: hash `23b22aa0f8653f756fc73e6aaa3471c070194b892ca59e1bd578661b7e33090a`
- Canonico sugerido: `HOME\Segundo Cérebro\Beethoven Vírus.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Beethoven Vírus.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 361: hash `5e5e94534496899d777eb3eb7e1dcd18b428f52105558a883e62027e36d6c7bb`
- Canonico sugerido: `HOME\Segundo Cérebro\Marketing 4.0 - Philip Kotler.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Marketing 4.0 - Philip Kotler.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 362: hash `612c79fef0f5faeb30d125730b433e5f6f75d6987dcbc9642192d09e41a03ee5`
- Canonico sugerido: `HOME\Segundo Cérebro\Cores, luz e mesclagens no PS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Cores, luz e mesclagens no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 363: hash `6bbdda31c747c1c6cd7a04eaa835642c55506e7d12ea51ba5fba3c4e7ddd70ca`
- Canonico sugerido: `HOME\Segundo Cérebro\Vilmar e Fausto - Fit Station.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Vilmar e Fausto - Fit Station.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 364: hash `df59bfc18ab7dfb34f2e768ab6c1223236b2282067751b324174370a60f7f8b4`
- Canonico sugerido: `ACIRV\Notas\Sobre o relatório do dia 30.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Sobre o relatório do dia 30.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 365: hash `cd1de1d68113129765935e9bf0b1a79b9f8aaac771770b081b1d759f95d255e3`
- Canonico sugerido: `HOME\Segundo Cérebro\SeedRandom().md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\SeedRandom().md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 366: hash `1eb71cd15604f22c08f09d3f63a9d99d1251ce5b1c636be85c450c2ca65ba1ab`
- Canonico sugerido: `HOME\Segundo Cérebro\Liber Vendas, uma introdução.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Liber Vendas, uma introdução.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 367: hash `a853fe996d47ddffc62b9a227c0ac7b8871acca6c55c83b5a5a6b9fcf32fb5e3`
- Canonico sugerido: `HOME\Segundo Cérebro\Kinectype.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Kinectype.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 368: hash `8b3ef6f7492729eddaf94239b48a6adb671608f132affec087f9982063f5660a`
- Canonico sugerido: `HOME\Segundo Cérebro\M06A04 Puppet Tool.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M06A04 Puppet Tool.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 369: hash `71b5195535e15928009a41453b798843ea071face82a54110c42965d08d1760c`
- Canonico sugerido: `HOME\Segundo Cérebro\Hans Muller.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Hans Muller.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 370: hash `124f4933743536212407eab6172c0007bf54d14a15c572eb437204392fcae4b6`
- Canonico sugerido: `HOME\Segundo Cérebro\PORQUE FAÇO.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\PORQUE FAÇO.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 371: hash `1b5ef6c1cbb337fb45c3a4b424e50232b77f969ae0a4687f3f77cf130764152e`
- Canonico sugerido: `HOME\Segundo Cérebro\Dominando o Adobe Premiere 2.0.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Dominando o Adobe Premiere 2.0.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 372: hash `c57bd5990dacc242ef27cd1b840798a32243171c442460e1860ab6aa5c46cdb6`
- Canonico sugerido: `ACIRV\Notas\050126 - Carta a Vivi.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\050126 - Carta a Vivi.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 373: hash `59175c3ab187542a70635ec348d69f3dd13d3b1b62ce43d96e2c6ed96cf14f4d`
- Canonico sugerido: `HOME\Segundo Cérebro\Ducking.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ducking.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 374: hash `0e3d63d3c270fde103fbb8c6acf8e834e17c480047a3b57fd7bd09ccd144bfec`
- Canonico sugerido: `HOME\Segundo Cérebro\Missão, visão e valores.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Missão, visão e valores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 375: hash `d7b8cbc354548b605d234ae183a9b4a0df5698e0cc0addbfbc36e00feaf3ddc2`
- Canonico sugerido: `HOME\Segundo Cérebro\Typewriter, texto e elementos em curvas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Typewriter, texto e elementos em curvas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 376: hash `b55580b664245b131b3dc637e3a29341726438a99064faada74deea755bb2f2e`
- Canonico sugerido: `HOME\Segundo Cérebro\Keylight.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Keylight.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 377: hash `5d088b5a3586c1f1f023daba37016fea2077feb611c284ea5f5e2d33c65e0df5`
- Canonico sugerido: `HOME\Clones\_ECO\Reorganizar vários ECO's.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Clones\ECO - Contexto Completo\Reorganizar vários ECO's.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 378: hash `c6ea529a801abbd81f1a5d550808d8e0c7b999f5af9e374a5f73242a3000ffe9`
- Canonico sugerido: `HOME\Segundo Cérebro\Efeito Parallax Rig.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Efeito Parallax Rig.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 379: hash `7be9d9c69ac8a0d464e44247fa76700bc2bbead481bb6b5b754e4c1dd0d2e152`
- Canonico sugerido: `HOME\Segundo Cérebro\Primeira campanha.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Primeira campanha.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 380: hash `0964348d2942d5e632918a796ddffe740b6932a3c93884f676207682d3f1ce56`
- Canonico sugerido: `HOME\Segundo Cérebro\Redação.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Redação.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 381: hash `cc19f1b543eadf9e13a981b92d94ab3413b944220422f26dff4a358e6d0957a9`
- Canonico sugerido: `HOME\Segundo Cérebro\M06A01 Organização do personagem dentro do illustrator.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M06A01 Organização do personagem dentro do illustrator.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 382: hash `cae11fd13df27708ad2e37ad4ac98f970c8abf464d3b7463e24f13b9af0ef03f`
- Canonico sugerido: `HOME\Segundo Cérebro\Paulo Vespúcio.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Paulo Vespúcio.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 383: hash `0bab6b2241f76508963a3e0c404d5e4f52d80d4d3205564fbf1ca22a5ee7ac9b`
- Canonico sugerido: `HOME\Segundo Cérebro\Criatividade e Processos no PS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Criatividade e Processos no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 384: hash `a2807ba37b9ab39f98dcf8b9b897f913bc9f5d55ad57dfcb1f22ab41c12b0cb3`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre Fields.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre Fields.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 385: hash `68f983063b5d2562d1d3181b0b8635b8612ac195acb5d421e751225b078c76b5`
- Canonico sugerido: `HOME\Segundo Cérebro\Atalhos Illustrator.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Atalhos Illustrator.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 386: hash `cffc68282461b698215fa64cc4d22260e3a4aa435e7913c3c5f0187469a6c503`
- Canonico sugerido: `HOME\Segundo Cérebro\Efeitos Visuais.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Efeitos Visuais.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 387: hash `e350442e4d4bc47873065235062a7e2d88bd0df693aedb718ef0b41a9dd5086d`
- Canonico sugerido: `HOME\Segundo Cérebro\Fx AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Fx AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 388: hash `bf0f26d5e7c3e68f5b2f0e43cd2d3a9338d04c504c8e4116e1c459a44c542d26`
- Canonico sugerido: `HOME\Segundo Cérebro\36daysoftype.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\36daysoftype.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 389: hash `011928e3e058400ac7f04d67d4b6e2d84bbbaa72bcc1c492e912e129824914db`
- Canonico sugerido: `HOME\Segundo Cérebro\Tarefas padrão do Dia 02.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tarefas padrão do Dia 02.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 390: hash `2893dd93f3b7db8cb8c19a0138ea005feb00f3ed380ca1440cefc4c62171c528`
- Canonico sugerido: `ACIRV\Notas\Melhorando a IA redatora.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Melhorando a IA redatora.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 391: hash `6e71398552576592f42c564c6365076ac6c26275351189cecad06a1c585f67c3`
- Canonico sugerido: `ACIRV\Notas\110326 - diagnóstico da atual gestão do tempo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\110326 - diagnóstico da atual gestão do tempo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 392: hash `9a119ab39bf4c431fab181d1d259fe288c16988d3124f7461a850fa96d09cda6`
- Canonico sugerido: `HOME\Segundo Cérebro\Simulate tags.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Simulate tags.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 393: hash `69a4a85aaee58c3990e3f58e2ebad61da0c99ea066769f82a96a383a6ea405a4`
- Canonico sugerido: `HOME\Segundo Cérebro\Variáveis de Loop.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Variáveis de Loop.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 394: hash `f77e80a35dcd893962fd50e9ff3c2c1fe3838ce5c4025cc6e0e1396635b89a4e`
- Canonico sugerido: `HOME\Segundo Cérebro\Substituição e Efeitos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Substituição e Efeitos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 395: hash `1f7589150f9173ea00b3df87f9afac62be2dd64206d1a767f651e38f03af75d6`
- Canonico sugerido: `HOME\Segundo Cérebro\Vertex Map.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Vertex Map.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 396: hash `75e65c5c3e212bb5dfd20c6acefcac4c66d22a78452ee651f604bf873326bd02`
- Canonico sugerido: `HOME\Segundo Cérebro\Os melhores produtos transformam o cliente.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Os melhores produtos transformam o cliente.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 397: hash `580c4d935dd98671e0bfa17a9446b020e136484847729cd13578a441e813b0db`
- Canonico sugerido: `ACIRV\Notas\300126 - Pedido do Raphael.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\300126 - Pedido do Raphael.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 398: hash `1ce90a56b94b0a519d93534accfccefef8561aea0b4ac44f1b1f35f852867f19`
- Canonico sugerido: `HOME\Segundo Cérebro\Capítulo 02 - O circo de gatos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Capítulo 02 - O circo de gatos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 399: hash `3699cbfb9e4a4d78149ad09c923060450e6437d84e8e0735033c6d5d7a5fa6b6`
- Canonico sugerido: `HOME\Segundo Cérebro\Liber Hoor.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Liber Hoor.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 400: hash `56d8bebcccda0e929d8982a86ed4a05bd81607db6db93b13f3498910fcdc02ed`
- Canonico sugerido: `HOME\Segundo Cérebro\Como transformar qualquer logo em 3D.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Como transformar qualquer logo em 3D.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 401: hash `e521365e65210fa634aa5502cd115115e1300f10fde4a86c7165fd25dbc7693a`
- Canonico sugerido: `HOME\Segundo Cérebro\M06A06 Refinamento da animação usando expressões.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M06A06 Refinamento da animação usando expressões.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 402: hash `2fcd3996d06548a3218fab3f1cb90c4248b5b90f4ea8a03ac6f25442020a6051`
- Canonico sugerido: `HOME\Segundo Cérebro\Estou lendo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Estou lendo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 403: hash `984dbc6c58fa7ec076062c1b094ade25a8447d0bf7f7504fd97145f99206215f`
- Canonico sugerido: `HOME\Segundo Cérebro\Organização e Fluxo de Trabalho no PS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Organização e Fluxo de Trabalho no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 404: hash `a6aeaad862394ae74ca8903aca3d73ff5a2b2bcfcbc44ebac31bbd5a8170fb42`
- Canonico sugerido: `HOME\Segundo Cérebro\Treinar isto....md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Treinar isto....md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 405: hash `c5f73db9e9365015e8c1877a2cff99927105cb5c609c98b935a787ef4c50bef4`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A14 Como animar máscaras.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A14 Como animar máscaras.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 406: hash `1074a65e44473ff1a796d4b273142cfa3ab99da68723c2c87e352201fb834b61`
- Canonico sugerido: `HOME\Segundo Cérebro\Meus serviços.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Meus serviços.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 407: hash `ab965cd94263e7b9a98fb996b77eb3eb47635404d508d158832181cfbfb0205c`
- Canonico sugerido: `HOME\Segundo Cérebro\Manipulação de Camadas e Cores.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Manipulação de Camadas e Cores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 408: hash `d5641e772cfa1d66c099db3f2f8a2168c1a105cb9f06ec426d140db6466f017f`
- Canonico sugerido: `HOME\Segundo Cérebro\Atalhos de Seleção.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Atalhos de Seleção.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 409: hash `b3aa6000c3786ab90d8f2fae9c52f75868290901c6fea6f3e786c9a374dd057d`
- Canonico sugerido: `HOME\Segundo Cérebro\Contas de Contigência.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Contas de Contigência.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 410: hash `d08e4bb752d33cd943dbd2adc8e43a13491afd87925b9cc1958e26318ab0a682`
- Canonico sugerido: `ACIRV\Notas\Lovable\Como copiar qualquer site.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Lovable\Como copiar qualquer site.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 411: hash `342b3d2de719d41f41a2d3b2af2506fa9c47cea41cf02c0d0f1ea930707466e0`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A09 Trabalhando com offset e fill.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A09 Trabalhando com offset e fill.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 412: hash `29fa7d2978b9de0442d79674f9b821bed79ac5277af588c7abdee00e20d31e07`
- Canonico sugerido: `HOME\Segundo Cérebro\Metas Financeiras.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Metas Financeiras.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 413: hash `2c7115cccdec801e4c017f5d0a6362776752c6b16dcfb6e7d5048c2f1d4bf08f`
- Canonico sugerido: `HOME\Segundo Cérebro\M05A06 Tracking.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M05A06 Tracking.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 414: hash `ea9141658be074c2e2d5989d58fdf59a4b60dbc69e882ab2970e396f0e776fd5`
- Canonico sugerido: `HOME\Segundo Cérebro\CEVC - Adobe After Effects.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\CEVC - Adobe After Effects.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 415: hash `a5ed2f91db31b991f9504ddaacb7875713c1952a00af0f25139a1cebab16814e`
- Canonico sugerido: `HOME\Segundo Cérebro\Emitter.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Emitter.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 416: hash `5aeab3a7618a05044a1b893e89935581708b4c9ba5d36b7718360c53de11001d`
- Canonico sugerido: `HOME\Segundo Cérebro\Notas e ideias sobre After Movie.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Notas e ideias sobre After Movie.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 417: hash `2f8eee03ec1c55189dd67ce112d83c0b95b12d651fc1ff71d1a413d0cde555f0`
- Canonico sugerido: `HOME\Segundo Cérebro\Tracking, Exportação e Shadow Catcher.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tracking, Exportação e Shadow Catcher.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 418: hash `dd96fe37fbb8482b09901504734a6fdc0d15b76d63c72b82cee2b52396e855a4`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre texturizar o Pyro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre texturizar o Pyro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 419: hash `4801bb16d197b07fe1374b0108124772691d1db996f81bb788873b7b5ba133db`
- Canonico sugerido: `HOME\Segundo Cérebro\Poética de Aristóteles.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Poética de Aristóteles.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 420: hash `eb9e5680248c0b9c7d36540f4996afd7789d1e7d785af61c89d995a390704f31`
- Canonico sugerido: `HOME\Segundo Cérebro\Forças.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Forças.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 421: hash `37ada769e25da734cc77b434cd091e5b48255dfc2e3f6d553dd12e02e1c19eca`
- Canonico sugerido: `HOME\Segundo Cérebro\Dope Sheet.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Dope Sheet.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 422: hash `d2ed74d9568fd5e9b7826dd2c74703685bbcce2926941c53643fcf6cbc9ad879`
- Canonico sugerido: `HOME\Segundo Cérebro\Stage.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Stage.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 423: hash `579883062877601f6b1aa7010e21bf9aed9f880d5052d9731a914d988579730d`
- Canonico sugerido: `HOME\Segundo Cérebro\Expression Control.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Expression Control.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 424: hash `553f8b1c269ee741a67db6ad512734eafe37934004a017e2cc4aeffa245cb7b4`
- Canonico sugerido: `HOME\Segundo Cérebro\Thiago MD.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Thiago MD.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 425: hash `fd0483b1f60b98bb579277f6a881aebd25ec24be1bbcdd5d42749cdebececbd4`
- Canonico sugerido: `HOME\Segundo Cérebro\Martinelli Academy.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Martinelli Academy.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 426: hash `ff12bb7b05939095613d3f621839c6c950738da6daf40642e09b1cee8ed6f36b`
- Canonico sugerido: `HOME\Segundo Cérebro\Atalhos e Criação Rápida de Composição.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Atalhos e Criação Rápida de Composição.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 427: hash `0a8001eb64fd33aaf1cc3e839dd69142add9a93a15c3228a7646937d209ac415`
- Canonico sugerido: `HOME\Segundo Cérebro\Método de autoridade.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Método de autoridade.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 428: hash `c46e45ea7050128d8cf62eb4a8275bfe28e7cb2d7b4246082a15ab75765f4d81`
- Canonico sugerido: `ACIRV\Notas\Como criar o novo backdrop.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Como criar o novo backdrop.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 429: hash `9583fca044787b97018c320515d822d49bc15df558591fcb829bf0afdb6e919b`
- Canonico sugerido: `HOME\Segundo Cérebro\Aula 04 Principais ferramentas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Aula 04 Principais ferramentas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 430: hash `d07301665deb899eef68de8b96e1865fab99c5103edb6d0370c820c6fece0036`
- Canonico sugerido: `HOME\Segundo Cérebro\Organização de Sequências.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Organização de Sequências.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 431: hash `e70160f229856205334f9ad320341681142d1fa99f9c4e6ed2915f31c5f32e3e`
- Canonico sugerido: `HOME\Segundo Cérebro\Kayky - Italian Sorvetes.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Kayky - Italian Sorvetes.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 432: hash `305b3a9b11a0ce14700dc8e8523fff0b4101c6ae71fc1084af209c623e949964`
- Canonico sugerido: `HOME\Segundo Cérebro\Collect Save.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Collect Save.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 433: hash `6bb5af54f02d0eba3ab5bbf28932a8749288e6cded41f83d7fa356f86fdc75dc`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A07 Como transformar sólidos em máscaras.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A07 Como transformar sólidos em máscaras.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 434: hash `d306a5d673a0200dc1022a4189ec41bb589033f0ab2d5603272edd024fe15173`
- Canonico sugerido: `HOME\Segundo Cérebro\M04A02 Como animar texto.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M04A02 Como animar texto.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 435: hash `bd32ecbd267a8846091565a4e3f80f116770ccb6f17d8bf7dba9afecf82cbfdc`
- Canonico sugerido: `HOME\Segundo Cérebro\Talvez seja melhor....md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Talvez seja melhor....md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 436: hash `b23b27d38ca5d17873e8b0f7967c26f1a11eafd39f41759156b82b58bbd2a8ab`
- Canonico sugerido: `ACIRV\Notas\Lovable\API no Lovable.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Lovable\API no Lovable.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 437: hash `18a3e1965238c391fbc3aebbd6a82ebced2ec2cc0605062f08cdb2b7c3a5fc82`
- Canonico sugerido: `ACIRV\Notas\Papelada transcrita.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Papelada transcrita.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 438: hash `d863cb26c1548ddcf6c606639236cd5e8ab3c78ee0b37b3ee9ce3beded44fa7d`
- Canonico sugerido: `HOME\Segundo Cérebro\Câmeras com o Octane.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Câmeras com o Octane.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 439: hash `d934cfe9e646625061346941ba818a288c89b4d1905740bf4f25947f89a444b2`
- Canonico sugerido: `HOME\Segundo Cérebro\Águia Automóveis.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Águia Automóveis.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 440: hash `90156544071cacc0aaffc08b47e464346f6ee9c172a29c3b75d9807948ad7484`
- Canonico sugerido: `HOME\Segundo Cérebro\M02A01 Apresentação da plataforma.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M02A01 Apresentação da plataforma.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 441: hash `b57865bebead9c1be76dd05eae332073ca4f81ec0ac067f3f0090a5174068121`
- Canonico sugerido: `HOME\Segundo Cérebro\Estratégia de Isca.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Estratégia de Isca.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 442: hash `ed1bb9d1aa3f0271d95d1facf1b634b1da5ff1abd10aec68551b30d364b08391`
- Canonico sugerido: `HOME\Segundo Cérebro\Derretendo objetos com o Vertex Map.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Derretendo objetos com o Vertex Map.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 443: hash `a5d5c6e96d3b2eb916fc4a74b94bb0d2de803ff238b183f6e468dbeb75866cd4`
- Canonico sugerido: `HOME\Segundo Cérebro\Plugins da BWMV.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Plugins da BWMV.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 444: hash `43a59c3597d673cf92305e61abee454d8fb1197bf3763505c5c9ef152deeebf1`
- Canonico sugerido: `HOME\Segundo Cérebro\Ferramenta de Formas e Estilos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ferramenta de Formas e Estilos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 445: hash `81e6edd07d3eb6b4f8cc18ee2fc42e1d3527e1d4ebe27651fe5eb9e09ad22d61`
- Canonico sugerido: `HOME\Segundo Cérebro\Missão Prospecção.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Missão Prospecção.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 446: hash `865dbbc86c9c814694b2127beb88faa86e555874d9d051c4c8e34b92bc4573ba`
- Canonico sugerido: `HOME\Segundo Cérebro\O QUE FAÇO.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\O QUE FAÇO.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 447: hash `bc8b1ced1206dda1db781c8f389ac2329c6e9912037ad67d7748d36ef41a1be7`
- Canonico sugerido: `HOME\Segundo Cérebro\PolyFx.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\PolyFx.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 448: hash `f8c4b6afdc0fdb560d058f1b2e2b4f4570121f09b166283d2a4fcfafd233625f`
- Canonico sugerido: `HOME\Segundo Cérebro\Time Remapping com Keyframes.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Time Remapping com Keyframes.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 449: hash `93161606c3f5a7f774c5f7d785fb124a4d3657b29760dcd4faadc98331c8469b`
- Canonico sugerido: `ACIRV\Notas\Dica sobre como construir criativos do Raphael Valongo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Dica sobre como construir criativos do Raphael Valongo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 450: hash `1c41f49d61ddc461391d7ae82c85957d62ba33760c4be101e7b28c73cf54ea9b`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre iluminação.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre iluminação.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 451: hash `636c59ca92762bf54f6d2243e7506a820ba634f5f5a242f53d29f63d05e4e9bf`
- Canonico sugerido: `HOME\Segundo Cérebro\Áudio e Mixagem - DAP 2.0.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Áudio e Mixagem - DAP 2.0.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 452: hash `6a5d3711a1f668ea3f7025c55312c8ce5c4178732281916dadff3396866610e8`
- Canonico sugerido: `HOME\Segundo Cérebro\Cursos em andamento.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Cursos em andamento.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 453: hash `473bf9ca8ee6e84fe68ec7521672b63a87f8929f6a45d37eea5bf6723e2dcb67`
- Canonico sugerido: `HOME\Segundo Cérebro\Moodboard para desenho tipográfico - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Moodboard para desenho tipográfico - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 454: hash `b83dcc20bf9eeab802193202e9cf7b874251e560301c3b2478f5dea2f3679ee9`
- Canonico sugerido: `HOME\Segundo Cérebro\Quero reler.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Quero reler.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 455: hash `ef4effd2b3872a45e975ec31fadcfbe534d22fd940f4abaac99bd98bbf07f422`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre parâmetros do Pyro Output.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre parâmetros do Pyro Output.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 456: hash `71a7b5d8f6de07d81ae39c9594693c5c6d162777f5d740832bc4b8b75d146d08`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre o portfólio.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre o portfólio.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 457: hash `d629497e61234f7d93e523ae49f8f17aa54b87f899192fcbf9f122011fe169fb`
- Canonico sugerido: `HOME\Segundo Cérebro\M06A03 Foward Kinematics.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M06A03 Foward Kinematics.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 458: hash `de78bb1cf49e622af5e91edec9893f06182a2514a136646197c793f5cf784062`
- Canonico sugerido: `HOME\Segundo Cérebro\M02 Apresentação da plataforma.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M02 Apresentação da plataforma.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 459: hash `c53c9dcda367a446e9cf3b16e1d83ad02a6fbd8242654ed8efdf6ff0a032cc31`
- Canonico sugerido: `HOME\Segundo Cérebro\Ruído Fractal.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ruído Fractal.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 460: hash `42cac3298fc26cd60331b46d4f9486dda7857257f3b887b5efb2b239cedf89a0`
- Canonico sugerido: `HOME\Segundo Cérebro\COMO FAÇO.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\COMO FAÇO.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 461: hash `e931ec9a9d2918cf90eceb92c04ebcfe57042643f5965c82f64be2f68b49b1ea`
- Canonico sugerido: `HOME\Segundo Cérebro\Criativos Pro - Stories Animados 2.0.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Criativos Pro - Stories Animados 2.0.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 462: hash `e15b09645572ebd0619ab540368113410a8246c8d420471317b3eb3470c0e6a8`
- Canonico sugerido: `HOME\Segundo Cérebro\M04 Efeitos básicos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M04 Efeitos básicos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 463: hash `cf36a76f48c3f7e0e033a0f08e4ade589e214e25a4e55680d293b3aa37d8ed4b`
- Canonico sugerido: `HOME\Segundo Cérebro\Produto, tráfego e conversão.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Produto, tráfego e conversão.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 464: hash `1943daacd5dd11a0279d0c73957cb69024ca1bd130fb2b93e5e4af7e55f6fc29`
- Canonico sugerido: `HOME\Segundo Cérebro\Cache.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Cache.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 465: hash `76ce8fe9aa15c6095880ffbe30201bdb1b12c3d8228ccd78b6238ad99fbb5197`
- Canonico sugerido: `HOME\Segundo Cérebro\Projeto Centelha.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Projeto Centelha.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 466: hash `9f4c102a30cec80e9e4320604912f0155126334bbf4eef3855b6973e88e7cbf6`
- Canonico sugerido: `HOME\Segundo Cérebro\Mascarando efeitos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Mascarando efeitos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 467: hash `13d3157b33af844d771622ad752a71fcfe048de3d9af0057e3f901ea2356fd75`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A16 Ferramenta de Nulls em Máscara.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A16 Ferramenta de Nulls em Máscara.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 468: hash `6cc823bac7a484a661c5946e7941f9dfdbe4beb83ddbb1a58b8934ac11c57927`
- Canonico sugerido: `HOME\Segundo Cérebro\Livros, cursos e outros.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Livros, cursos e outros.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 469: hash `8f9e7058fea869ff911885080e8546c8bd97ef2bcf2af232ea8fea61701149d3`
- Canonico sugerido: `HOME\Segundo Cérebro\Estrutura Libris.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Estrutura Libris.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 470: hash `1bdb8865273df089a100cccf3fbb4ffd4b0d3e64c5d47c19f44e9c99e6220f04`
- Canonico sugerido: `HOME\Segundo Cérebro\Minhas 4 contas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Minhas 4 contas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 471: hash `c05e7607c5a9a9e6a204065ebc4333158171e479b4d438595db1afae9219ffd8`
- Canonico sugerido: `HOME\Segundo Cérebro\Ideia para uma ferragista.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ideia para uma ferragista.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 472: hash `db1c06d8be5493befa214f5d399c11c3f9fc9655a40c676dbb5880ba70e1e9c3`
- Canonico sugerido: `HOME\Segundo Cérebro\Obsidian.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Obsidian.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 473: hash `aac5d771b5f1b511b8e15a1454b14efcb295ae106fa73cabc47a955f00b07a02`
- Canonico sugerido: `HOME\Segundo Cérebro\Multi-camera fake.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Multi-camera fake.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 474: hash `4f9aa36fa5fdd36651c7e2ea206fc6f5b4c0e0fa417b128e44b752d42cb61302`
- Canonico sugerido: `HOME\Segundo Cérebro\Animação de Texto.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Animação de Texto.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 475: hash `18e18a94b0b3b876f2b185eb3a1b171c898311cb397e0853c0b659aec879cbb6`
- Canonico sugerido: `ACIRV\Notas\Prompt da Vivi para escrever matéria jornalística.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Prompt da Vivi para escrever matéria jornalística.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 476: hash `e23ca292b3af86153b646d5574d1746fbddc0fccf5c77e28a98d1ffc1e88cc9e`
- Canonico sugerido: `HOME\Segundo Cérebro\Hoor Vendas, uma introdução.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Hoor Vendas, uma introdução.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 477: hash `22a28d3aab0d4c68bbc7dac3bb29fec00d43e1f19c3d0fb110af1aa7bb22c3f0`
- Canonico sugerido: `HOME\Segundo Cérebro\Se você quer crescer rápido, crie conteúdos compartilháveis.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Se você quer crescer rápido, crie conteúdos compartilháveis.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 478: hash `105be2b07defbb77448ad369863acf14db47a3d4627c0daf05af8fd15350ee4e`
- Canonico sugerido: `ACIRV\Notas\Um estudo de Lara Dutra.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Um estudo de Lara Dutra.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 479: hash `06bd6c170f18f8664ece86bba7cdb8f3e5803260dfdf1307dd89ad7c36422f19`
- Canonico sugerido: `HOME\Segundo Cérebro\Diminua rapidamente a quantidade de polígonos de um modelo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Diminua rapidamente a quantidade de polígonos de um modelo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 480: hash `52821cf01a3b5bf8261b35a55579824b3278fc8595b57351c2cbb32795b87f50`
- Canonico sugerido: `HOME\Segundo Cérebro\Organização com pastas e labels.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Organização com pastas e labels.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 481: hash `f361bcc3004b1e81c88a5ab5ef1bef5fd1fc25333f708bf9962b92d565b7ee1a`
- Canonico sugerido: `ACIRV\Notas\Como melhorar o manual de cerimonial.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Como melhorar o manual de cerimonial.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 482: hash `7a45676c2a88f066d20f00791dd70c81270dd0a997fa70df0f40382e03f1c683`
- Canonico sugerido: `HOME\Segundo Cérebro\Sombra e Profundidade no PS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sombra e Profundidade no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 483: hash `7363f63765077e557094951144700d50a05e657ea8bd8642406dd04a165a18de`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A11 Revisão.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A11 Revisão.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 484: hash `56eb182a67e4ca3b938eea2fd92db8fd46688c0b6b716455288aeee46046a73b`
- Canonico sugerido: `HOME\Segundo Cérebro\Aprendi com.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Aprendi com.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 485: hash `8dac488be61cbb4932acab668c655322cccd51eec87f5f4055448613897a7b2c`
- Canonico sugerido: `HOME\Segundo Cérebro\Random Effector.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Random Effector.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 486: hash `6b19f4cec72064e16bd18f79e17b00b21c3d4fde36510bcf54c1d26899d1ae1a`
- Canonico sugerido: `HOME\Segundo Cérebro\Rosaina - DF Supermercado.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Rosaina - DF Supermercado.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 487: hash `3ec8a657d209c2dc26f0ca9bfe684a0eea4e4d1771cd30e3fef8d4487a79eef8`
- Canonico sugerido: `HOME\Segundo Cérebro\Nomenclatura e Preferências.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Nomenclatura e Preferências.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 488: hash `effa4f50f5621f8647696db056cd4309b3c3ed88802a73fec4cc2ac922ed7bdc`
- Canonico sugerido: `HOME\Segundo Cérebro\Ducking na prática.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ducking na prática.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 489: hash `3f4fc05a9b3f79f4924594dea98b7189ede0511c83a0e8115fc24cb63b293c05`
- Canonico sugerido: `HOME\Segundo Cérebro\LoopIn().md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\LoopIn().md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 490: hash `75f114c15ea9e900e163b6eaf581251411de3d23272d57e0c272ba7989ce68ad`
- Canonico sugerido: `HOME\Segundo Cérebro\HDRI e Ambientes Virtuais.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\HDRI e Ambientes Virtuais.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 491: hash `974d2101f05e0511bd5a541924bfaef13ae0fa286867cbb7ea19bd6d3459554c`
- Canonico sugerido: `ACIRV\Notas\PROMPT RELEASE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\PROMPT RELEASE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 492: hash `968e5e8a43cd773460764c950635faabf38ba351a4eca99bbaf91cc9dfc95e84`
- Canonico sugerido: `HOME\Segundo Cérebro\Displacer.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Displacer.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 493: hash `7d78fd549ea4c99175ef4ed9f07a7ef52fe4b2a07a49aa27ed3312b574a58ca0`
- Canonico sugerido: `HOME\Segundo Cérebro\Inserindo expressões.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Inserindo expressões.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 494: hash `c3837a9b377445babcc8b449666d0b1659fe4d319b6088ce28c95988bdf36a79`
- Canonico sugerido: `HOME\Segundo Cérebro\Voronoi Fracture.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Voronoi Fracture.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 495: hash `8ccce0268f6e8db58edb3d89e64064679b59d83d2011b1a07cd0080536f879e4`
- Canonico sugerido: `HOME\Segundo Cérebro\M04A09 Efeito Stroke.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M04A09 Efeito Stroke.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 496: hash `2a7c1146e2afe3041f975063a46383aef04aff4befa567809d6b437a1e77eb18`
- Canonico sugerido: `HOME\Segundo Cérebro\Motion C4D.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Motion C4D.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 497: hash `e9a898fb5e97c8686bdc671ca010b13c523b2daa2198978c46031c7126fd2fe3`
- Canonico sugerido: `HOME\Segundo Cérebro\AE para Motion Design.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\AE para Motion Design.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 498: hash `f8e7a7cc1ce780f3fa0171339942e87b86d782c17249c3071146f71b7dc7dc86`
- Canonico sugerido: `HOME\Segundo Cérebro\Lifetime.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Lifetime.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 499: hash `f45437ff720c4c584d3dbde70a466d4c802d3ddcdcb561617e3cf0606d7a13ef`
- Canonico sugerido: `HOME\Segundo Cérebro\Resultado bom em tráfego pago.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Resultado bom em tráfego pago.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 500: hash `0218fad382387afc91f976d04eaa489d63d10a3487ce10ff876d8d5542808573`
- Canonico sugerido: `HOME\Segundo Cérebro\Como fazer uma Spline ser o guia para o caminho de um modelo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Como fazer uma Spline ser o guia para o caminho de um modelo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 501: hash `730cc1d364a9c0cd9e14fa8557461c44deb6868385e4ea20e2d2a5fc383a01a1`
- Canonico sugerido: `HOME\Segundo Cérebro\Como funciona o ME.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Como funciona o ME.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 502: hash `8813b53814b6d5a4d4df5e59e0bb4d17322ea6cea1ce48040ab367a65e45a54d`
- Canonico sugerido: `HOME\Segundo Cérebro\Exportação das letras - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Exportação das letras - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 503: hash `20d297db9e5a200949824610df461ddb8ac17f8b53e9326627c6994b54f29f9f`
- Canonico sugerido: `HOME\Segundo Cérebro\Evite esse erro de principiante.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Evite esse erro de principiante.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 504: hash `d9357e0b3ab71350f7324bb133c8c083c7b947fb11fcba4bf3356d09be2f33f3`
- Canonico sugerido: `HOME\Segundo Cérebro\Pilares para definir objetivos a longo prazo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Pilares para definir objetivos a longo prazo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 505: hash `9c50a3185996244385315e81e09e0cf7664a8e6cc49b7b14d3feffd057530985`
- Canonico sugerido: `HOME\Segundo Cérebro\M02A06 Tipos de Layers.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M02A06 Tipos de Layers.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 506: hash `9991eafa9990decc1e2a17ef78fd75d7f1d92a6c0360c4dc930e0f2065b635f8`
- Canonico sugerido: `HOME\Segundo Cérebro\Tráfego pago.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tráfego pago.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 507: hash `521293518559aa2bc32fd44beef112e0395fa11beb0a026113dfc76e7f61b6b4`
- Canonico sugerido: `HOME\Segundo Cérebro\Mixando materiais com o Octane.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Mixando materiais com o Octane.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 508: hash `72dec4322a86978913f61ce5d4ed7238a980a9ce0c254ad576ae1eb70e1152cc`
- Canonico sugerido: `HOME\Segundo Cérebro\Pyro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Pyro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 509: hash `65b2769a0de1aa977f8bade55584f6c8aeeb9f0589e462603e33672b3f3570b3`
- Canonico sugerido: `HOME\Segundo Cérebro\Texturas Luminosas (Emissão).md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Texturas Luminosas (Emissão).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 510: hash `a4b1ff30200d2251afef079a5152d433cb772f2c518465b1a578fda9c328e115`
- Canonico sugerido: `HOME\Segundo Cérebro\Plugins e Scripts AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Plugins e Scripts AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 511: hash `5edd0c6c9fbb221c09fb63216d0c1dc97515692758ac89bad46c0acc37223bb3`
- Canonico sugerido: `HOME\Segundo Cérebro\Match Cut ou Raccord.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Match Cut ou Raccord.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 512: hash `7233ab09d789547d5f6faaa27980d3917d0a1818b02ad5ec3af3d8df07f89b76`
- Canonico sugerido: `HOME\Segundo Cérebro\Teoria das cores - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Teoria das cores - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 513: hash `7d879ac66c1e56f248879ea7f90a2f2d35bdac3a91abe7a7efa225f7ba4f76f6`
- Canonico sugerido: `HOME\Segundo Cérebro\Hora de Exportar.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Hora de Exportar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 514: hash `a671b29fee0496cd101940d4e3ae07b4888dabbde05b0579071db021f755214d`
- Canonico sugerido: `HOME\Segundo Cérebro\Liber Vendas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Liber Vendas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 515: hash `02774b4c6de12e611d503eed2879660b2e30da044c3ceda4202faaab68df7f57`
- Canonico sugerido: `HOME\Segundo Cérebro\Seguir a musa é seguir o caminho..md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Seguir a musa é seguir o caminho..md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 516: hash `054c51c6d5f13966379bf50bb33e309510ead1b1f1b1fb5ec6cb7771b2e7320d`
- Canonico sugerido: `ACIRV\Notas\Inicio do prompt para fazer o planejamento de janeiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Inicio do prompt para fazer o planejamento de janeiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 517: hash `8fe032c6dcb8200bbc02a2261a5e7dd136216fe2de46875f1420954b7b18e3cc`
- Canonico sugerido: `HOME\Segundo Cérebro\Eudes.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Eudes.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 518: hash `84c4edb857ca18a7059f51ad3e3f352ea08a2c931ff9b603ede43a5b66c1077f`
- Canonico sugerido: `HOME\Segundo Cérebro\Tarefas padrão do Dia 03.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tarefas padrão do Dia 03.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 519: hash `fec5e3e9f3799344dc59fe8a093ea13ccf9dba46515dc65a55966c39428e4285`
- Canonico sugerido: `HOME\Segundo Cérebro\Tipografia no PS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tipografia no PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 520: hash `4dc9a105e37d33f3e0736581cfb140b8676141063eb0773725ec6c90ed26bb03`
- Canonico sugerido: `ACIRV\Notas\Números sobre o Conecta.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Números sobre o Conecta.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 521: hash `3b10153f118d39043a908bebc109b801da6f92dd2b9086c51bad14f47faa8357`
- Canonico sugerido: `HOME\Segundo Cérebro\Bicicletaria Dois Irmãos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bicicletaria Dois Irmãos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 522: hash `80e0354d7913970f966369c5ade5231de6e729b4e97b80a12ec12b46cc29b9b9`
- Canonico sugerido: `HOME\Segundo Cérebro\M05A01 Ferramentas de Chroma Key.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M05A01 Ferramentas de Chroma Key.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 523: hash `ae7300b7613f66818d86ea7bf180d04edb790751007eda22fbef7037c50bcb93`
- Canonico sugerido: `HOME\Segundo Cérebro\NPPR.Team.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\NPPR.Team.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 524: hash `93ac9e8a6f6403cb20a71b8e151ac49f48c0cbcd0f918373e61f77772f919cbc`
- Canonico sugerido: `HOME\Segundo Cérebro\Regrinhas de treino.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Regrinhas de treino.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 525: hash `e81e783a2d4214d2facf35361f8a9695edb2efd98e04b88876ae3c7d0777dac5`
- Canonico sugerido: `HOME\Segundo Cérebro\Decupagem.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Decupagem.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 526: hash `0329c3ec8fd9324dacbaa650bf22aa8bd54ad51c5f07402744c1ddc4b300f108`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A15 Nivelamento de cor das camadas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A15 Nivelamento de cor das camadas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 527: hash `5ae60e336ae471676968257112211b58314b1a5867e69a3008206416ca843266`
- Canonico sugerido: `HOME\Segundo Cérebro\Re-escalonando o tamanho dos clipes.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Re-escalonando o tamanho dos clipes.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 528: hash `d959e066f4e9e5b8e4e5bc7c296c03f665ace56c02b4bc70a41f4901ec9a7d44`
- Canonico sugerido: `HOME\Segundo Cérebro\Edição de vídeo pelo Photoshop.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Edição de vídeo pelo Photoshop.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 529: hash `db86e3f15bc416a1a7e3fc44d694f477323e77ad92c7995cad46546a1adcbcf5`
- Canonico sugerido: `HOME\Segundo Cérebro\Comissão por afiliação.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Comissão por afiliação.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 530: hash `6c7cb0f8a1c21892965a6b7edd9cec29fb8b82612c1d1945935f22887a3cd7fb`
- Canonico sugerido: `HOME\Segundo Cérebro\Cinema 4D.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Cinema 4D.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 531: hash `000b2fe06d7df64dd36173b6cfa3897245b498bf40b31120667f600b6fd2edc4`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A03 Como usar o Motion Path.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A03 Como usar o Motion Path.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 532: hash `0327b4d71483e58f89a0dfa81cc98e821311a79f600936731be6ed19b4fa9f25`
- Canonico sugerido: `HOME\Segundo Cérebro\Posterize Time.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Posterize Time.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 533: hash `039f7b0990fdd40997883b06af4a5ed57cecfe303705a807d1a6e2373075972e`
- Canonico sugerido: `HOME\Segundo Cérebro\Triangulo da auto-obsessão.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Triangulo da auto-obsessão.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 534: hash `40a438dd3d6cc11269460ac6a8fbb9010bf5b82d3b80448548f3f28328d0070b`
- Canonico sugerido: `HOME\Segundo Cérebro\M05 Compositing.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M05 Compositing.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 535: hash `c9a7a460a5c196f8162582c0c1f9c3be49e7bb2e004a44fc02b4dd8b124815fc`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre composição de vídeos para Instagram.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre composição de vídeos para Instagram.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 536: hash `c183fe56a5beb435d674aebd41f001e68ee6d36b334b15fa310356ea32fd4a18`
- Canonico sugerido: `ACIRV\Notas\Para pedir idéias.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Para pedir idéias.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 537: hash `26f569eb9733d6f829a73ff2988aa7994910334f58c7018fee816ccda89c9f79`
- Canonico sugerido: `HOME\Segundo Cérebro\M05A07 3D Câmera Track.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M05A07 3D Câmera Track.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 538: hash `752aab97550aabfb078c74582b851e63604d9d5100024de1d5f2c22447f49361`
- Canonico sugerido: `HOME\Segundo Cérebro\Notas AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Notas AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 539: hash `6cd2f77fa2105033edef3f9d03501bc98553e574d2fbc28888219995143f4bf3`
- Canonico sugerido: `ACIRV\Notas\050226 - Reunião sobre a SudoExpo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\050226 - Reunião sobre a SudoExpo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 540: hash `51de92e429ae1a696509d9966d5d14af5e09a1335deeb37d2f1ee35a57818189`
- Canonico sugerido: `ACIRV\Notas\Tamanhos rebranding comunicação interna.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Tamanhos rebranding comunicação interna.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 541: hash `30ad0796a734d7d83a40f9e4ace70a4a4c1cfc3a114772e3d751fe336d44a3dc`
- Canonico sugerido: `HOME\Segundo Cérebro\Captura suave e FPS arredondado.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Captura suave e FPS arredondado.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 542: hash `ee847591b2e6f7e3e13dbf6c9ca63dc78b4a2f87ea28fab1675563496adf7dad`
- Canonico sugerido: `HOME\SaaS com Kelvyn\TPM\TPM Obsidian\00_Insights.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\00_Insights.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 543: hash `eb9f8de8482a66e70d9b7f83ae9edb17f1c5b6a3131d7a5f299b2ad696c35ee1`
- Canonico sugerido: `HOME\Segundo Cérebro\Deslocamento.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Deslocamento.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 544: hash `b07ec638ebddb0805d722cc3c47a58ebe5792eaeb2f72e406b0f2f5616854d40`
- Canonico sugerido: `HOME\Segundo Cérebro\Papas Grill's.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Papas Grill's.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 545: hash `a717f2f0c6f21bacf51d34459f475b9e4dc32bb96d7ca1189f129f20d4f20f44`
- Canonico sugerido: `HOME\Segundo Cérebro\Repetição de Texturas no Node Editor.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Repetição de Texturas no Node Editor.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 546: hash `0595f92efcc632231d29d51c395a1f2b7e5f7fdc8cceebe43f88dee8a613bbb5`
- Canonico sugerido: `HOME\Segundo Cérebro\LoopOut().md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\LoopOut().md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 547: hash `d91169fc956a4c47e6345c36dd6ad69f565e40ceac81edfdef351d10331cc5b5`
- Canonico sugerido: `HOME\Segundo Cérebro\Looping e outras propriedades de animação via KeyFrames.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Looping e outras propriedades de animação via KeyFrames.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 548: hash `1f12b2176b18a42250d58a546a7657939f1b7f7cdce5682acc1ea3639fe961f7`
- Canonico sugerido: `HOME\Segundo Cérebro\Lista de efeitos oficiais do Premier.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Lista de efeitos oficiais do Premier.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 549: hash `a1b92d3b9aeda61cd66df1da6fcea55823703052249312460cc6ab9e07efa3f8`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A04 Graph Editor e Refinamento de Animação.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A04 Graph Editor e Refinamento de Animação.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 550: hash `149ebf3fa3f452b77c71d2fb694c6c719906e0fb500dc1ba695a482e769ad7d2`
- Canonico sugerido: `HOME\Segundo Cérebro\M0202 Como criar uma composição.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M0202 Como criar uma composição.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 551: hash `4f5cac907c011d0e5623fe42bfdd5a176b66cb62f4b538369bd5ee2dcc9c4726`
- Canonico sugerido: `HOME\Segundo Cérebro\Variáveis.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Variáveis.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 552: hash `f224143e15b955ed1515a6c360740bdf5aec4d0283b7d236ca545f62d3228736`
- Canonico sugerido: `HOME\Segundo Cérebro\Grab.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Grab.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 553: hash `63e9fec394911c9898315667606fdc2dafbd593ca708ec070c430daa47036492`
- Canonico sugerido: `HOME\Segundo Cérebro\M05A03 Rotoscopia.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M05A03 Rotoscopia.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 554: hash `761577fd302ce09b7bd56d8d8bf5962b59ebe3391af8418ad15fa4f00f5dcff4`
- Canonico sugerido: `HOME\Segundo Cérebro\Colorização com Lumetri.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Colorização com Lumetri.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 555: hash `1bc43039bab438e1008ea45a0342b9c44965bbef43378be434cbe59c7c5970ad`
- Canonico sugerido: `HOME\Segundo Cérebro\Wiggle(Frequência,Amplitude).md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Wiggle(Frequência,Amplitude).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 556: hash `7eef14aca1b550a1a488ee4a1ac88a8baf80ad03e4e418dd424054c0d923b18d`
- Canonico sugerido: `HOME\Segundo Cérebro\M05A05 Time Stretch e Time Warp.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M05A05 Time Stretch e Time Warp.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 557: hash `e236fdc28ac51138ac22b248a9ee47a361b4a047524d71056b81edf77ed3c609`
- Canonico sugerido: `HOME\Segundo Cérebro\Falloff.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Falloff.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 558: hash `66f3d1314c1fe95ddd81ba5b0004dba9b9a5d2975f641e9c9a986c7553d7802b`
- Canonico sugerido: `ACIRV\Notas\Sobre cabeçalho obrigatório dos cartões do Trello.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Sobre cabeçalho obrigatório dos cartões do Trello.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 559: hash `3658345d30b4cc1569598cd35e7a12c4808a1a6eae488ec6283e23cebf1bc1ac`
- Canonico sugerido: `HOME\Segundo Cérebro\Isabel Pavanello.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Isabel Pavanello.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 560: hash `f8f26cd37f7acb1533fbddf35552bfd49f77ba076d07e650dc7231c737b28420`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A10 Tipos de Mesclagem.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A10 Tipos de Mesclagem.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 561: hash `3b42a2b110acaa3bee1a3ca4cfcdc29175d42dd6a6bda0a36a3ad4b3cff3f055`
- Canonico sugerido: `HOME\Segundo Cérebro\Curso Edição de Vídeo COMPLETO.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Curso Edição de Vídeo COMPLETO.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 562: hash `d0b002d8e4a557e65ca36a28ec38760a5deaa14087434a9353c84f8f8d62d9e6`
- Canonico sugerido: `ACIRV\Notas\RETROSPECTIVA 2026.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\RETROSPECTIVA 2026.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 563: hash `0675d7e82fe8e11b7c2b32298aadae0b50d4e2b568ff646c498c121c174cea11`
- Canonico sugerido: `HOME\Segundo Cérebro\UGC ou User Generated Content ou Conteúdo Gerado pelo Usuário..md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\UGC ou User Generated Content ou Conteúdo Gerado pelo Usuário..md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 564: hash `30d10eaf13724b54d19ff29ec9447583450d7226c5a85dc231e0515a5f46a4a0`
- Canonico sugerido: `HOME\Segundo Cérebro\Insights.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Insights.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 565: hash `4b73a5c473761b64b32d9e61fc7b2fe8184e5ee5e9e9285aa08f0d99756a20b6`
- Canonico sugerido: `HOME\Segundo Cérebro\Como calcular o salário do empreendedor.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Como calcular o salário do empreendedor.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 566: hash `1065c5c62feac19ce2e17ddaf0f3ef6103fd5e5c31cfc12e554a1b85f794feb0`
- Canonico sugerido: `HOME\Segundo Cérebro\Usando a sombra original da imagem.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Usando a sombra original da imagem.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 567: hash `4ff85ef323fdad4ad00218feb85fa842f450951805c5a71ca0bc9fc51e123a9a`
- Canonico sugerido: `HOME\Segundo Cérebro\Exportando modelos selecionados.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Exportando modelos selecionados.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 568: hash `ee09b9f4dbb8209d77a3fe1d9afea72011fffc4b4d97ab34c394beb3ca145188`
- Canonico sugerido: `HOME\Segundo Cérebro\M04A11 Aplicação - Ramp e Glow - Audio Wave Form.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M04A11 Aplicação - Ramp e Glow - Audio Wave Form.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 569: hash `e822129398de4b26ee190a6d6fc32ac4e285fa3c7d300f8f5ad22afefdfaca9c`
- Canonico sugerido: `HOME\Segundo Cérebro\M02A08 Como lidar com arquivos perdidos.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M02A08 Como lidar com arquivos perdidos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 570: hash `59b7fa4ab8693501399ce05e8f37cad2312de1ce3e05db1d390066e274f0b782`
- Canonico sugerido: `HOME\Segundo Cérebro\Deslocamento Turbulento.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Deslocamento Turbulento.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 571: hash `1ef27729d721c7182843500e35430c7137ab4a66755b1d7a2c06f86e62450716`
- Canonico sugerido: `HOME\Segundo Cérebro\Atalhos de movimentação no Viewport.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Atalhos de movimentação no Viewport.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 572: hash `0e8b5f3507b48e5937d380445fb26cc2c6b33331be621dce620deef6fbe3c528`
- Canonico sugerido: `HOME\Segundo Cérebro\Time.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Time.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 573: hash `829193ada75dd898e5ca60b49e052e954828ddb29a73af25ca88abaa8a23e0a1`
- Canonico sugerido: `HOME\Segundo Cérebro\Estudo e Referências - DAP 2.0.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Estudo e Referências - DAP 2.0.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 574: hash `c55c05476eace2dd9aa40cb1f8b3d1d2929ae7613a4cebb5a1557cabb92989bb`
- Canonico sugerido: `ACIRV\Notas\Acessos site.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Acessos site.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 575: hash `f97f34f82a01f68f4fae7249d110dd36a74d54056437bcf0b486d636e7786f72`
- Canonico sugerido: `HOME\Segundo Cérebro\Câmeras.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Câmeras.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 576: hash `b941b6cee3796360b3ba0e0abea79d6d99ca5d313f92744d3c2ef2e4073bc2ab`
- Canonico sugerido: `HOME\Segundo Cérebro\Material Id.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Material Id.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 577: hash `9e340118a91fc0885c952f1cd6702260fb81052d379cc4073d34a91dfead0a05`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A02 Interpolação de KeyFrames.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A02 Interpolação de KeyFrames.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 578: hash `c191fd90e58bd3e0cdb611ca52c3fb328e2ea8b1044578dd6c05fd7a2600d2d2`
- Canonico sugerido: `HOME\Segundo Cérebro\Cache do Pyro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Cache do Pyro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 579: hash `01133c84c318b187ef5dadd017759c2a633b0f38439e8409fe741fdea958148d`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre o 3D do AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre o 3D do AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 580: hash `436ac803a072a889338c3b36b51d3c07c3a72385fd38a2f7fe2d7bd46baa2e1c`
- Canonico sugerido: `HOME\Segundo Cérebro\M05A04 Time Remapping.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M05A04 Time Remapping.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 581: hash `9f6ccdc47a55d1c3fc2ad45a2293c61bd2d426794c039b94728cf5ccde216f33`
- Canonico sugerido: `HOME\Segundo Cérebro\Parâmetros do Cilindro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Parâmetros do Cilindro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 582: hash `d2703129007c2b6cac0e2ad806db365202abfaf7a45209e6ceb0e4c595e8c04f`
- Canonico sugerido: `HOME\Segundo Cérebro\Bruno Cabeleireiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bruno Cabeleireiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 583: hash `41b0dca3249e75c2678f998916658437aba35761589b053235d5bcb3f30b46db`
- Canonico sugerido: `HOME\Segundo Cérebro\Anotações Premier.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Anotações Premier.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 584: hash `a56b394a51efd14522381924f68ea888e81086cbc989c58c3e70602efd29e668`
- Canonico sugerido: `HOME\Segundo Cérebro\EXR para composição no AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\EXR para composição no AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 585: hash `ebf9eeea6dc14f5f4a7a98324d66b4b2431c76a907b82e078c5f68ce853f4297`
- Canonico sugerido: `HOME\Segundo Cérebro\Octane.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Octane.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 586: hash `73708325130080fb1c5f6f8200594835e8c282c4a937594130dc89ef37390dad`
- Canonico sugerido: `HOME\Segundo Cérebro\Faça a câmera seguir um objeto.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Faça a câmera seguir um objeto.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 587: hash `071802ecb8cc42eb60040b66520582a0567a4dcd0cae2e9daa04d4bbfee87033`
- Canonico sugerido: `HOME\Segundo Cérebro\Focal Length (Distância Focal).md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Focal Length (Distância Focal).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 588: hash `2f309487fad5b60557a0b196b5cbd9f09d9a08f35a1212732576299780568aa0`
- Canonico sugerido: `HOME\Segundo Cérebro\Extrusão e Texturas no AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Extrusão e Texturas no AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 589: hash `2bf45a4cec742a2e6931372ce519bf193d41fb47534958e2a165b185a83e5559`
- Canonico sugerido: `HOME\Segundo Cérebro\Introdução ao Illustrator - Aulão YT.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Introdução ao Illustrator - Aulão YT.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 590: hash `801cd0198fa142757e41635835cf5f1023fa2870c85c2cad041068271dc621c1`
- Canonico sugerido: `HOME\Segundo Cérebro\Como visualizar duas composições.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Como visualizar duas composições.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 591: hash `e5b83fcc90de37e84629e53973083ae448b9585d5e2b4abc2dff5997464eb5fa`
- Canonico sugerido: `HOME\Segundo Cérebro\Iluminação com o Octane.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Iluminação com o Octane.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 592: hash `fe78506f2e3685e2968dcef130f403ec293a2ade78bb06ac8510c58643487955`
- Canonico sugerido: `HOME\Segundo Cérebro\Drive e Link de Cifras.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Drive e Link de Cifras.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 593: hash `f006773ce999e1879400a98dccd0afb2bc4290447a2bfa41f3c5cf885b3a20aa`
- Canonico sugerido: `HOME\Segundo Cérebro\Afiliações do Peter.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Afiliações do Peter.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 594: hash `471517f8de5a8b2144e94841d446f1b1697b74ccfc3dc03642a0c662a9d2c66b`
- Canonico sugerido: `HOME\Segundo Cérebro\Burlando a proscrastinação.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Burlando a proscrastinação.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 595: hash `a6998090bd83012ba79f0ab30b8867ee91e7e6939d046d231d9b2cfac457fe1f`
- Canonico sugerido: `HOME\Segundo Cérebro\M05A02 Luma Key.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M05A02 Luma Key.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 596: hash `d6bb6008ff6feee765dd5bd3da4b304b84bfd28b244b3a9e385807ad2ad6ece9`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A01 Animação Básica e KeyFrames.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A01 Animação Básica e KeyFrames.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 597: hash `68a8d8540632ec5342735f007126f6a50477d2adbdd295b38078edeb198a42b9`
- Canonico sugerido: `HOME\Segundo Cérebro\Media Encoder.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Media Encoder.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 598: hash `586c89c47347e8d9183e9cad565b9e4cd20ae65ab04cced908f6dddd8a7de257`
- Canonico sugerido: `HOME\Segundo Cérebro\Link de afiliado.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Link de afiliado.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 599: hash `aa32972b5a4c6570989dced6b82acebdfe99085a529a9024efce7aacbaee796c`
- Canonico sugerido: `HOME\Segundo Cérebro\Nova Pesca.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Nova Pesca.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 600: hash `9e0660a16cec49eaf9a17018d0d4304d1294c84553c3307d1252e29dfd6ebce0`
- Canonico sugerido: `HOME\Segundo Cérebro\Andy Ramos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Andy Ramos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 601: hash `774f6cc267711884a1df6e2ab407eef965aa4e19698b626e52a5cb30d48a3ea8`
- Canonico sugerido: `HOME\Segundo Cérebro\Preciso desenhar como vou agir nas seguintes situações.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Preciso desenhar como vou agir nas seguintes situações.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 602: hash `1274d2bed0d22ca9160eb6cbcefd9e1975c4cc6954333e72a45b425865f360ea`
- Canonico sugerido: `HOME\Segundo Cérebro\Prompt obrigatório nas IAs generativas de vídeo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Prompt obrigatório nas IAs generativas de vídeo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 603: hash `e9e59f962a2b5826b96d41c09de26765517880860ab04b94fd1a61c7c2ceecd0`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre aparador de formas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre aparador de formas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 604: hash `a4ca046510828507d4a2fc17dd5a8d73c1cd60dfddafcfeca3e669702d538cb8`
- Canonico sugerido: `HOME\Segundo Cérebro\Modo Solo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Modo Solo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 605: hash `e5caa5cc0f135fcee26993f4eb133725dac3d7197bfd57f68cb4170ac9f13915`
- Canonico sugerido: `HOME\Segundo Cérebro\Oportunidades no Design.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Oportunidades no Design.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 606: hash `5d58f3fe5202340177eb8a624276bde79a2f9cfb9a98144861a88edbc8f1f2d1`
- Canonico sugerido: `HOME\Segundo Cérebro\Introdução a arte generativa - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Introdução a arte generativa - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 607: hash `b6c5721085b9b3969a39d8e81516da4439ca6b3611284a211cd404c15e481caf`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre o professor - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre o professor - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 608: hash `5a477d45140f35fd104b0813f8b9cad243d847fedec29212572680c801d753fb`
- Canonico sugerido: `HOME\Segundo Cérebro\Defina seu público alvo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Defina seu público alvo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 609: hash `fd7303baa3a68bc829412d711852ddb3ed8c29bfacb99d4ab12b832a5dea126d`
- Canonico sugerido: `HOME\Segundo Cérebro\Klinsmann.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Klinsmann.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 610: hash `64d115109f8d1bfbabf2a0d18b16d507328c92e45ddc1fa3242fb0fb10f07d3b`
- Canonico sugerido: `HOME\Segundo Cérebro\Renderização com o After Effects do Projeto com pós-produção finalizada.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Renderização com o After Effects do Projeto com pós-produção finalizada.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 611: hash `2c85045c200d601bc511c44ca5996109321558ada581618c494e23daa2d6ca39`
- Canonico sugerido: `HOME\Segundo Cérebro\Speed.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Speed.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 612: hash `56b143f638781d5c285042e51ed605c0c1cf80efd9393ed2e1335e00f660b30a`
- Canonico sugerido: `HOME\Segundo Cérebro\Seleção de cores com Lumetri.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Seleção de cores com Lumetri.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 613: hash `94f06904bf2465f11b104d5c162174ec79dc907a34ae8c0013d9149ce3ea4a74`
- Canonico sugerido: `HOME\Segundo Cérebro\Animação de Stories.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Animação de Stories.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 614: hash `0a6c83024693c519454e6f6ee3468bc796eb73ef82b87ef77c7b47b212f8e10f`
- Canonico sugerido: `HOME\Segundo Cérebro\Plugins Premier.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Plugins Premier.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 615: hash `a70e9ff8d9b7ca6edadbbd145105ae33e21e2f1067781401b6bee897b1813894`
- Canonico sugerido: `HOME\Segundo Cérebro\Principal Função do ME.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Principal Função do ME.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 616: hash `e765de40f29a52d3b8aa75b5ed81beb67112b7ea35846ccb1aa820ff7d1cf7f7`
- Canonico sugerido: `HOME\Segundo Cérebro\Converter em texto editável AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Converter em texto editável AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 617: hash `6d25f2991b495acc3d71b39cba96816b8d411c09fc3d7594ce13f4832d755f88`
- Canonico sugerido: `HOME\Segundo Cérebro\Ferramentas que utilizo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ferramentas que utilizo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 618: hash `8dfdbe972af8922d41689df258680fa6dbabc36f12f8460a0989b2bebfc1ef9d`
- Canonico sugerido: `HOME\Segundo Cérebro\Rotation.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Rotation.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 619: hash `14ce44a71ac7a50b309d0314f36f185678c788cda0aa5ee3c1f6a2181cb02c63`
- Canonico sugerido: `HOME\Segundo Cérebro\Integração com a Adobe.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Integração com a Adobe.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 620: hash `2b5735f93a7c4ddd7d93c27eddc9b9332cfed0d802e91543f72e4cce1f17a972`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre parâmetros do Pyro Tag.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre parâmetros do Pyro Tag.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 621: hash `5ea2e01e68e55d4e1e310481df12e44af0817d4510e5b36eebf816142fddba43`
- Canonico sugerido: `HOME\Segundo Cérebro\CC Jaws.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\CC Jaws.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 622: hash `6fd92c50494796cf4171df5555a5324c03c3b7e3f8f00846d5eaca8342635bd7`
- Canonico sugerido: `HOME\Segundo Cérebro\Cloner.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Cloner.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 623: hash `b06f4cfd83bb63f33e4faa1e412b6ac6f81973f54b649e72f76d354c5374db19`
- Canonico sugerido: `HOME\Segundo Cérebro\Navegador de mídia do ME.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Navegador de mídia do ME.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 624: hash `3753189f7fb305bfeaaf67a4c3adb6d47cf79189bd69a801ae1a1ecd45530ab1`
- Canonico sugerido: `HOME\Segundo Cérebro\Minhas histórias.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Minhas histórias.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 625: hash `0d20c5d603f7865b6a475ff7e9a6f3707710cba2534ec68b57b62c7d7f649c1e`
- Canonico sugerido: `HOME\Segundo Cérebro\Referência é ouro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Referência é ouro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 626: hash `9cff44c33aee357dbb7782c5c8dedb6cdac6691475a221b98f7aa91513ec4d55`
- Canonico sugerido: `HOME\Segundo Cérebro\Atalhos Dope Sheet.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Atalhos Dope Sheet.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 627: hash `d16de322cf3db1b92822b944e8a960c2c929e887f15933cef59dae2fb5d9ca22`
- Canonico sugerido: `HOME\Segundo Cérebro\Trabalhando com Múltiplos Renderizadores 3D no After Effects.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Trabalhando com Múltiplos Renderizadores 3D no After Effects.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 628: hash `3b144af46a25aacbc6d89abaf5150699fe513ef8168b261066936d5e1a2765e7`
- Canonico sugerido: `ACIRV\Notas\Lovable\21st.dev com Lovable.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Lovable\21st.dev com Lovable.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 629: hash `097c3906be962f6615d496a455549090b0e833734eab044f0aa374dc1d848c9e`
- Canonico sugerido: `HOME\Segundo Cérebro\A força da obsessão.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\A força da obsessão.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 630: hash `97ac51e75a3f11c0e1be8523e8d0f81138435e866e42a05a6e6e2b368c74611e`
- Canonico sugerido: `HOME\Segundo Cérebro\Design de tipografia com técnicas de animação procedural.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Design de tipografia com técnicas de animação procedural.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 631: hash `ba2086849d2d798ecfe35f2f2db4fc749362d89cd068c6718ca90f82b9d56232`
- Canonico sugerido: `HOME\Segundo Cérebro\Audio Waveform.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Audio Waveform.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 632: hash `dae35132c41e28bedbaefb7fcb9e7bebccac63daee19d212d3110c66f7d1f381`
- Canonico sugerido: `HOME\Segundo Cérebro\Presets.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Presets.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 633: hash `3bb3ce590a146099001eb64d64be3e27a65cde6045afe0ae083141e42cefce37`
- Canonico sugerido: `HOME\Segundo Cérebro\Áreas de atuação para Motion Design.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Áreas de atuação para Motion Design.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 634: hash `ac8c8f69369267e549dd1c5cb6625f1a2d11a90ce1b5225d4aa00198d0fd5abc`
- Canonico sugerido: `HOME\Segundo Cérebro\Câmeras e Renderizadores.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Câmeras e Renderizadores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 635: hash `d6f8240fc3676598d4e7c126dcefd65c298179643222ea394c573241967c9105`
- Canonico sugerido: `HOME\Segundo Cérebro\Planos e ângulos de filmagem.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Planos e ângulos de filmagem.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 636: hash `2473d4908ce1a171a174a0cfb5a624eb0135f18ef5a0fc11b8cd31a5e83916df`
- Canonico sugerido: `HOME\Segundo Cérebro\Renderização e finalização.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Renderização e finalização.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 637: hash `041a5ceba9371d6055ce6c478ca6a5f7315b435006c4db06b22a46c696a4d9f9`
- Canonico sugerido: `HOME\Segundo Cérebro\Interface Otimizada para Motion.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Interface Otimizada para Motion.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 638: hash `e897cd8327806e1b2f217c1dfb6c4bf6bfa8473015a39687f8b56a3515b6f714`
- Canonico sugerido: `HOME\Segundo Cérebro\Ideias iniciais NOX.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ideias iniciais NOX.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 639: hash `4ad03a4367f5babdd2baa5b83f8ea45417056f53e43a86e803b22447ea90eb4a`
- Canonico sugerido: `HOME\Segundo Cérebro\HandBreake.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\HandBreake.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 640: hash `b624ad8906b6caf8798cb03815f4377892b9582efdd80f1004f295007450bb01`
- Canonico sugerido: `HOME\Segundo Cérebro\Temperatura na Hotmart.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Temperatura na Hotmart.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 641: hash `e8d164ed97795f2478510d9ad268ece7de8fbaf4fd3033b7ea15b88e13c4ff96`
- Canonico sugerido: `HOME\Segundo Cérebro\Contas alternativas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Contas alternativas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 642: hash `cc93e8a0c8e834172a2952f900ac02561dbb0d773b4bb7d088fa7fc73de57e0b`
- Canonico sugerido: `HOME\Segundo Cérebro\F-Curves Mode.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\F-Curves Mode.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 643: hash `6e423850d2a6eaf1334039f4a801c737edfc19c8b38b076a4586b9b0ee27f0ad`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre o Slow.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre o Slow.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 644: hash `a044f7c607c16704307dae8bf3ed68582237e9fc3be948608b2d9c6a9cb75fd7`
- Canonico sugerido: `HOME\Segundo Cérebro\Gestão de conhecimento e tempo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Gestão de conhecimento e tempo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 645: hash `6ca80bc150f2e95cd989e708160d32250ca3256201508750aac19841c9bd2517`
- Canonico sugerido: `HOME\Segundo Cérebro\Gabriel, vulgo Pai da Maya.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Gabriel, vulgo Pai da Maya.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 646: hash `34566dd1c8fef2d55e554f8f620d6211f9218afe4678eadc28cbec9cbf330dba`
- Canonico sugerido: `HOME\Segundo Cérebro\M04A06 Expressão Pendulum.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M04A06 Expressão Pendulum.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 647: hash `20667da6d368ea2692d00db939bfb7b138e21364941411b93b76d25a21173dea`
- Canonico sugerido: `HOME\Segundo Cérebro\RubberHouse 2.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\RubberHouse 2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 648: hash `9a95968c1d39f88d85a18ce21ab53c7f36114517e84d547c13fbbacd5fae59f6`
- Canonico sugerido: `HOME\Segundo Cérebro\Principais plataformas de afiliação.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Principais plataformas de afiliação.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 649: hash `3cebf6b8ec8e8235b3d4b1d9d413f088335f1ed9c46950c0b1bfce4693d74eb2`
- Canonico sugerido: `HOME\Segundo Cérebro\Edição e Fluxo de Trabalho.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Edição e Fluxo de Trabalho.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 650: hash `95dcdbea49b78aee5c188ccfcb7fb687eb5fe3626d515cb896d6a1894767abda`
- Canonico sugerido: `HOME\Segundo Cérebro\Bancos de Materiais no C4D.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bancos de Materiais no C4D.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 651: hash `459508cc5368ef9f34ddf7e74c8791458942941482628f895e1bd3724a857e1b`
- Canonico sugerido: `HOME\Segundo Cérebro\Green Motors.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Green Motors.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 652: hash `d9b41d7a0b9782044993d1eb10e047aab868adf1105eb8111713eafb1fb50d2d`
- Canonico sugerido: `HOME\Segundo Cérebro\Melhores produtos para ser afiliado.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Melhores produtos para ser afiliado.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 653: hash `3199e4cbd659c471a85612713fad97758f5a4da8bd4f647dcc869253dd940617`
- Canonico sugerido: `HOME\Segundo Cérebro\Pedro Alves.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Pedro Alves.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 654: hash `a2a06aff1fe55bae699949697d7a5bbaff237ed8631097c11da1db1420b546ad`
- Canonico sugerido: `HOME\Segundo Cérebro\Em caso de Câmera Tracking.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Em caso de Câmera Tracking.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 655: hash `9a57f033f688e2eea5e51448be7ce51a95bbf3626722a3fb8321db4f3561183c`
- Canonico sugerido: `HOME\Segundo Cérebro\Rápido e Devagar.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Rápido e Devagar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 656: hash `a8e661205a470fb1b684515bfec7a2c467a7e2fbdd2b6c581e4feb43207c74a8`
- Canonico sugerido: `HOME\Segundo Cérebro\Z Depth.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Z Depth.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 657: hash `77dfb9535a73388ec356e4a9e82e5d7cba875e8a971c2e707ff1c9ac8bbd54ff`
- Canonico sugerido: `HOME\Segundo Cérebro\Definindo transição padrão.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Definindo transição padrão.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 658: hash `a486cdcf688da645f6774e43032740265d46bb61a5eb58e8ff7eb44f21416561`
- Canonico sugerido: `HOME\Segundo Cérebro\Ativando e Desativando Expressões.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ativando e Desativando Expressões.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 659: hash `bf09e6f5a8208d0a3305e9001aef8e09450c3522c51bf20baad8b65d7d7b6238`
- Canonico sugerido: `HOME\Segundo Cérebro\Materiais pelo Renderizador.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Materiais pelo Renderizador.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 660: hash `35ac0aed58fb416c7d7fb5baec8adfa4ae45074a84e59fcbdc30f261adaf7ea9`
- Canonico sugerido: `ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Março.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Março.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 661: hash `7bc36b9da548990a661adaaed7c1ba674b73852bee5512054d5c1d5801ad1fe1`
- Canonico sugerido: `HOME\Segundo Cérebro\Bibliotecas de áudio gratuitas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bibliotecas de áudio gratuitas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 662: hash `4cdc951130f85d494861fff7bf5f444c162b259e3fee7bdaaad64d613560f4f3`
- Canonico sugerido: `HOME\Segundo Cérebro\CGI & VFX.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\CGI & VFX.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 663: hash `12548ec2e21b0cc829935d63f0751dfa7a938b8863143f9737fc49f8055202ce`
- Canonico sugerido: `HOME\Segundo Cérebro\Fill.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Fill.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 664: hash `eb5499bc99ebc075b60fad95b8cb243a2cdd91a4af1882720068e84d161e6ba2`
- Canonico sugerido: `HOME\Segundo Cérebro\Notas Illustrator.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Notas Illustrator.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 665: hash `cbea87e84d35a4546874f032fe0d46ec9e4c1c2b74641317a5947115e6c0368c`
- Canonico sugerido: `HOME\Segundo Cérebro\Duplique um elemento no Cinema 4D.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Duplique um elemento no Cinema 4D.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 666: hash `fbb795fce7c740f7730166d4fcb227a1a955f3d9f184d4e640e9ef561fd9314e`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre o temo Ducking.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre o temo Ducking.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 667: hash `82898d8023a735c7b230434fa40b6805eb8ed35181cc75676201c58ee1893abf`
- Canonico sugerido: `HOME\Segundo Cérebro\Vector.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Vector.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 668: hash `720736cd3d6eae7ceef3448177a71e9dc8e582a279dc909c1bce4c0b0bd55463`
- Canonico sugerido: `HOME\Segundo Cérebro\Escalonando máscaras AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Escalonando máscaras AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 669: hash `2e6d813a9ea195aa20b378a91265d233a22fbaa7ef2177953922bf7993c2e21a`
- Canonico sugerido: `HOME\Segundo Cérebro\Composição e render no Adobe Premier.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Composição e render no Adobe Premier.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 670: hash `62c7fba0806f70c59ae15f0c68d7bc571a800614b554e34d42f640b0652188d2`
- Canonico sugerido: `HOME\Segundo Cérebro\Customer Centric.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Customer Centric.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 671: hash `6df883133bd589e30d6d175f4eeb489a7313579f85ef56248382d00e0d5885e3`
- Canonico sugerido: `HOME\Segundo Cérebro\O objetivo de uma campanha de tráfego.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\O objetivo de uma campanha de tráfego.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 672: hash `2999473812be2372b22c8033dda1e313574d0e9f01cc5e507bd447ffee0e2061`
- Canonico sugerido: `HOME\Segundo Cérebro\Edição de vídeo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Edição de vídeo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 673: hash `e7783e0543bf08aa0ea0301521b43711e3c7e582f97124a3ff5f9501c64eaca6`
- Canonico sugerido: `HOME\Segundo Cérebro\Criando Camadas de Ajuste.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Criando Camadas de Ajuste.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 674: hash `0a99cdd8d6e7daf331c5ff07e312a0d0685c64cefebea3db6a47fb5705495c06`
- Canonico sugerido: `HOME\Segundo Cérebro\Manoel Motos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Manoel Motos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 675: hash `a89983be042f4c9fa294886a300b5aa9565836ed3a8edd06fb8550090260b435`
- Canonico sugerido: `HOME\Segundo Cérebro\Motion Bro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Motion Bro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 676: hash `2827d46e26d85f3ee17680a6e43f2cce3e4df11b558c3d30b92080b599b3ff75`
- Canonico sugerido: `HOME\Segundo Cérebro\Taxa de conversão.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Taxa de conversão.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 677: hash `5376b8a7b5ba7423a7ba244db2234a00994e6e2dc23a87842c7cf6c6a7e90942`
- Canonico sugerido: `HOME\Segundo Cérebro\Tracer.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tracer.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 678: hash `963d23cb6801d7ec40fdd0a615b5fd69d182faa3edeb52b32c08c54eb0d32cbb`
- Canonico sugerido: `HOME\Segundo Cérebro\House Academia.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\House Academia.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 679: hash `1c614cf61ac17c56c28e7d776d8f2490ef977f8d9de021b24db639a622a553fe`
- Canonico sugerido: `HOME\Segundo Cérebro\X-Ray.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\X-Ray.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 680: hash `e27837a1a542720e483336fe689449de1b2da342903651c96631703d42afbca3`
- Canonico sugerido: `HOME\Segundo Cérebro\Fundamentos - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Fundamentos - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 681: hash `f05f68b48fd48197157fb4942d7230d314ef9eefcd715e865635c532e3b0f3b2`
- Canonico sugerido: `HOME\Segundo Cérebro\Mecânica Brutus.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Mecânica Brutus.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 682: hash `91566ddd0e655c46c15e4ae498ef6efcf1993dfca71bbada41928cc24e5ef2c3`
- Canonico sugerido: `HOME\Segundo Cérebro\Blogs.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Blogs.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 683: hash `b5fe8283dc8a143de4037677af1f377ed0c5f50e2ec40b056a2754de356b2967`
- Canonico sugerido: `HOME\Segundo Cérebro\Desenho tipográfico - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Desenho tipográfico - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 684: hash `0bb6ebe00021194f24eecde4c2c201da496f36408e4ba5c0c6161dbb7a9f34cf`
- Canonico sugerido: `HOME\Segundo Cérebro\Fernando Magalhães.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Fernando Magalhães.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 685: hash `64dc14479f0f0b8dee00f5a694157ed31dafeb3cdc2010a0f29e82dfbe1f28f0`
- Canonico sugerido: `HOME\Segundo Cérebro\Liber Marketing.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Liber Marketing.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 686: hash `c41bd1e50f91c94e9de6ee2a03601b52a74c666dddaedad54d7a7acc3fc64a0b`
- Canonico sugerido: `HOME\Segundo Cérebro\M02A05 Propriedades dos Layer.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M02A05 Propriedades dos Layer.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 687: hash `7886cb3c7c2bac48ce8ccca91020989636f24b028c979936fa74aa12b13f6e48`
- Canonico sugerido: `HOME\Segundo Cérebro\O poder do 3.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\O poder do 3.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 688: hash `45b90677f9770fc722cae93e02ff6733b82e6c4c2649a50c8415a5efaa70043e`
- Canonico sugerido: `HOME\Segundo Cérebro\Estoque.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Estoque.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 689: hash `5b81ee1da0c84972ae223a0308951d39e11ecf44d98d3f5f8b417eacc0f2db6c`
- Canonico sugerido: `HOME\Segundo Cérebro\O After Effects mescla arquivos PSD CMYK ao importá-los.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\O After Effects mescla arquivos PSD CMYK ao importá-los.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 690: hash `7b0077ff87a3d0d0d75ee05d3cda95a66f25b4ea0a57b8bc6e333b476d0fc4d2`
- Canonico sugerido: `HOME\Segundo Cérebro\Composição no After Effects.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Composição no After Effects.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 691: hash `d80fb8ef1a8f75bb484cf4cd43d992a6f10195bacb4e6bf47e4a9791c469bc54`
- Canonico sugerido: `HOME\Segundo Cérebro\Expressões interagem com efeitos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Expressões interagem com efeitos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 692: hash `f7d117dce936e61cb5f17513d7b5dadaa85ac9ec4cf57556caf17b172c312f2b`
- Canonico sugerido: `HOME\Segundo Cérebro\Loop Path Cut.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Loop Path Cut.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 693: hash `1b53bfa3f7188a93c5f2baf66feb00b5ccbedfd8f1cd6faa4b0d0025022bc870`
- Canonico sugerido: `HOME\Segundo Cérebro\Sapphire.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sapphire.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 694: hash `cd99ceb1570018f178b13f5333a902f44bf5f33db66f98a2e2cddcbebdffdca0`
- Canonico sugerido: `HOME\Obsidian doc\tudo em um lugar\Como organizar o fluxo de análise - Por Rical.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Ágora\Ágora Obsidian\Para roadmap\Como organizar o fluxo de análise - Por Rical.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Esta em sub-vault aninhado; revisar sem cruzar fronteiras automaticamente.)
### Grupo 695: hash `8308f66215d4271398c6238152a5d66c9a70e16288b5f6db006351628879086f`
- Canonico sugerido: `HOME\Segundo Cérebro\Fluxo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Fluxo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 696: hash `084cd3efe49804f60b2945f55958d8db332cf2c6837de5d38b1df0a4d5c956a7`
- Canonico sugerido: `HOME\Segundo Cérebro\Use LUTs.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Use LUTs.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 697: hash `9d5e9882717f17b228133770dd596087ac470734157525900923c7aab6b8c932`
- Canonico sugerido: `HOME\Segundo Cérebro\Action FX Pro - PixFlow.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Action FX Pro - PixFlow.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 698: hash `a91e58fe966c17b991ddc18dbce7bcf48e5018729472aef1f5eab201f7c264fd`
- Canonico sugerido: `HOME\Segundo Cérebro\Curves.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Curves.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 699: hash `cac75e46f05abf00989da719f97732e34727188ee4c6ebf378538167f130b989`
- Canonico sugerido: `HOME\Segundo Cérebro\Voxel Size.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Voxel Size.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 700: hash `27673ae706b70ca320ceea61144c93c4362d8e2acd5dab5a6fab1cac954e6237`
- Canonico sugerido: `HOME\Segundo Cérebro\M04A03 Criando a primeira expressão no After.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M04A03 Criando a primeira expressão no After.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 701: hash `f75fc820b5d81c33798f8eccd6e6a14f013e44a3c09c8e13837c53dbca8a84ad`
- Canonico sugerido: `HOME\Segundo Cérebro\Para fazer aparecer a interface de animação.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Para fazer aparecer a interface de animação.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 702: hash `a4b8f00fc642f0981b128b1ebde1f1c7aba737938b813bf3f110ac1caf5bab21`
- Canonico sugerido: `HOME\Segundo Cérebro\Blending Modes no Premiere.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Blending Modes no Premiere.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 703: hash `f6083981d7b21dc0c40af45277c630e9038cd06f17294e247522c6dcfb2eabc7`
- Canonico sugerido: `HOME\Segundo Cérebro\Comtatto.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Comtatto.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 704: hash `58ea3035af709cf2e7edef2f40b75c8dd4042ea6071be516841e2b9d8b06f880`
- Canonico sugerido: `HOME\Segundo Cérebro\Notas que tenho que resolver.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Notas que tenho que resolver.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 705: hash `ac7bd0e8a4238bb300a727d814e01b00a53bd0582bfc9c49f2222d3a2b3e5ffb`
- Canonico sugerido: `HOME\Segundo Cérebro\Aula 02 Introduções diversas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Aula 02 Introduções diversas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 706: hash `65e473797554cb978e2aaab5408924c729cf9b914eb15b84491a3f338d97e737`
- Canonico sugerido: `HOME\Segundo Cérebro\Deep of Fied ou Profundidade de campo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Deep of Fied ou Profundidade de campo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 707: hash `39b127fbf8ddd6103259e8d854609833458bd6a68baaa580d6ec5a94f9d53ec1`
- Canonico sugerido: `HOME\Segundo Cérebro\Ricardo Veículos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ricardo Veículos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 708: hash `8c77434e3e4e89d394e49345f84917945509201960e610ea508657a8afa28607`
- Canonico sugerido: `HOME\Segundo Cérebro\Stroke.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Stroke.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 709: hash `eb86743fd4c589cdade45073527a0463b2b251c7be895ed014519085f367c79a`
- Canonico sugerido: `HOME\Segundo Cérebro\HDRI.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\HDRI.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 710: hash `aad2c2bad274c3e298ae7e0752f8452487c5dcbd76bc230c234ab2350fbe9c0a`
- Canonico sugerido: `HOME\Segundo Cérebro\Joysticks ‘n Sliders.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Joysticks ‘n Sliders.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 711: hash `38b02d26cff7e7c7695c171f45b7da76ed36d7310a34424c4aacaf74fcbc61bd`
- Canonico sugerido: `HOME\Segundo Cérebro\Inspirações do Yogo Costa.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Inspirações do Yogo Costa.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 712: hash `d3e0113355c598cc2c6b104c38acc64b12bae4bbfba79fb71800640bc8fe6177`
- Canonico sugerido: `HOME\Segundo Cérebro\RSMB.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\RSMB.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 713: hash `32b9ef8a8ad53783faef795045e43087dfa33edac30da47b749260612b87c95f`
- Canonico sugerido: `HOME\Segundo Cérebro\Grade Curricular.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Grade Curricular.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 714: hash `25a0caed0879256525e8232244f97ee46526873874fedddb24a3d0dee2e8aea9`
- Canonico sugerido: `HOME\Segundo Cérebro\Transformando contorno em caminho.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Transformando contorno em caminho.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 715: hash `18e288be1fafb90c9ad28fb09fd23e4c741b10068ea12eff4eeaabf319f4c8b4`
- Canonico sugerido: `HOME\Segundo Cérebro\Keyframes com Câmera Ativada.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Keyframes com Câmera Ativada.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 716: hash `76c9945467f5e221bebd1724547702addf824438fff640e31a350ee87260f434`
- Canonico sugerido: `HOME\Segundo Cérebro\Para baixar apps pagos da Microsoft Store de Graça.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Para baixar apps pagos da Microsoft Store de Graça.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 717: hash `4a28c1278ea2eb18cf5a354833d78a5f5e563803fefd26fe9140d76515b7887b`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A13 Como criar máscaras.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A13 Como criar máscaras.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 718: hash `3e7425e8109e795c115c321b8af67a3dd611f3cd776271dd161efeb2ab599013`
- Canonico sugerido: `HOME\Segundo Cérebro\Ocultar no Render e Viewport.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ocultar no Render e Viewport.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 719: hash `29625407515f5471f5a8558d23d9fae4b8c673821df110fefab1fd5cb28ffffe`
- Canonico sugerido: `HOME\Segundo Cérebro\Como tratar melhor as pessoas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Como tratar melhor as pessoas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 720: hash `d8e2fcd2bdc202f2e3918f193fc07b2ffe61e1c1a643583043648a0e88112b18`
- Canonico sugerido: `HOME\Segundo Cérebro\Escaleta.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Escaleta.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 721: hash `69ab1a91e719b8583174ec665ae924426ec2ae172aef35bd9c664215da97164d`
- Canonico sugerido: `HOME\Segundo Cérebro\Premier.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Premier.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 722: hash `db1791c07e17ef653a58dce2fb3689b42f9814580d51f9823fc4d1bfdef67ec6`
- Canonico sugerido: `HOME\Segundo Cérebro\Tratamento de cores.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tratamento de cores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 723: hash `71d7c7fc940873c97e4454d0213160353a4ef58e8fa54483f8c9606e55b01cd8`
- Canonico sugerido: `HOME\Segundo Cérebro\Zach Liebermann.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Zach Liebermann.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 724: hash `725df25affc576307befdb803f46970e9b5c1685cdd240c1b49800ff5d02197b`
- Canonico sugerido: `ACIRV\Notas\Release - Pós Workshop NR-01 na prática.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\ACIRV\Notas\Release - Pós Workshop NR-01 na prática.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 725: hash `70757d32185653e32457207a44407237a1f4245854b535ec525186b9b2c9b0dc`
- Canonico sugerido: `HOME\Segundo Cérebro\Introdução ao design de tipos - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Introdução ao design de tipos - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 726: hash `a6add229f986317dde9913bb0576d49e293bb96a369389f6798fb32d9f630113`
- Canonico sugerido: `HOME\Segundo Cérebro\Top Rodas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Top Rodas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 727: hash `90eebd27942b8eb82316f7a568e323610f78847abffea4870de5f23a73565a2d`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A05 Preparação do projeto para animação.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A05 Preparação do projeto para animação.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 728: hash `4ea8404dc727f39f6b28c8dff6e7eff2f79e9b07263d1fdc99a4557221a3262c`
- Canonico sugerido: `HOME\Segundo Cérebro\Para descobrir o Valuation - Com velho da Havan.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Para descobrir o Valuation - Com velho da Havan.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 729: hash `4747bc593ca29d8bad03fa886834c0621f557a430941e793d571d8438790f4a6`
- Canonico sugerido: `HOME\Segundo Cérebro\Trabalhando com LOG - DAP 2.0.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Trabalhando com LOG - DAP 2.0.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 730: hash `aad129e53d559d3432cbad1d51c3eb5bf5f0717442395c9d2e6c2a14a37a1de1`
- Canonico sugerido: `HOME\Segundo Cérebro\Limitações de Animação com 3D Avançado e Cinema 4D.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Limitações de Animação com 3D Avançado e Cinema 4D.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 731: hash `f0fe5fe0b15f5fa1c4e13a37d3ce5ee1cb2d21c45f02f18c92fd5d3a716c4e35`
- Canonico sugerido: `HOME\Segundo Cérebro\Lumetri Color.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Lumetri Color.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 732: hash `a20a6ff3d110fcb37edd61f37b1aa4ff8494d87eddf674925af5ee093ddc1529`
- Canonico sugerido: `HOME\Segundo Cérebro\Text Break.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Text Break.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 733: hash `0aec9f81e0481ea547f970806caf75e89f06fdf14f1694308f224f43e1ce63bc`
- Canonico sugerido: `HOME\Segundo Cérebro\Efeitos coloridos - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Efeitos coloridos - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 734: hash `be5533cba24c4b643414a8e65b13c2b120399d3b8429be6bec38420f6257bf2e`
- Canonico sugerido: `HOME\Segundo Cérebro\Profissional.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Profissional.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 735: hash `2354e60bce6e8ac4c39ef8ca91e96f32551bd407d04181ad7d325ec43f749314`
- Canonico sugerido: `HOME\Segundo Cérebro\Anotações PS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Anotações PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 736: hash `c3ebe6dd00d079a077de969e5c956bca3d5f9c681d81cf8fd891575da01a7ff1`
- Canonico sugerido: `HOME\Segundo Cérebro\Hoor Digital.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Hoor Digital.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 737: hash `f4ab1509f0ad8f4c18adcf01ec52443b1f9aa4cb79b921b85386d83c8df825db`
- Canonico sugerido: `HOME\Segundo Cérebro\Linear Color Key.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Linear Color Key.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 738: hash `4efebfa5ceb34a51133cf7146a3a028f677c85d18177035e23923e1579822acc`
- Canonico sugerido: `HOME\Segundo Cérebro\Navegação na viewport com câmera 3D no AE.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Navegação na viewport com câmera 3D no AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 739: hash `48f87d73e39e291883d92e574418c422e71a574801253394a1608352c849b8ad`
- Canonico sugerido: `HOME\Segundo Cérebro\Chaves Lincon.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Chaves Lincon.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 740: hash `4de1280b5ec4aafca8f5a1f030426bab52c76e8cc6c880309714031d5f176718`
- Canonico sugerido: `HOME\Segundo Cérebro\Atalhos C4D.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Atalhos C4D.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 741: hash `b9d4014565e393872d4b5028b8efa985ebde65286e18a19ff2ab822c0a335430`
- Canonico sugerido: `HOME\Segundo Cérebro\Echo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Echo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 742: hash `6d33db43596158479a8dbe56e4c06914dd4d0b1f5afa862be0e8d38684b72165`
- Canonico sugerido: `HOME\Segundo Cérebro\O forte do PS é manipulação.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\O forte do PS é manipulação.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 743: hash `1d7a72372ff8b11fca486332a79f4f4a402d5ca0faa819dd11c0b4b668af31d8`
- Canonico sugerido: `HOME\Segundo Cérebro\After Effects.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\After Effects.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 744: hash `d1ab70b023863b4d9d6052f52e438e9aa3892c84e5ecc349f737be730150bae7`
- Canonico sugerido: `HOME\Segundo Cérebro\AutoKeying Ativo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\AutoKeying Ativo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 745: hash `84b890b48db7df0fce1ac8c390a2b4e94c553edfd5e241f76a20e3a6b5fa61f1`
- Canonico sugerido: `HOME\Segundo Cérebro\Motivo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Motivo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 746: hash `697556b9e881213986151c05616ae88f07cea02a5031e1d2799cedc3328646e8`
- Canonico sugerido: `HOME\Segundo Cérebro\Renderizador Octane.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Renderizador Octane.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 747: hash `8db21eb642ffbf15d2823de1407a75d744b750e4fb0a87a31607164fd8b9b0eb`
- Canonico sugerido: `HOME\Segundo Cérebro\Separando expressões.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Separando expressões.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 748: hash `2773910ae2858654a13d214af4b5070c064c48498396f3297bab808b4a0b4a75`
- Canonico sugerido: `HOME\Segundo Cérebro\Texturas Nativas do Octane.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Texturas Nativas do Octane.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 749: hash `f38a7a432e225fadc3d6645f763786a3f6973ea04d38b8c49f2b7d75609b2b43`
- Canonico sugerido: `HOME\Segundo Cérebro\Fx Console ou Video Copilot.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Fx Console ou Video Copilot.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 750: hash `708c72383d80334c1ca4681e87683f552137a81ec5108358b7bff91041031fe5`
- Canonico sugerido: `HOME\Segundo Cérebro\Impulso Marketing.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Impulso Marketing.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 751: hash `39e920ee84b07b1044d3bebccb5228c954f3e883b9b1f7ff0c91c28ec9f66c8d`
- Canonico sugerido: `HOME\Segundo Cérebro\Reverse.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Reverse.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 752: hash `8e13434ca218f98983018b1c97f338ed9745ede647b581165213b7b589e11dc2`
- Canonico sugerido: `HOME\Segundo Cérebro\Foto Panorâmica para Tracking.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Foto Panorâmica para Tracking.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 753: hash `da0a36b673a69058ae4f15192ed80410516b16a42535af56607b39557c698002`
- Canonico sugerido: `HOME\Segundo Cérebro\JS + Expressões AE = Eficiência máxima.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\JS + Expressões AE = Eficiência máxima.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 754: hash `ba7d61030de10b2b8b1d318ebb3d802594b34faf9422703c4e634589bd35bdc2`
- Canonico sugerido: `HOME\Segundo Cérebro\Timewarp.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Timewarp.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 755: hash `3d500ddc42feb77142d241aaed5805a54bb8ad52e9b7e40f19b5eb11d0f2bdaf`
- Canonico sugerido: `HOME\Segundo Cérebro\Produtividade e Gestão.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Produtividade e Gestão.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 756: hash `c20903adabb9a91d07d45480b98af9530e38a7d32e4a5b69af89aea6e6bb9810`
- Canonico sugerido: `HOME\Segundo Cérebro\Adobe Typekit.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Adobe Typekit.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 757: hash `c2b3247513ab24e60baa91fd1725b019905d2df92c89a28ac848894e1bdb40cf`
- Canonico sugerido: `HOME\Segundo Cérebro\Composição de uma peça audio-visual.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Composição de uma peça audio-visual.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 758: hash `3ede57d4de44cdde6b4f348cc35401e3920bab72b605d4db6b9381a0fa68fad5`
- Canonico sugerido: `HOME\Segundo Cérebro\@thisset.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\@thisset.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 759: hash `614ad0a90eacc17c3795e91e55e18c67cb232eb8ee171a1963fcf10d0f39aaae`
- Canonico sugerido: `HOME\Segundo Cérebro\Clone.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Clone.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 760: hash `2ef7580c1c8b18c4cf97f9eb5d610a54f784e108b49d4614ef73a23737026752`
- Canonico sugerido: `HOME\Segundo Cérebro\Break.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Break.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 761: hash `8d9f7394c1ab7832728f5fbd6f56848d9f1537f455db4ab3a8fd9d346132dd88`
- Canonico sugerido: `HOME\Segundo Cérebro\Parent.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Parent.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 762: hash `d6f2517b9902024482c57b05f78072250c558c5b441c3985adaa177c9db79662`
- Canonico sugerido: `HOME\Segundo Cérebro\Plugins PS.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Plugins PS.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 763: hash `c5a227f7af121fd19f1a5794e20c06bb95d84852bb0e04da4eac9aba03f43b42`
- Canonico sugerido: `HOME\Segundo Cérebro\Rosa de Saron.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Rosa de Saron.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 764: hash `1924c869fe6a50d066b2105de42678977103b3c62a5e0c22a97022642cb894bf`
- Canonico sugerido: `HOME\Segundo Cérebro\Brazu.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Brazu.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 765: hash `c8bf9e7dbb4f5fc0e6dd02cd1679e2cc81e5c8f9f9bce90966573cb318bd2197`
- Canonico sugerido: `HOME\Segundo Cérebro\M04A01 Como criar texto no After.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M04A01 Como criar texto no After.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 766: hash `6f9cca8f73c848983bbccc934bda806aac10915439dee41f48dc747f93c68fd2`
- Canonico sugerido: `HOME\Segundo Cérebro\Quixel Bridge.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Quixel Bridge.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 767: hash `2a473a72b5f56934f672987140de57b36f6dd0307e45eae577a49f269a0464a3`
- Canonico sugerido: `HOME\Segundo Cérebro\Inspirações - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Inspirações - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 768: hash `b960622d2ee06c6c5a06350cfd60b860daeab05c545f6c21c897e7c20e92c67b`
- Canonico sugerido: `HOME\Segundo Cérebro\Riofer.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Riofer.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 769: hash `ed7c37a9eae7e6e5b59224f7d7eddc230feb488a6ddeb0c687e08bd1dae15570`
- Canonico sugerido: `HOME\Segundo Cérebro\Tracking.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tracking.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 770: hash `5a48c74ba9eb56cdf94628e9213bcc837c0b2b34a7b858964e574d42d945bcde`
- Canonico sugerido: `HOME\Segundo Cérebro\Aula 01 Como configurar a interface do Illustrator.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Aula 01 Como configurar a interface do Illustrator.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 771: hash `36309caf49552689095704a699f782dae8574a1f69e8e188602ac0a492c57b06`
- Canonico sugerido: `HOME\Segundo Cérebro\Lavanderia Popular.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Lavanderia Popular.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 772: hash `13987301c749398a19bd782fa53f13ce164177868deae9d0321700d752041d0e`
- Canonico sugerido: `HOME\Segundo Cérebro\Música Barroca a 60bpm e 40hz neural beats afina o cérebro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Música Barroca a 60bpm e 40hz neural beats afina o cérebro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 773: hash `7140a09b5f3b9ab586b2a4e28353c3ce91cc8d68f772177bffb499a3de0c5a20`
- Canonico sugerido: `HOME\Segundo Cérebro\FXMonster.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\FXMonster.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 774: hash `66b4c21d95bb16537f72f9da7b45349c5373a16e9ea0a0a7e7e82162d35b963a`
- Canonico sugerido: `HOME\Segundo Cérebro\Ighor Barbeiro.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ighor Barbeiro.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 775: hash `481d896ce10de8acad632d1404be8156eab2827199f561b1048c0c68ee8e9c7c`
- Canonico sugerido: `HOME\Segundo Cérebro\Lei de Mason.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Lei de Mason.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 776: hash `460641ddf5feffb60f0e3ce88e90a841b08c3a2570abf38ab66cf62ed673f4e5`
- Canonico sugerido: `HOME\Segundo Cérebro\Parâmetros Animáveis.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Parâmetros Animáveis.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 777: hash `5f83443ad0e14e63465ce40d0f94ab3b2256287db7096a0f9ec5e5b48ea4f99c`
- Canonico sugerido: `HOME\Segundo Cérebro\Prévia organização de arquivos para AE.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Prévia organização de arquivos para AE.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 778: hash `b0cf57cf443c98b0e4a82c4a80a136930e6efa11db38262d5f22b814ee0127c5`
- Canonico sugerido: `HOME\Segundo Cérebro\Ollavo Lavanderia Popular.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ollavo Lavanderia Popular.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 779: hash `c7dcb8deb88039f7c36a0e36da4c53d48336438796a08fa90a1ad577f2b720e2`
- Canonico sugerido: `HOME\Segundo Cérebro\Templates Obsidian.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Templates Obsidian.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 780: hash `74650e63d568ed1472fa748508237818deff864689fe50f0617cc3135ff1c39e`
- Canonico sugerido: `HOME\Segundo Cérebro\Seed.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Seed.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 781: hash `8543b4c035b0d103b10c25425706203e8be7a3fd4f1d3f3288ae3003e1c7094c`
- Canonico sugerido: `HOME\Segundo Cérebro\Campanha de Lançamento - Óculos de Leitura..md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Campanha de Lançamento - Óculos de Leitura..md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 782: hash `a1444f3b79cd241bcf804181f809e602ce962c1f4f3edb41e0caa17860889461`
- Canonico sugerido: `HOME\Segundo Cérebro\Greyscalegorilla.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Greyscalegorilla.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 783: hash `1b5bf7592de4d34b025252ed637bdf666d5e8568ca0aa19b8bce127913e8a9f9`
- Canonico sugerido: `HOME\Segundo Cérebro\Hidra.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Hidra.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 784: hash `05b6b865c953fb9b0899b9309e25fe3ab534e9e7c35f6bd720438cd83210936e`
- Canonico sugerido: `HOME\Segundo Cérebro\Burst.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Burst.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 785: hash `30cf2e59b0655254222578947079f24d6b2ac103ebd4d1ac47d97ddc9348bd99`
- Canonico sugerido: `HOME\Segundo Cérebro\Animo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Animo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 786: hash `e11844ed555f5decbce316627496b4b46db953b0ec45b19aa9c2bb8b5220f205`
- Canonico sugerido: `HOME\Segundo Cérebro\Efeitos Premier Mais Usados.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Efeitos Premier Mais Usados.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 787: hash `2dcde78932f56aeb8bfc28fe727c9c931dfdd98d28a4b2e1ee4c6535c708337c`
- Canonico sugerido: `HOME\Segundo Cérebro\Loop simples em formas de máscara e outras propriedades não numéricas (Curvas, por exemplo).md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Loop simples em formas de máscara e outras propriedades não numéricas (Curvas, por exemplo).md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 788: hash `3a9e3a7305bf7102342dd6aeecc62787dd52330fe32d755cd42ccd68b1d3332f`
- Canonico sugerido: `HOME\Segundo Cérebro\M03A06 Animação de Layers em Blocos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M03A06 Animação de Layers em Blocos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 789: hash `2a7e232a7583f3306cf656f454046354495e9635a8b0928e3b3cf326081f616c`
- Canonico sugerido: `HOME\Segundo Cérebro\Modos de Visualização.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Modos de Visualização.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 790: hash `7922140cbf3d878447bdb45aa85bd39c1acd60408fafe33343dd6989b57501a2`
- Canonico sugerido: `HOME\Segundo Cérebro\Effect ► Transition.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Effect ► Transition.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 791: hash `30bc53908540ff440c95cccb99ff21706815aca474ccd41cbe6f999d304f9edc`
- Canonico sugerido: `HOME\Segundo Cérebro\Pós-produção.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Pós-produção.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 792: hash `f204204db03dc0063e148f8de887d7c72c68463f493405e3fb30acd9b4cdd47e`
- Canonico sugerido: `HOME\Segundo Cérebro\Tornado o padrão de transição de aúdio para 6 frames.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tornado o padrão de transição de aúdio para 6 frames.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 793: hash `bebcf0cd0d4aebbbba7d6fd1fd890db3af7dc9e23fd7869eb5bff6585bd87ffd`
- Canonico sugerido: `HOME\Segundo Cérebro\Casa do Sabor.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Casa do Sabor.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 794: hash `cca09378d1d9668746005984213a2d7cea03027f14064e10a62465c7ea399be6`
- Canonico sugerido: `HOME\Segundo Cérebro\Cineware.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Cineware.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 795: hash `04e2665a26f04f44ec503d0d0b0d9122fa4137198e1c1b8e521f528f0546da99`
- Canonico sugerido: `HOME\Segundo Cérebro\Tritônico.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tritônico.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 796: hash `680bbeeae60b49c63f9ceb7527c898e05e85976edbf52e78786a1b9ef801bb95`
- Canonico sugerido: `HOME\Segundo Cérebro\Wrap.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Wrap.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 797: hash `402f085e3e67627ea57c6987b6ce8936cee92a505cb1271257b624f3f969fa77`
- Canonico sugerido: `HOME\Segundo Cérebro\Math.round().md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Math.round().md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 798: hash `b41ce4eb2c6f9ad2a65c241f200f76e7c49cfa4c1198660eb202ddf8cc1e431e`
- Canonico sugerido: `HOME\Segundo Cérebro\Efeitos de distorção - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Efeitos de distorção - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 799: hash `ff8540fbe89263c278aa0dfbca8d8666da552331affcf8375ea9d85bdd83e08a`
- Canonico sugerido: `HOME\Segundo Cérebro\Master Place.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Master Place.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 800: hash `a44896bc594a16e9ff4841a47c6df20da1c1a10ddaa3bcf52eb26d3a7d78f986`
- Canonico sugerido: `HOME\Segundo Cérebro\Nota inversa.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Nota inversa.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 801: hash `32057d23efb62cf4be797da3b67f613bdc137cce5829954ea048e13c5b3e7810`
- Canonico sugerido: `HOME\Segundo Cérebro\Ordem de objeto máscara e objeto a ser mascarado.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ordem de objeto máscara e objeto a ser mascarado.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 802: hash `2ac11429b6c985c36515e428d7a135917bed8e73e5c4bfdbde84c3dde204fdd4`
- Canonico sugerido: `HOME\Segundo Cérebro\Stare.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Stare.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 803: hash `e02a43b179ff8089796cc738bfa439f1a82dc1c1310ea54826ebee184d46790e`
- Canonico sugerido: `HOME\Segundo Cérebro\Bevel.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bevel.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 804: hash `e9cbeec88afaf7dbc5933d1d443f59eef2137d19ee38007dd46262d25c520c1d`
- Canonico sugerido: `HOME\Segundo Cérebro\Simulações de Física C4D.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Simulações de Física C4D.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 805: hash `96743b700e8f3a677cd3efc8502aefe6de17998dee38190ab1014b40ea56abf9`
- Canonico sugerido: `HOME\Segundo Cérebro\Allan Produtos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Allan Produtos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 806: hash `a751be9d9e68089a90029924e76e7ac8a837c3ee041284a378d068120db4ec39`
- Canonico sugerido: `HOME\Segundo Cérebro\Trasher.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Trasher.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 807: hash `2f4628dab03a0573b9f6a63a043eda378c4cc7aecc1c3f093911ea05e5f18d79`
- Canonico sugerido: `HOME\Segundo Cérebro\(PSICOMETRIA) Essa é a palavra da próxima era da IA.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\(PSICOMETRIA) Essa é a palavra da próxima era da IA.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 808: hash `2c344093990352ab9ff64d2dfa5778506fa4f199f3c40f080f53f6b189cef20b`
- Canonico sugerido: `HOME\Segundo Cérebro\Extrusão com Ctrl.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Extrusão com Ctrl.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 809: hash `2e20aa48cd5212b6f09fcadb50ceb89e87649f51b370dc7a262251b499aa4c2e`
- Canonico sugerido: `HOME\Segundo Cérebro\PSD Codec.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\PSD Codec.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 810: hash `2c34e5e5a1bd31365816650c842c77638ba803ba9d989e045ee14dcc5cd5c724`
- Canonico sugerido: `HOME\Segundo Cérebro\Sobre o termo Power Window.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sobre o termo Power Window.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 811: hash `f9cca5ef68b51b2dc5023f49eb2dbf42b7bc216927b5f3c777d9ace9e3d907d6`
- Canonico sugerido: `HOME\Segundo Cérebro\Arquivos que preciso instalar.md`
- Motivo: Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Arquivos que preciso instalar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual. Localizado em area com sinal de espelho/import, reforcando revisao humana.)
### Grupo 812: hash `a940c84af9e9381a11d7f36f5149d6ec795cda7c65543a3118e079d17ce8b03a`
- Canonico sugerido: `HOME\Segundo Cérebro\Shadowify 2.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Shadowify 2.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 813: hash `313ad36e7e5781e2f66cf7794e862fc5db2a58215aed4fe41f6ca9ab8a10f65a`
- Canonico sugerido: `HOME\Segundo Cérebro\CSA segurança.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\CSA segurança.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 814: hash `2e5e55da7970bfea4b8c50e164caff4f8ca71fe6afa01cfe9748d8c9ef844838`
- Canonico sugerido: `HOME\Segundo Cérebro\Delay.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Delay.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 815: hash `68040414613d067bb635902f022e8ae6ad9679c68ec3343d5fe1719e9a7ca15a`
- Canonico sugerido: `HOME\Segundo Cérebro\PixImperfect Compositing.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\PixImperfect Compositing.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 816: hash `a6fa3667230b530383c4e79a6d2f472d4b13e59386090e83476af7dfe82d0c38`
- Canonico sugerido: `HOME\Segundo Cérebro\End Scale.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\End Scale.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 817: hash `db4c5dbc56268e38c84272772f14c1324a279b79210d73f070135a976f75a330`
- Canonico sugerido: `HOME\Segundo Cérebro\Introdução - DTTAP.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Introdução - DTTAP.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 818: hash `4a1635db41b5d1250c3da6d797c3f7d6200e774f8e862d8f23009b20ba326ef9`
- Canonico sugerido: `HOME\Segundo Cérebro\M04A08 Efeitos Básicos - Gradient Ramp.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\M04A08 Efeitos Básicos - Gradient Ramp.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 819: hash `178cf32c6d67ea9b526d0f3498a60d276098b932ddbd142fad46b7ca0e212816`
- Canonico sugerido: `HOME\Segundo Cérebro\Liber Nox.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Liber Nox.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 820: hash `ed60e0d9fb3a1f820561b920bfb7308464f1b0898eae34c9a127a3bb89ec6ac3`
- Canonico sugerido: `HOME\Segundo Cérebro\Texture.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Texture.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 821: hash `4ae4606710671eccadf96d542a4d12746396bbe61c29cf8b53e836e32f985d99`
- Canonico sugerido: `HOME\Segundo Cérebro\Roteiros para campanhas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Roteiros para campanhas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 822: hash `3dbd4473cb04cae45b45494d1c7eb2412f20c8b95aa202d1da74b6194b4739af`
- Canonico sugerido: `HOME\Segundo Cérebro\Gradient Ramp.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Gradient Ramp.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 823: hash `3078b8145be8ed87ba0952efa548c69d476db094425318350ac6fe75d4b3bc2f`
- Canonico sugerido: `HOME\Segundo Cérebro\mattiamediax.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\mattiamediax.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 824: hash `ed174db25e75e2b072b76bf89a6ac698c0d88f1913def43f5a47b583052f8061`
- Canonico sugerido: `HOME\Segundo Cérebro\Conta e senha do Proton VPN.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Conta e senha do Proton VPN.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 825: hash `dc2ee7533c53e70b72f39d522133504fc4bdc48b44d0e2cabb02c11d2d83cd94`
- Canonico sugerido: `HOME\Segundo Cérebro\Downloadgram.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Downloadgram.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 826: hash `ad2f53b6b9511c994124589425e477740fecfbdce4e69d886218dc9f5263fc58`
- Canonico sugerido: `HOME\Segundo Cérebro\Poly Heaven.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Poly Heaven.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 827: hash `3b17142a40db3ca5d8ffc1e9dacd5cb6ca1d24fc4d82c76822e6c8f8e7ccad83`
- Canonico sugerido: `HOME\Segundo Cérebro\Séries ocultistas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Séries ocultistas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 828: hash `68ecc9135af0f90b267b6738c180b04e19c7b0ab7703231d88065b51b3a41778`
- Canonico sugerido: `HOME\Segundo Cérebro\Duik.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Duik.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 829: hash `e89d9c78f77bb97aa6cd153a49e435fe02132108ff3b83902a3942ed1ac79695`
- Canonico sugerido: `HOME\Segundo Cérebro\Ninja do Açaí.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ninja do Açaí.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 830: hash `d7e368d13215313cd6115ae5806f0cda9beb76c62411efd3508ba1e069d5e13b`
- Canonico sugerido: `HOME\Segundo Cérebro\Pander.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Pander.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 831: hash `6b1e2829f8e748cbcd343a92539dbf3755ea557e61ffc0c5379a889a56f5a6c1`
- Canonico sugerido: `HOME\Segundo Cérebro\Photoshop.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Photoshop.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 832: hash `1e6d04611aecb321910eefae40129e6977b02b74d7fb4c1fa41bcdcb31233e6e`
- Canonico sugerido: `HOME\Segundo Cérebro\Unblast.com.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Unblast.com.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 833: hash `f9a0556170434e44c3356dc720b73918cc3b0ef683b640b267f460d49de49713`
- Canonico sugerido: `HOME\Segundo Cérebro\Guilherme - Megacell.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Guilherme - Megacell.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 834: hash `4e2d95f8d45a7be6395e918750e04493dccdd92bd1cbef013fdebda8666917d7`
- Canonico sugerido: `HOME\Segundo Cérebro\Nuva Glitch.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Nuva Glitch.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 835: hash `ff66344735decf3c0353ddcc508dd04727d1b7ae5d87a96b14fd4259f2e8a9e2`
- Canonico sugerido: `HOME\Segundo Cérebro\Melhores formas de vender como afiliado hoje.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Melhores formas de vender como afiliado hoje.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 836: hash `cdf82bc0a85341d80740d7369a5a0d1cd8d4634c38bb3a7d6fc72e45ad422dfa`
- Canonico sugerido: `HOME\Segundo Cérebro\Eixos X, Y e Z.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Eixos X, Y e Z.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 837: hash `01068520d33d03d3763a4f66c6951d9827aef93c495568d60eff515a91475f2f`
- Canonico sugerido: `HOME\Segundo Cérebro\Excite.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Excite.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 838: hash `7a1552a6ad814f78b2e9f4430460ef33abbbad27e5f19263e462dfbc1e4a8e3d`
- Canonico sugerido: `HOME\Segundo Cérebro\Pai e Filho Borracharia.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Pai e Filho Borracharia.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 839: hash `09543f227940bdb91e950bd80330ea9c0529ddba16d1062af38074066d9d7bcf`
- Canonico sugerido: `HOME\Segundo Cérebro\Tangencial.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Tangencial.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 840: hash `4cabd9aa657740b297a9a0d3dd29e5689b9efbf3452931e88058595240ae731e`
- Canonico sugerido: `HOME\Segundo Cérebro\Cine A - Shopping Rio Verde.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Cine A - Shopping Rio Verde.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 841: hash `2c535a065071505a5927f6c283500ca05b7ba221f6a3aa3313280d9d0d02390e`
- Canonico sugerido: `HOME\Segundo Cérebro\Frajolas Pizzaria.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Frajolas Pizzaria.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 842: hash `5b5a857995bde5e7f6d92f5a369f4f0536d05615e3cd8ffada3b287f99af178f`
- Canonico sugerido: `HOME\Segundo Cérebro\Milano Sorvetes.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Milano Sorvetes.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 843: hash `ab3e61da9d91a79e5c070861cdd5808681a17a9e5a6685b638aaea8f19a9c853`
- Canonico sugerido: `HOME\Segundo Cérebro\Top Car.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Top Car.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 844: hash `3fde69904b8433fea44c46242ca8afe56dc3304bc931f84552a35cb72887a761`
- Canonico sugerido: `HOME\Segundo Cérebro\ChatGPT e outras IAs pelo Telegram.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\ChatGPT e outras IAs pelo Telegram.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 845: hash `ff2a7ead4fc74cc2b2004d522e5c25f32faada3b2cd978c7c4a05699a08d7b81`
- Canonico sugerido: `HOME\Segundo Cérebro\Império Art Calhas.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Império Art Calhas.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 846: hash `f627f701ac38861094d4a9c0045651850c20c97698606ef459dda9980b341629`
- Canonico sugerido: `HOME\Segundo Cérebro\Skybox Blockade Labs.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Skybox Blockade Labs.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 847: hash `27a921df9d92fd242b4a8d160fc9aca2a676d0c22e6a883ef9196be237e37976`
- Canonico sugerido: `HOME\Segundo Cérebro\Sort.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sort.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 848: hash `1bad6f0b794f03eed2b59cceac55e38a2fa2ed532708672299900759370f8c9f`
- Canonico sugerido: `HOME\Segundo Cérebro\Bithrate viewport.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bithrate viewport.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 849: hash `e71fbb58cb5e35f2328d0136760cccb5e0a75ff41afd7cd453e9d38cbdef0489`
- Canonico sugerido: `HOME\Segundo Cérebro\Cacau Show - Shopping Rio Verde.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Cacau Show - Shopping Rio Verde.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 850: hash `71db4d7a7373f129a716270ec54ca9d8f82b9678fa62c2cf7fd219e148403ccb`
- Canonico sugerido: `HOME\Segundo Cérebro\Null.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Null.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 851: hash `93ea7450579053d9b5b0a68437ebfae269fbd0c18be6347104eb8048ca976856`
- Canonico sugerido: `HOME\Segundo Cérebro\Trim.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Trim.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 852: hash `63313eb15a359f796b7a5a131049b4a134ece249ac06b18ad87633c593bdca73`
- Canonico sugerido: `HOME\Segundo Cérebro\Contas que eu precisava estudar.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Contas que eu precisava estudar.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 853: hash `dfb2ffe0296688439df21f8668cb06f92f80587411daa170be5ec6cd064ea06c`
- Canonico sugerido: `HOME\Segundo Cérebro\Brightness & Contrast.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Brightness & Contrast.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 854: hash `3456ae6b602c30bcc3ece6b3ff48259dadebdfcc465eec0a1a67cd6960a47ed2`
- Canonico sugerido: `HOME\Segundo Cérebro\Illustrator.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Illustrator.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 855: hash `80a9b6fc43834e00ebfc508da639748d59e01e87aeea36b446d995f9949734e4`
- Canonico sugerido: `HOME\Segundo Cérebro\Sketchfab.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sketchfab.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 856: hash `4ec244c18161b93b5f13cce33ce30de5f27e67086437f4db14be5d630ecd28cb`
- Canonico sugerido: `HOME\Segundo Cérebro\Aula 03 Teoria das Cores.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Aula 03 Teoria das Cores.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 857: hash `9d061cb5b1532c495b44aa4319de9ef1401ac4557d32020f8bea43c49462931c`
- Canonico sugerido: `HOME\Segundo Cérebro\Mister Horse - Animation Composer 3.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Mister Horse - Animation Composer 3.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 858: hash `d42849693db19f264463b1ea37f5dbdbf7b2495bd900ab9c78c217bc6115dc35`
- Canonico sugerido: `HOME\Segundo Cérebro\Mockup Baker.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Mockup Baker.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 859: hash `1bd42ef6a9cc926ef19bd9db9f9ae3fdf39cc42e831f49d55aa577de7d9594d4`
- Canonico sugerido: `HOME\Segundo Cérebro\Ver essa aula depois.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ver essa aula depois.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 860: hash `11e30f036b660c14f029814fa99d98a747c9883b637057092611d1d2d7b6ddbc`
- Canonico sugerido: `HOME\Segundo Cérebro\Método GTD.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Método GTD.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 861: hash `f05fbfd0119c525269c447b04afc0c9467a4e90330b86e134e9a013ddd7f90b0`
- Canonico sugerido: `HOME\Segundo Cérebro\Dynamics.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Dynamics.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 862: hash `c2b0481c8f4e85874cce8955c1788ac3f1b2fb53750d89f8f6b505177cb5d32e`
- Canonico sugerido: `HOME\Segundo Cérebro\Extract.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Extract.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 863: hash `1cf7db3a25fc7e1db595af7815f5df9076ce8857d6d8e52b339859bf0a50559f`
- Canonico sugerido: `HOME\Segundo Cérebro\Fernando Brothers Cars.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Fernando Brothers Cars.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 864: hash `e4d5ee7d7e9b911cbc7c20e90d155008c66ddfd40e7c2905a11175b868e939e2`
- Canonico sugerido: `HOME\Segundo Cérebro\Pinplus.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Pinplus.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 865: hash `d8417353bc6e09ea2f95c53ea80b66c93959dbbccab19e8ee981cbfbc7105ad1`
- Canonico sugerido: `HOME\Segundo Cérebro\Rename.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Rename.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 866: hash `a968f1e1b8e9e1fa00972cd1d924d384817a1f4e43971961e552cb5a1fca4656`
- Canonico sugerido: `HOME\Segundo Cérebro\Spin.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Spin.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 867: hash `65903bb3ec063b96b2f166503d5f583dcbb39246667a70c2560ad87818ba3608`
- Canonico sugerido: `HOME\Segundo Cérebro\Start Emission.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Start Emission.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 868: hash `6239570a040edd1d17d11174315726244a1c75f6b37106fba64264e3c5184fa3`
- Canonico sugerido: `HOME\Segundo Cérebro\Gmailnator.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Gmailnator.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 869: hash `58dff62762abeb28d7721509e8e814a1244e8f92b1cc0faf8157c4fa9036f619`
- Canonico sugerido: `HOME\Segundo Cérebro\Inspirações de como criar conteúdo.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Inspirações de como criar conteúdo.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 870: hash `28deb2f9526970e879b3f7da8d3c2461c12514f3c5a6f18b3be5d605851a4d70`
- Canonico sugerido: `HOME\Segundo Cérebro\Teste de Tags.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Teste de Tags.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 871: hash `d3c7433336b0d4c2d9d986da4d7f0c3255d8e9a192eaf642e751fd40b6fdab88`
- Canonico sugerido: `HOME\Segundo Cérebro\Bithrate Renderer.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bithrate Renderer.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 872: hash `32fb98ec2f6331c95eebc1ac0ec2f31fc1cd70c22c8d31b7f321f3ecaa262203`
- Canonico sugerido: `HOME\Segundo Cérebro\Dru Car.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Dru Car.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 873: hash `8f6194096e02fe72b25caef66c96345c933ad6fa91358adc23ce23145ec3ebea`
- Canonico sugerido: `HOME\Segundo Cérebro\Trismegistus Coffee.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Trismegistus Coffee.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 874: hash `8ed9e8c9b5d52564d1b50a3fa58cf3f94c8fb66edd1f3055391763861144735c`
- Canonico sugerido: `HOME\Segundo Cérebro\Arte Ryka.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Arte Ryka.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 875: hash `ce3d0fc38f09402b5d006c2444e684b839d4955b8e3020cc2dfc7fd5c65adf87`
- Canonico sugerido: `HOME\Segundo Cérebro\Fernanda do mercadinho.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Fernanda do mercadinho.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 876: hash `c5df24047079d3e12fbe8b28a8a526e7ba5182f921d795ad9058b793b637996a`
- Canonico sugerido: `HOME\Segundo Cérebro\Natural Life.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Natural Life.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 877: hash `fda608e9b4dba422943d24b9bde777aa87b24fc2ef1991474ab09700cd0b4199`
- Canonico sugerido: `HOME\Segundo Cérebro\Bom lugar para comprar Scripts e Plugins.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bom lugar para comprar Scripts e Plugins.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 878: hash `7632d1990c1ec8b6ad5ebf434be2a1f2d5530e1dc9b5cab8f8993b08db1ff982`
- Canonico sugerido: `HOME\Segundo Cérebro\CC Particle World.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\CC Particle World.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 879: hash `ed53b44573ee31ba96fb8a9356b28719b50534e105f658acd2187b62e5f4a356`
- Canonico sugerido: `HOME\Segundo Cérebro\Color Range.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Color Range.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 880: hash `de75a0cd1d25a58f373361c007c28d3f5bcd7709ed153b005a00768964eb7632`
- Canonico sugerido: `HOME\Segundo Cérebro\Orbit.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Orbit.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 881: hash `5a9a1aefee19c74fdaaa14dbe192cc167729802240e44c788bdbbc5fdb9cb88b`
- Canonico sugerido: `HOME\Segundo Cérebro\Saturation.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Saturation.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 882: hash `071b50849e8b62b7149c663588408eabb2b71e98519b53bc12753bbe4761661f`
- Canonico sugerido: `HOME\Segundo Cérebro\Stop Emission.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Stop Emission.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 883: hash `06b57d32032cd0bae69f2e05b884ff6383543f6a7ab83c1ea593f3e24542e7b3`
- Canonico sugerido: `HOME\Segundo Cérebro\Mariane Ortiz.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Mariane Ortiz.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 884: hash `cb09877207e69a3770477df476f622d9919e133804a24ab4086c3fe3ee21036a`
- Canonico sugerido: `HOME\Segundo Cérebro\POE.AI.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\POE.AI.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 885: hash `b162ab2c1b3a2ada4a0b78d1b3d44a195b182ef2bb1d272cc667780d0396869d`
- Canonico sugerido: `HOME\Segundo Cérebro\Principais plataformas de tráfego.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Principais plataformas de tráfego.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 886: hash `8bfe693431042926ef31df4bbd725cdc3d86d061ff7330154a9a9b8bfea21bf8`
- Canonico sugerido: `HOME\Segundo Cérebro\Jump.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Jump.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 887: hash `c8e6775bae6e88960e9422f6b61df0963304a51e34de3bef87037598bfe44a1f`
- Canonico sugerido: `HOME\Segundo Cérebro\Ultracell.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Ultracell.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 888: hash `b68b0ca2b72f295e68a0a8db07fe2f45b9f5a1109142c735973f0385779104b9`
- Canonico sugerido: `HOME\Segundo Cérebro\Boa Forma.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Boa Forma.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 889: hash `f53744afbbe0cdb999e640a9b53b3bfea042d9a18724f5a318e384e46419e91a`
- Canonico sugerido: `HOME\Segundo Cérebro\CM Veículos.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\CM Veículos.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 890: hash `04c41c713bd0c0d1a8f4ac241a996dab5b97781bb7331fa39c12ce8e3652c11f`
- Canonico sugerido: `HOME\Segundo Cérebro\Luna da Geovanna.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Luna da Geovanna.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 891: hash `1d666ad7b128dc7086727aa9b9a2c4480920f8d07941c680f75eef9c32516913`
- Canonico sugerido: `HOME\Segundo Cérebro\Drop Shadow.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Drop Shadow.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 892: hash `7904e4779216d00dac1a83af4373467ecdd6ca70c296578eb14b52eab75d6f68`
- Canonico sugerido: `HOME\Segundo Cérebro\Lis Righetto - Achairê Studio.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Lis Righetto - Achairê Studio.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 893: hash `8204ea25045feff2d9b1d5721043a983227b5b5971d16b94a462d2d95de03d95`
- Canonico sugerido: `HOME\Segundo Cérebro\MD para PDF em Massa.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\MD para PDF em Massa.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 894: hash `d55b0cf51f10cb5e0b05c96fc2f744ef105093b2f87dc64e1c0cd4d4cdba5bab`
- Canonico sugerido: `HOME\Segundo Cérebro\Para transformar vídeo em png sequence.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Para transformar vídeo em png sequence.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 895: hash `66f54fa1e211eaed565a2b19de6e56c8ed3045a403324efb3be647feee9f30eb`
- Canonico sugerido: `HOME\Segundo Cérebro\Removendo os espaços em branco.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Removendo os espaços em branco.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 896: hash `df95ae825bd41b46a3c33d14c5181621652a3b8303c2a289f9b9303e3bf3a10a`
- Canonico sugerido: `HOME\Segundo Cérebro\Vídeos com IA para a Hoor.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Vídeos com IA para a Hoor.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 897: hash `25c5201483a537ce789cd6f043b02ce136e56d8d21994780ce5b58164af4e8a6`
- Canonico sugerido: `HOME\Segundo Cérebro\Blend.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Blend.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 898: hash `e707bc79e2675155df938ad1af7a04aea614207d15714465bda5f8ebcb22742a`
- Canonico sugerido: `HOME\Segundo Cérebro\RP Automóveis.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\RP Automóveis.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 899: hash `f76644a861ee2c0ab922419137e97715dd6173d68ca1b38327809497444ffb18`
- Canonico sugerido: `HOME\Segundo Cérebro\N8N.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\N8N.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 900: hash `86f2914645f27bd1f02097c94eff5733351ccfe27598529245c9df0e2bdfd887`
- Canonico sugerido: `HOME\Segundo Cérebro\Synfig.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Synfig.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 901: hash `1650726fa7591c442c33c2d5d31202eae9441403b1efcc12dd93ad40712ecaeb`
- Canonico sugerido: `HOME\Segundo Cérebro\Chaveiro Popular.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Chaveiro Popular.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 902: hash `3505edb5a3966535c8a09135a0bcab494d38fb9f52c7c8f7c8c49d22410f5fc6`
- Canonico sugerido: `HOME\Segundo Cérebro\Sistema de Produtividade do Paiva.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Sistema de Produtividade do Paiva.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 903: hash `e31e829895ffbfabfba016cf5e843911b23fc447eaf55b9cd05672061b1a391c`
- Canonico sugerido: `HOME\Segundo Cérebro\Vignete.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Vignete.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 904: hash `eacd6e94a4beb9917f02069cfef3f4e06f7cd98a36b5b416e398aa367c3b02e7`
- Canonico sugerido: `HOME\Segundo Cérebro\IamKekeu.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\IamKekeu.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 905: hash `6357bc3b97f80ccafa4094f998a74a2f95ab9052ad6b0f26821ba22ef7cfc2d7`
- Canonico sugerido: `HOME\Segundo Cérebro\Bom Sabor.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Bom Sabor.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 906: hash `9a7571fe4153fd3860e8a0e48e8db755b5ee1daa59faf8b27eab9a57ed627273`
- Canonico sugerido: `HOME\Segundo Cérebro\Volte rapidamente a câmera para o ponto de origem.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Volte rapidamente a câmera para o ponto de origem.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 907: hash `4e6d66c047bb00097dc036b494e243c324fd40037eb9e15dbb7e52c3ea456557`
- Canonico sugerido: `HOME\Segundo Cérebro\Inspiração para insta de concessionária.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Inspiração para insta de concessionária.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 908: hash `c269675b3d7564b605446cfa1c33dd44b9139c3e3c0deec7f045fba21eb97675`
- Canonico sugerido: `HOME\Segundo Cérebro\Loja de roupa no Popular.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Loja de roupa no Popular.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 909: hash `1fb32e6f7bfe61bad37d547065e935d5b36d5d14f2f2a4ec053d9f7fe61ac9aa`
- Canonico sugerido: `HOME\Segundo Cérebro\Nicolas Walter Orgânico.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Nicolas Walter Orgânico.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 910: hash `91b0d0d9efe5fc7cee3e4b52f791b7285181177d40ed62c54a145e64e5be881e`
- Canonico sugerido: `HOME\Muad’Dib\00_Dataview e Tasks\task.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\O Professor\00_Dataview e Tasks\task.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 911: hash `4a27f65e2ec5c4bdbb3125018d0e6dfc2d93849411c676b6f01fbbf6322c1f21`
- Canonico sugerido: `HOME\Segundo Cérebro\Mistborn.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Mistborn.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 912: hash `3a8116a2328786c2fe5daea7450b9b2d952d94353b71d676d31f9993c400048d`
- Canonico sugerido: `HOME\Segundo Cérebro\SENHA VPS HOSTINGER.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\SENHA VPS HOSTINGER.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 913: hash `34784dc4f1011f9aeab3f6fce9412f1f681ef7b5b09f35959264ab8ab809aec6`
- Canonico sugerido: `HOME\Segundo Cérebro\Thays Podóloga.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Thays Podóloga.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 914: hash `2c2e6277a52307625b6c690e41ce49dbc1e1648f9a5c1feb03db449bf2360f2b`
- Canonico sugerido: `HOME\Segundo Cérebro\Flip.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Flip.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 915: hash `e998b8a1aa8a2a5d8d8711eb888842f141561ac99bfde07578d797051a79fc10`
- Canonico sugerido: `HOME\Segundo Cérebro\IP da minha VPS EasyPanel.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\IP da minha VPS EasyPanel.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 916: hash `d122cbb5086296a3bffd9ca28b2f6c418d2152fdcf4f55e9139a2924854ff4fe`
- Canonico sugerido: `HOME\Segundo Cérebro\Fabrício e Yasmin - Techcell.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Fabrício e Yasmin - Techcell.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 917: hash `ce23bf811608e6cec7d181a028cb986cc8e008801360b19af6d98824a3f93e21`
- Canonico sugerido: `HOME\Segundo Cérebro\Voz da Hoor.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Voz da Hoor.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 918: hash `231e09a1c5fa0b0cf24688f8440120c9cff8e16db9439a78889deb5f3c018e75`
- Canonico sugerido: `HOME\Segundo Cérebro\Inteligências Artificiais.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Inteligências Artificiais.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 919: hash `701758b7ebaf494b2746ff31965018bbd510d983b6ed83d1ee9fdee326c936ca`
- Canonico sugerido: `HOME\Segundo Cérebro\Voz do Hoor.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Voz do Hoor.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 920: hash `fa9304349b9d8b93e5010a67a2f78bf1f174c2678d266316d82fb6a59926771c`
- Canonico sugerido: `HOME\Segundo Cérebro\Senha padrão para as contingências.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Senha padrão para as contingências.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 921: hash `2392b437faecb8303d8e4c6642cd819f869f79f21383ef23523474716d897190`
- Canonico sugerido: `HOME\Segundo Cérebro\Aniversário Thiago.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Aniversário Thiago.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
### Grupo 922: hash `c009dd0512362578d0b1b1df5cbbc66f43c8b365a58cdde77e4c9c9033212662`
- Canonico sugerido: `HOME\Segundo Cérebro\Relógios na Praia.md`
- Motivo: Fora de area espelho/import, reduzindo chance de manter copia derivada. Fora de sub-vault aninhado, evitando priorizar fronteira mais sensivel. Arquivo Markdown, priorizado por navegabilidade no Obsidian. Caminho relativamente curto e estavel pela heuristica de desempate.
- Seguros para revisao manual: `HOME\Segundo Cérebro\SC\Relógios na Praia.md` (Hash SHA-256 identico ao arquivo canonico sugerido. Mesmo tamanho em bytes do grupo. Nao foi escolhido como canonico, entao e candidato natural a revisao manual.)
