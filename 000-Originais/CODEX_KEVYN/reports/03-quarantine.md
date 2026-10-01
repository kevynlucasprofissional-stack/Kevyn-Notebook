# Quarantine 03

- Gerado em: 2026-04-04T16:20:50.393465-03:00
- Objetivo: Quarentenar apenas material claramente de baixo risco em _archive_review/, preservando manifesto completo e respeitando fronteiras de sub-vault.

## Método

- Leitura do inventario atual do vault com deteccao de sub-vaults aninhados.
- Cruzamento com reports/03-exact-duplicates.json para exigir prova de duplicata exata quando o criterio depende de copia canonica.
- Selecao conservadora de apenas .trash, nomes genericos muito fracos em areas mirror/noise e duplicatas exatas em areas mirror/noise com canonico fora dessas areas.

## Critérios

- Nenhum item dentro de sub-vault aninhado foi movido.
- Nada sob HOME/Kevyn Lucas foi tocado.
- Arquivos genericos fora de areas mirror/noise so entram quando ja estavam em .trash.
- Material espelhado do Google Drive so entra quando houve correspondencia canonica exata fora do espelho.

## Arquivos afetados

- `reports\03-quarantine.md`
- `reports\03-quarantine.json`
- `logs\03-quarantine.md`

## Riscos

- Ainda pode haver copias espelhadas sem hash identico nesta rodada; elas ficaram apenas sinalizadas.
- Arquivos vazios e genericos fora de areas mirror/noise foram mantidos se houvesse qualquer ambiguidade operacional.
- Mudancas foram feitas por filesystem porque nao ha Obsidian CLI disponivel neste ambiente.

## Próximos passos

- Revisar o manifesto em reports/03-quarantine.md e confirmar se a trilha de arquivo em _archive_review/03-quarantine faz sentido para restauracao futura.
- Se quiser ampliar o recorte, a proxima rodada pode analisar espelhos do Google Drive com validacao textual adicional para casos nao identicos.
- Depois da revisao humana, criar um checkpoint Git dedicado para esta quarentena.

## Resumo

- Modo: `dry-run`
- Itens movidos: 0
- Itens movidos do Google Drive: 0
- Itens movidos com canonico correspondente: 0
- Itens apenas sinalizados: 19

## Itens Movidos

- Nenhum item elegivel nesta rodada.

## Itens Sinalizados

- `ACIRV\Notas\00_rascunho.md` | `generic-but-nonempty` | Nome generico, mas arquivo nao vazio.
- `Google Drive (Not synced)\Meu Drive\ACIRV\Notas\Blocos de foco\180326 - Bloco de foco tipo operacional.md` | `mirror-without-exact-proof` | Existe caminho canonico potencial fora do espelho (ACIRV\Notas\Blocos de foco\180326 - Bloco de foco tipo operacional.md), mas sem prova estrutural suficiente nesta rodada.
- `Google Drive (Not synced)\Meu Drive\ACIRV\Notas\Gestão de tempo.md` | `mirror-without-exact-proof` | Existe caminho canonico potencial fora do espelho (ACIRV\Notas\Gestão de tempo.md), mas sem prova estrutural suficiente nesta rodada.
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\00_Insights.md` | `nested-subvault` | Dentro de sub-vault aninhado.
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\00_rascunho.md` | `nested-subvault` | Dentro de sub-vault aninhado.
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\210326 - Sessão de desenvolvimento.md` | `nested-subvault` | Dentro de sub-vault aninhado.
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\2103262143 - Feedback Agent UX e UI.md` | `nested-subvault` | Dentro de sub-vault aninhado.
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\2103262209 - Prompt ajuste de UX UI.md` | `nested-subvault` | Dentro de sub-vault aninhado.
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\Agent UX e UI\Agent UX UI - Prompt 01.md` | `nested-subvault` | Dentro de sub-vault aninhado.
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\Agent UX e UI\Agent UX UI - Prompt 02.md` | `nested-subvault` | Dentro de sub-vault aninhado.
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\Agent UX e UI\Agent UX UI.md` | `nested-subvault` | Dentro de sub-vault aninhado.
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\TAREFAS 210326.md` | `nested-subvault` | Dentro de sub-vault aninhado.
- `HOME\ACIRV\Notas\00_rascunho.md` | `generic-but-nonempty` | Nome generico, mas arquivo nao vazio.
- `HOME\BioVision\Notas\00_rascunho.md` | `generic-but-nonempty` | Nome generico, mas arquivo nao vazio.
- `HOME\Gestão de Tempo\Untitled.sheet` | `generic-but-nonempty` | Nome generico, mas arquivo nao vazio.
- `HOME\Kevyn Lucas\Outros\Não integrados\00_rascunho.md` | `protected-area` | Dentro de HOME/Kevyn Lucas.
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico\Agente Prescritivo (Clone).md` | `nested-subvault` | Dentro de sub-vault aninhado.
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico\Princípio da Sincronização (Copywriting).md` | `nested-subvault` | Dentro de sub-vault aninhado.
- `HOME\Ágora\Ágora Obsidian\00_rascunho.md` | `nested-subvault` | Dentro de sub-vault aninhado.
