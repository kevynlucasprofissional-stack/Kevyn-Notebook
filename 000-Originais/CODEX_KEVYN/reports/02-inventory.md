# Inventory 02

- Gerado em: 2026-04-04T10:59:50.335905-03:00
- Objetivo: Gerar inventário do vault com foco em navegabilidade, orfandade e zonas de risco.

## Método

- Varredura recursiva excluindo áreas operacionais do próprio fluxo de auditoria.
- Identificação de arquivos Markdown, sub-vaults e links internos por wikilink e Markdown link.
- Classificação heurística de nomes genéricos, áreas espelho/import e diretórios trash.

## Critérios

- Nenhum arquivo foi movido, renomeado ou apagado.
- Notas sem backlinks e sem links de saída são tratadas como triagem, não como verdade semântica.
- Sub-vaults são detectados por presença de `.obsidian`.

## Arquivos afetados

- `reports/02-inventory.json`
- `reports/02-inventory.md`
- `logs/02-inventory.md`

## Riscos

- Backlinks e links quebrados dependem de resolução heurística e podem conter falsos positivos.
- Áreas espelho/import são inferidas por nome de caminho.

## Próximos passos

- Executar `exact_dedupe.py` para separar duplicatas exatas de candidatos semânticos.
- Executar `link_audit.py` para priorizar orfandade e hubs.

## Resumo

- Arquivos auditados: 4132
- Notas Markdown: 3576
- Sub-vaults detectados: 7
- Notas sem link de saída: 2303
- Notas sem backlinks: 1503
- Links não resolvidos: 865

## Top Pastas

- `HOME\Segundo Cérebro`: 716 arquivos, 715 markdown
- `HOME\Segundo Cérebro\SC`: 715 arquivos, 715 markdown
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas`: 298 arquivos, 298 markdown
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico`: 182 arquivos, 182 markdown
- `HOME\Cérebro Profissional\Notas`: 155 arquivos, 153 markdown
- `ACIRV\Notas`: 127 arquivos, 127 markdown
- `HOME\ACIRV\Notas`: 106 arquivos, 106 markdown
- `HOME\O Professor\02_EGO - O MAGUS\A guerra da arte`: 86 arquivos, 85 markdown
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações`: 85 arquivos, 85 markdown
- `.venv\Lib\site-packages\pip\_vendor\rich`: 79 arquivos, 0 markdown
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta`: 65 arquivos, 65 markdown
- `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio`: 59 arquivos, 58 markdown
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\O Pequeno Príncipe`: 53 arquivos, 53 markdown
- `HOME\Kevyn Lucas\Outros\Integrados`: 49 arquivos, 49 markdown
- `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash`: 41 arquivos, 41 markdown
- `HOME\Clones\ECO - Contexto Completo`: 39 arquivos, 37 markdown
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash`: 35 arquivos, 34 markdown
- `HOME\Kevyn Lucas\Outros\Não integrados`: 35 arquivos, 35 markdown
- `HOME\Muad’Dib\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PARTE I - Técnicas fundamentais para lidar com as pessoas\temp`: 35 arquivos, 35 markdown
- `HOME\BioVision\Notas`: 26 arquivos, 25 markdown

## Top Extensões

- `.md`: 3576
- `.py`: 404
- `.pdf`: 36
- `[no extension]`: 35
- `.png`: 21
- `.typed`: 14
- `.txt`: 13
- `.exe`: 11
- `.canvas`: 5
- `.apache`: 2
- `.bsd`: 2
- `.bat`: 2
- `.json`: 2
- `.pem`: 1
- `.rst`: 1

## Notas Sem Backlinks

- `.venv\Lib\site-packages\pip-25.3.dist-info\licenses\src\pip\_vendor\idna\LICENSE.md`
- `.venv\Lib\site-packages\pip\_vendor\idna\LICENSE.md`
- `ACIRV\Diário\2025\11 - novembro\11 - terça-feira.md`
- `ACIRV\Diário\2025\11 - novembro\13 - quinta-feira.md`
- `ACIRV\Diário\2025\11 - novembro\14 - sexta-feira.md`
- `ACIRV\Diário\2025\11 - novembro\17 - segunda-feira.md`
- `ACIRV\Diário\2025\11 - novembro\18 - terça-feira.md`
- `ACIRV\Diário\2025\11 - novembro\19 - quarta-feira.md`
- `ACIRV\Diário\2025\11 - novembro\21 - sexta-feira.md`
- `ACIRV\Diário\2025\11 - novembro\24 - segunda-feira.md`
- `ACIRV\Diário\2025\11 - novembro\25 - terça-feira.md`
- `ACIRV\Diário\2025\11 - novembro\27 - quinta-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\01 - segunda-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\02 - terça-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\03 - quarta-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\04 - quinta-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\05 - sexta-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\08 - segunda-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\09 - terça-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\10 - quarta-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\12 - sexta-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\29 - segunda-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\07 - quarta-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\08 - quinta-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\13 - terça-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\15 - quinta-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\16 - sexta-feira.md`
- `ACIRV\Diário\2026\02 - fevereiro\03 - terça-feira.md`
- `ACIRV\Diário\2026\02 - fevereiro\18 - quarta-feira.md`

## Arquivos com Nome Ruim

- `ACIRV\Notas\00_rascunho.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\novo.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 12.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 15.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 16.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 17.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 2.canvas`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 25.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 31.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 34.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 37.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 39.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 40.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 41.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 42.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 43.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 46.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 47.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 48.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 50.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Untitled 1.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Untitled.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\Sem título.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Sem título.md`
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\novo.md`
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 12.md`
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 15.md`
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 16.md`
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 17.md`

## Sub-vaults Detectados

- `.`
- `HOME\Kevyn Lucas`
- `HOME\Ágora\Ágora Obsidian`
- `HOME\Neuron\Neuron Obsidian`
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico`
- `HOME\SaaS com Kelvyn\TPM\TPM Obsidian`
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian`

## Áreas Espelho/Import

- `HOME`: 288 arquivos
- `HOME\Clones`: 232 arquivos
- `Google Drive (Not synced)`: 201 arquivos
- `Google Drive (Not synced)\Meu Drive`: 201 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME`: 197 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro`: 67 arquivos
- `HOME\Clones\_ECO`: 55 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash`: 41 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional`: 40 arquivos
- `HOME\Clones\Alex Hormozi`: 39 arquivos
- `HOME\Clones\ECO - Contexto Completo`: 39 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash`: 36 arquivos
- `HOME\Clones\Alex Hormozi\Livros`: 28 arquivos
- `HOME\Clones\_ECO\ECO V3`: 26 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole`: 22 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash`: 22 arquivos
- `HOME\Clones\Jung`: 21 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas`: 19 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos`: 19 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS`: 19 arquivos
- `HOME\O Professor`: 19 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE`: 18 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre`: 18 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash`: 18 arquivos
- `HOME\Segundo Cérebro`: 18 arquivos
- `HOME\O Professor\04_PERSONA 02 - O SOL`: 15 arquivos
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas`: 15 arquivos
- `HOME\Clones\_ECO\ECO V3\input_data`: 14 arquivos
- `HOME\Clones\_ECO\ECO V3\input_data\kotler`: 14 arquivos
- `HOME\Clones\Outros`: 14 arquivos
