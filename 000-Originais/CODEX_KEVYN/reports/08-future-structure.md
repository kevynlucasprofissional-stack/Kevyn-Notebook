# Future Structure 08

- Gerado em: 2026-04-04T16:40:00-03:00
- Objetivo: definir uma estrutura futura leve para reduzir crescimento caotico do vault, preservando o legado e concentrando padroes em conteudo novo e revisoes pontuais.

## Metodo

- Leitura de `AGENTS.md`, da skill `obsidian-vault-ops`, do rascunho anterior `reports/06-future-structure.md` e do material de `templates/suggested/`.
- Validacao das fronteiras de sub-vault por pastas contendo `.obsidian/`.
- Consolidacao de um conjunto minimo de convencoes, frontmatter, templates e fluxo de staging sem retrofit global.
- Criacao de documentacao curta diretamente nas pastas operacionais para reduzir friccao de adocao futura.

## Criterios

- Aplicar os padroes principalmente ao futuro e a revisoes pontuais.
- Nao renomear, mover ou reescrever o legado em lote.
- Nao cruzar fronteiras de sub-vault em refactors automaticos.
- Manter a camada futura pequena, reversivel e compativel com areas ja existentes.
- Favorecer navegabilidade e decisao operacional, nao taxonomia total.

## Arquivos afetados

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

## Riscos

- Se as convencoes forem tratadas como obrigatorias para o legado, elas podem competir com estruturas locais ja funcionais.
- Alguns sub-vaults vao precisar de variacao local e nao devem receber enforcement central.
- Frontmatter minimo ajuda a operacao futura, mas nao deve virar pretexto para edicao em massa de milhares de notas.

## Proximos passos

1. Adotar os templates apenas em notas novas e em notas ja abertas por revisao real.
2. Comecar com `_staging/inbox/` como porta de entrada padrao para capturas novas.
3. Criar MOCs e homes de area apenas onde houver demanda concreta de navegacao.
4. Revisar depois de algumas semanas se os tipos e status propostos estao suficientes ou excessivos.

## Estrutura Futura Leve

Camada sugerida para o vault principal:

```text
_staging/
  inbox/
  review/
  manifests/

_archive_review/

templates/
  suggested/
```

Principio central:

- o legado permanece onde esta
- novas entradas entram por staging quando ainda nao houver destino claro
- areas vivas ganham uma home opcional
- hubs conectam o que importa sem tentar reescrever toda a taxonomia

## Convencoes de Nome

Convencoes para uso futuro:

- `AREA - Nome da Area` para paginas-home de areas vivas
- `MOC - Tema` para hubs puramente navegacionais
- `YYYY-MM-DD HHmm - Titulo curto` para capturas em inbox
- `Titulo natural` para notas gerais

Regras:

- evitar `Untitled`, `Sem titulo`, `Nova nota` e variantes genericas
- evitar prefixos numericos fora de casos em que a ordem faca parte do uso real
- evitar colocar versoes no titulo quando isso puder ir para changelog ou conteudo
- manter nomes humanos e buscaveis

## Frontmatter Minimo

Padrao sugerido para conteudo novo:

```yaml
---
title: "{{title}}"
type: note
status: active
created: {{date:YYYY-MM-DD}}
updated: {{date:YYYY-MM-DD}}
---
```

Campos opcionais apenas quando houver ganho claro:

- `area`
- `aliases`
- `tags`
- `source`
- `review_status`

Tipos recomendados:

- `note`
- `moc`
- `area`
- `inbox`
- `archive`
- `review`

Status recomendados:

- `active`
- `staged`
- `reference`
- `archived`
- `holding`

## Templates Sugeridos

Os templates foram mantidos curtos para nao aumentar manutencao:

- `00-inbox-capture.md`: captura nova ainda sem destino estavel
- `01-note-default.md`: nota geral com contexto, links e proximo movimento
- `02-hub-moc.md`: hub de navegacao com funcao explicita
- `03-area-home.md`: home enxuta para area viva
- `04-archive-record.md`: registro de saida do fluxo ativo
- `05-review-note.md`: item temporario de decisao ou revisao pontual

## Zona de Inbox e Staging

`_staging/` passa a ter tres usos claros:

- `inbox/`: entradas novas, capturas, rascunhos e itens sem lugar definido
- `review/`: notas que pedem decisao humana, dedupe leve, alias ou limpeza pontual
- `manifests/`: listas de trabalho, relatarios intermediarios e checkpoints operacionais

Fluxo minimo sugerido:

1. Capturar em `inbox/`.
2. Decidir se a nota vai para area viva, MOC, referencia ou `_archive_review/`.
3. Se nao houver contexto suficiente, manter em `review/` ou `inbox/`.
4. Promover manualmente apenas o que ja tiver funcao clara.

## Regras para Novas Notas

- Se a nota ainda nao tem destino, criar em `_staging/inbox/`.
- Se a nota so organiza navegacao, criar um `MOC - ...`.
- Se uma area estiver ficando recorrente, criar uma home `AREA - ...` em vez de abrir mais subpastas por impulso.
- So adicionar frontmatter minimo em notas novas ou ja revisadas manualmente.
- Nao transformar esta convencao em retrofit semantico global.
- Em sub-vaults com `.obsidian/`, tratar estas regras como referencia opcional, nao imposicao central.

## Compatibilidade com o Legado

Esta proposta foi desenhada para conviver com o que ja existe:

- sem mover milhares de arquivos
- sem renomear colecoes inteiras
- sem consolidar automaticamente material pessoal denso
- sem cruzar as fronteiras detectadas de sub-vault

O ganho esperado nao vem de reorganizacao massiva. Vem de impedir que o conteudo novo continue entrando sem forma.
