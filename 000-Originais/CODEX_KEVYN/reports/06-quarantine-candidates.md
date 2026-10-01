# Quarantine Candidates 06

- Gerado em: 2026-04-04T10:59:50.339905-03:00
- Objetivo: Listar arquivos e pastas candidatos a quarentena revisável em `_archive_review/` sem mover nada.

## Método

- Aplicação de heurísticas de espelho/import, clones, `.trash`, nomes genéricos e sub-vaults aninhados.
- Agrupamento por área de topo para facilitar revisão humana.
- Nenhuma ação de filesystem é executada.

## Critérios

- A saída é apenas manifesto de revisão.
- Sub-vaults são tratados como fronteiras de risco.
- Pastas e arquivos são sinalizados por razões explícitas.

## Arquivos afetados

- `reports/06-quarantine-candidates.json`
- `reports/06-quarantine-candidates.md`
- `logs/06-quarantine-candidates.md`

## Riscos

- Áreas de espelho podem conter conteúdo ainda útil e precisam de validação humana.
- Nomes genéricos podem aparecer em notas intencionais.

## Próximos passos

- Converter subconjuntos aprovados em manifesto dentro de `_staging/` antes de qualquer move.
- Cruzar com `exact_dedupe.py` para priorizar espelhos com duplicatas exatas.

## Resumo

- Arquivos candidatos: 868
- Pastas candidatas: 6
- Áreas sinalizadas: 4

## Áreas Mais Afetadas

- `HOME`: 658 candidato(s)
- `Google Drive (Not synced)`: 201 candidato(s)
- `.venv`: 6 candidato(s)
- `ACIRV`: 3 candidato(s)

## Pastas Candidatas

- `HOME\Kevyn Lucas`: Sub-vault detectado por `.obsidian`; não cruzar essa fronteira sem aprovação explícita.
- `HOME\Neuron\Neuron Obsidian`: Sub-vault detectado por `.obsidian`; não cruzar essa fronteira sem aprovação explícita.
- `HOME\Ágora\Ágora Obsidian`: Sub-vault detectado por `.obsidian`; não cruzar essa fronteira sem aprovação explícita.
- `HOME\SaaS com Kelvyn\TPM\TPM Obsidian`: Sub-vault detectado por `.obsidian`; não cruzar essa fronteira sem aprovação explícita.
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico`: Sub-vault detectado por `.obsidian`; não cruzar essa fronteira sem aprovação explícita.
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian`: Sub-vault detectado por `.obsidian`; não cruzar essa fronteira sem aprovação explícita.

## Arquivos Candidatos

- `.venv\Lib\site-packages\pip-25.3.dist-info\licenses\src\pip\_vendor\msgpack\COPYING`: Caminho com marcador de espelho/import/backup.
- `.venv\Lib\site-packages\pip\_internal\metadata\importlib\__init__.py`: Caminho com marcador de espelho/import/backup.
- `.venv\Lib\site-packages\pip\_internal\metadata\importlib\_compat.py`: Caminho com marcador de espelho/import/backup.
- `.venv\Lib\site-packages\pip\_internal\metadata\importlib\_dists.py`: Caminho com marcador de espelho/import/backup.
- `.venv\Lib\site-packages\pip\_internal\metadata\importlib\_envs.py`: Caminho com marcador de espelho/import/backup.
- `.venv\Lib\site-packages\pip\_vendor\msgpack\COPYING`: Caminho com marcador de espelho/import/backup.
- `ACIRV\Notas\00_rascunho.md`: Nome genérico ou sem título.
- `ACIRV\Notas\ESPELHO OFICIAL - CONECTA 5º EDIÇÃO.md`: Caminho com marcador de espelho/import/backup.
- `ACIRV\Notas\Lovable\Como copiar qualquer site.md`: Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md`: Área espelho/import do Google Drive não sincronizado.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\ACIRV\Notas\Blocos de foco\180326 - Bloco de foco tipo operacional.md`: Área espelho/import do Google Drive não sincronizado.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\ACIRV\Notas\Gestão de tempo.md`: Área espelho/import do Google Drive não sincronizado.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\ACIRV\Notas\Sugestão de segmentação - OFICINA Seja um bom líder.md`: Área espelho/import do Google Drive não sincronizado.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\HOME\ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md`: Área espelho/import do Google Drive não sincronizado.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\HOME\Clones\_ECO\ECO V2.5\main.py`: Área espelho/import do Google Drive não sincronizado.; Área de clones com alta chance de redundância.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\HOME\Clones\_ECO\ECO V2.5\prompt_parts\10_trajetoria.md`: Área espelho/import do Google Drive não sincronizado.; Área de clones com alta chance de redundância.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\HOME\Clones\_ECO\ECO V3\main.py`: Área espelho/import do Google Drive não sincronizado.; Área de clones com alta chance de redundância.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\HOME\Como estudar finanças.md`: Área espelho/import do Google Drive não sincronizado.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\04 Livros\Livro 100M Leads\Seção V Comece.md`: Área espelho/import do Google Drive não sincronizado.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\image1.md`: Área espelho/import do Google Drive não sincronizado.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\Misc\Goodwill compounds faster than revenue.md`: Área espelho/import do Google Drive não sincronizado.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\Misc\leading indicator.md`: Área espelho/import do Google Drive não sincronizado.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Hormoziano\Obsidian Hormoziano\Misc\one channel.md`: Área espelho/import do Google Drive não sincronizado.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\03 - terça-feira 2.md`: Área espelho/import do Google Drive não sincronizado.; Conteúdo localizado em `.trash`.; Caminho com marcador de espelho/import/backup.
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\04 - quarta-feira.md`: Área espelho/import do Google Drive não sincronizado.; Conteúdo localizado em `.trash`.; Caminho com marcador de espelho/import/backup.
