# Changelog 08 Future Structure

- Data: 2026-04-04
- Escopo: consolidacao de uma camada futura leve para notas novas, staging e revisoes pontuais, sem retrofit global do vault.

## Acoes executadas

- Releitura das diretrizes do repositorio e da skill `obsidian-vault-ops`.
- Reuso do rascunho anterior de estrutura futura e dos templates ja sugeridos.
- Expansao das convencoes para incluir regras operacionais para novas notas.
- Ajuste dos templates para cobrir inbox, nota padrao, MOC, area, arquivo e revisao.
- Estruturacao documental de `_staging/` com subpastas `inbox/`, `review/` e `manifests/`.
- Geracao do relatorio consolidado `reports/08-future-structure.md`.

## Alteracoes de conteudo

- Nenhum rename em lote executado.
- Nenhum move em lote executado.
- Nenhum retrofit semantico global aplicado.
- Nenhuma nota legada foi reescrita fora dos artefatos de suporte.

## Saidas geradas

- `reports/08-future-structure.md`
- `logs/08-future-structure.md`
- `templates/suggested/README.md`
- `templates/suggested/CONVENTIONS.md`
- `templates/suggested/00-inbox-capture.md`
- `templates/suggested/01-note-default.md`
- `templates/suggested/02-hub-moc.md`
- `templates/suggested/03-area-home.md`
- `templates/suggested/04-archive-record.md`
- `templates/suggested/05-review-note.md`
- `_staging/README.md`
- `_staging/inbox/README.md`
- `_staging/review/README.md`
- `_staging/manifests/README.md`

## Riscos observados

- A adocao cega das convencoes em sub-vaults pode gerar duplicidade de padrao.
- O frontmatter minimo pode virar excesso se for aplicado onde nao ha ganho operacional.

## Proximo checkpoint sugerido

- Usar a nova inbox/staging por alguns ciclos reais de captura antes de expandir qualquer padrao adicional.
