# Exact Dedupe 03

- Gerado em: 2026-04-04T10:59:50.338907-03:00
- Objetivo: Identificar duplicatas exatas por hash sem apagar nem mover arquivos.

## Método

- Hash SHA-256 calculado para cada arquivo fora das áreas operacionais.
- Agrupamento por hash idêntico.
- Sugestão de arquivo canônico por heurística conservadora.

## Critérios

- Apenas duplicatas exatas entram no agrupamento.
- Nenhum arquivo é alterado.
- A sugestão de canônico é revisável e não executa deduplicação.

## Arquivos afetados

- `reports/03-exact-dedupe.json`
- `reports/03-exact-dedupe.md`
- `logs/03-exact-dedupe.md`

## Riscos

- Arquivos binários distintos com mesmo propósito continuam separados se o hash divergir.
- A escolha de canônico usa heurística estrutural, não semântica.

## Próximos passos

- Revisar grupos maiores e decidir se algum conjunto deve ir para manifesto de quarentena.
- Executar `near_dedupe.py` apenas nas áreas em que o ruído semântico ainda for alto.

## Resumo

- Arquivos auditados: 4132
- Grupos de duplicata exata: 944
- Arquivos duplicados envolvidos: 2169

## Maiores Grupos

- `ACIRV\Notas\Regulamento da postagem e captura de material de eventos da ACIRV.md`: 249 arquivos, hash `e3b0c44298fc`
- `ACIRV\Diário\Diário.md`: 7 arquivos, hash `57cebb7f4a9c`
- `HOME\Clones\ECO - Contexto Completo\07_metodologias.md`: 4 arquivos, hash `5547479dcb1d`
- `HOME\Clones\ECO - Contexto Completo\09_contradicoes.md`: 4 arquivos, hash `dd9b8848b7d2`
- `HOME\Clones\ECO - Contexto Completo\06_metaprogramas.md`: 4 arquivos, hash `2a3e590264fe`
- `HOME\Clones\ECO - Contexto Completo\05_heuristicas.md`: 4 arquivos, hash `8206c0af2658`
- `HOME\Clones\ECO - Contexto Completo\08_moduladores.md`: 4 arquivos, hash `3af6f81b4604`
- `HOME\Clones\ECO - Contexto Completo\04_valores.md`: 4 arquivos, hash `0edbab451f2c`
- `HOME\Clones\ECO - Contexto Completo\03_eneagrama.md`: 4 arquivos, hash `28154a644145`
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 15.md`: 4 arquivos, hash `8eed28a405e3`
- `.venv\Lib\site-packages\pip\_vendor\tomli\LICENSE`: 4 arquivos, hash `b80816b0d530`
- `HOME\Segundo Cérebro\Glow.md`: 4 arquivos, hash `115464c1a271`
- `.venv\Scripts\pip.exe`: 3 arquivos, hash `a957f5b6c503`
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
