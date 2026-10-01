# Metadata Normalization 12

- Gerado em: 2026-04-04T17:27:30.986287-03:00
- Objetivo: Executar normalizacao mecanica de frontmatter para tags, aliases e singleton tags em areas de baixo valor, sem inferencia semantica forte.

## Método

- Varredura conservadora apenas em arquivos Markdown fora de sub-vaults aninhados.
- Conversao de `tag` para `tags` e `alias` para `aliases`, com listas YAML quando aplicavel.
- Normalizacao mecanica de tags por caixa, acentos, espacos/hifens e separadores hierarquicos, mantendo aliases textuais.
- Remocao de singleton tags apenas em areas de espelho, ruido, quarentena e import/backup de baixo valor.

## Critérios

- Nao houve alteracao no corpo das notas.
- Nao foram criados links novos.
- Nao houve movimentacao de arquivos.
- Singleton tags conceituais em areas autorais densas nao foram removidas por regra.

## Arquivos afetados

- `reports\12-metadata-normalization.json`
- `reports\12-metadata-normalization.md`
- `logs\12-metadata-normalization.md`
- `_staging\manifests\12-metadata-normalization.json`
- `HOME\Cérebro Profissional\Notas\Governança de Metadados.base`

## Riscos

- Tags com diferenca apenas acentual ou de pluralidade podem colidir depois da normalizacao mecanica.
- Bases do Obsidian usam sintaxe versionada; a base criada segue a convencao atual mais simples e pode precisar de ajuste visual no app.
- Frontmatter muito incomum foi mantido e nao reescrito agressivamente.

## Próximos passos

- Abrir a base de governanca para revisar as filas de tags, aliases e propriedades fora do padrao.
- Se houver interesse, uma rodada futura pode tratar singular/plural conceitual com revisao humana.
- Revisar os clusters sinalizados em `_staging/manifests/12-metadata-normalization.json` antes de ampliar o recorte.

## Resumo

- Notas consideradas: 706
- Arquivos alterados: 10
- Arquivos em areas de baixo valor alterados: 10
- Singleton tags removidas: 14
- Valores de tags antes: 53
- Valores de tags depois: 39
- Valores de aliases antes: 0
- Valores de aliases depois: 0
- Areas tocadas: 1
- Tags distintas vistas: 889
- Aliases distintos vistos: 71

## Arquivos Alterados

- `HOME\Muad’Dib\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PARTE I - Técnicas fundamentais para lidar com as pessoas\temp\O Desejo de Ser Importante (Dewey).md`
- `HOME\O Professor\02_EGO - O MAGUS\A guerra da arte\Medo como Indicador de Importância.md`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Insanidade como Fuga para um Mundo de Importância.md`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\Bajulação como Espelho do Ego Alheio.md`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\Faça a Outra Pessoa Sentir-se Importante (Princípio).md`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Cartaz 'VOCÊ É IMPORTANTE'.md`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Caráter Determinado pela Forma de Buscar Importância.md`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Desejo de Importância como Estímulo para a Ambição.md`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Desejo de Importância como Motor da Civilização.md`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Desejo de Ser Importante (John Dewey).md`

## Singletons Removidos

- `HOME\Muad’Dib\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PARTE I - Técnicas fundamentais para lidar com as pessoas\temp\O Desejo de Ser Importante (Dewey).md`: motivacao_profunda
- `HOME\O Professor\02_EGO - O MAGUS\A guerra da arte\Medo como Indicador de Importância.md`: bussola, heuristica
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Insanidade como Fuga para um Mundo de Importância.md`: realidade_psiquica, fantasia, dissociacao
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\Bajulação como Espelho do Ego Alheio.md`: espelhamento
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\Faça a Outra Pessoa Sentir-se Importante (Princípio).md`: influencia_etica
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Cartaz 'VOCÊ É IMPORTANTE'.md`: lembrete
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Caráter Determinado pela Forma de Buscar Importância.md`: filosofia_moral
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Desejo de Importância como Estímulo para a Ambição.md`: desejo_de_importancia
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Desejo de Importância como Motor da Civilização.md`: progresso, historia_das_ideias
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Desejo de Ser Importante (John Dewey).md`: necessidade_fundamental
