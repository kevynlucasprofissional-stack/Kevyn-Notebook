# Link Repair Results 07

- Gerado em: 2026-04-04T16:24:04.892457-03:00
- Objetivo: Registrar o reparo seguro executado nesta rodada e o que permaneceu apenas como manifesto revisável.

## Método

- Aplicação de aliases em frontmatter para casos de correspondência única e baixo risco.
- Nenhum rename, move, merge ou criação automática de backlink semântico.
- Reauditoria interna considerando aliases para medir o efeito real no comportamento de navegação do Obsidian.

## Critérios

- Só contam como reparo as mudanças persistidas em arquivo.
- Sub-vaults aninhados permanecem fora do escopo automático.
- Casos sem correspondência inequívoca continuam apenas no manifesto.

## Arquivos afetados

- `reports/07-link-repair-results.md`
- `logs/07-link-repair.md`
- `_staging/07-link-repair-manifest.json`

## Riscos

- A redução cobre apenas casos resolvíveis por alias; placeholders, notas ausentes, assets faltantes e casos semânticos permanecem.
- Backlinks estratégicos seguem como sugestão editorial, não como mudança aplicada.

## Próximos passos

- Revisar o manifesto em `_staging/07-link-repair-manifest.json`.
- Se desejar, separar uma segunda rodada só para backlinks estratégicos e MOCs curtos.
- Reavaliar renames/moves apenas quando houver Obsidian CLI utilizável ou aprovação explícita.

## Resumo

- Links quebrados antes: 697
- Links quebrados depois: 558
- Redução absoluta: 139
- Alvos não resolvidos distintos antes: 422
- Alvos não resolvidos distintos depois: 373
- Redução de alvos distintos: 49
- Arquivos alterados com aliases: 49

## Correções Aplicadas

- 26 aliases adicionados em `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio\`.
- 2 aliases adicionados em `HOME\O Professor\02_EGO - O MAGUS\A guerra da arte\`.
- 17 aliases adicionados em `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\`.
- 3 aliases adicionados em `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\`.
- 1 alias adicionado em `HOME\Cérebro Profissional\Notas\(Ebook) O segredo da mentalidade magra.md`.
- Casos de maior impacto reparados nesta rodada: `A Regra 85/15 do Sucesso Profissional`, `Invulnerabilidade do Sábio`, `Inexistência de Dano ao Sábio`, `Autossuficiência Absoluta`, `Fraqueza do Mal`, `Velhice Infantil`, `Analogia do Médico e o Louco`, `Natureza dos Bens do Sábio`.

## Manifesto Remanescente

- `A Crítica como Gatilho para a Defensiva`: 13 ocorrência(s) ainda dependem de revisão humana, criação de nota, asset ou rename/move.
- `PRINCÍPIO 7: Deixe que a outra pessoa sinta que a ideia é dela`: 6 ocorrência(s) ainda dependem de revisão humana, criação de nota, asset ou rename/move.
- `O Incidente 'Chá e Prosa' (Análise da Sombra Luciferiana)`: 6 ocorrência(s) ainda dependem de revisão humana, criação de nota, asset ou rename/move.
- `Perfil Comportamental Alto S/C (Castro)`: 5 ocorrência(s) ainda dependem de revisão humana, criação de nota, asset ou rename/move.
- `O Ego e o Self`: 5 ocorrência(s) ainda dependem de revisão humana, criação de nota, asset ou rename/move.
- `03 - quinta-feira.md`: 4 ocorrência(s) ainda dependem de revisão humana, criação de nota, asset ou rename/move.
- `Compounding (Juros Compostos)`: 4 ocorrência(s) ainda dependem de revisão humana, criação de nota, asset ou rename/move.
- `Kevyn Lucas: Arquétipo Mago`: 4 ocorrência(s) ainda dependem de revisão humana, criação de nota, asset ou rename/move.
- `Menor Mercado Viável`: 4 ocorrência(s) ainda dependem de revisão humana, criação de nota, asset ou rename/move.
- `O Desastre do Svelte (200 vs. 22)`: 4 ocorrência(s) ainda dependem de revisão humana, criação de nota, asset ou rename/move.
- `Aragorn`: 3 ocorrência(s) ainda dependem de revisão humana, criação de nota, asset ou rename/move.
- `Numenor`: 3 ocorrência(s) ainda dependem de revisão humana, criação de nota, asset ou rename/move.
