# Conventions Suggested

Camada futura leve para notas novas e revisoes pontuais. Nao usar como gatilho para retrofit global.

## Nome

- Areas vivas: `AREA - Nome da Area`
- Hubs navegacionais: `MOC - Tema`
- Capturas de inbox: `YYYY-MM-DD HHmm - Titulo curto`
- Notas gerais: titulo natural, sem prefixo obrigatorio
- Registros de revisao ou arquivo: manter titulo humano; se precisar de contexto, usar frontmatter

## Frontmatter minimo

Usar em conteudo novo ou quando a nota ja estiver sendo revisada manualmente:

```yaml
---
title: "{{title}}"
type: note
status: active
created: {{date:YYYY-MM-DD}}
updated: {{date:YYYY-MM-DD}}
---
```

Campos opcionais apenas quando ajudarem navegacao ou operacao:

- `area`
- `aliases`
- `tags`
- `source`
- `review_status`

## Tipos

- `note`: nota geral
- `moc`: hub de navegacao
- `area`: home de area viva
- `inbox`: captura ou rascunho em triagem
- `archive`: registro fora do fluxo ativo
- `review`: nota temporaria de revisao ou decisao

## Status

- `active`: em uso recorrente
- `staged`: em triagem
- `reference`: material de consulta
- `archived`: fora do fluxo ativo
- `holding`: retido temporariamente por falta de contexto

## Regras para novas notas

- Toda captura nova entra primeiro em `_staging/inbox/` quando ainda nao houver destino claro.
- So promover uma nota para area viva quando houver contexto, links ou tarefa concreta.
- Se uma nota existir apenas para agrupar navegacao, usar `MOC - ...` em vez de misturar com nota conceitual.
- Se uma pasta ou area estiver ativa, preferir criar uma home `AREA - ...` antes de abrir novas subpastas.
- Se uma nota perder funcao ativa, mover para `_archive_review/` apenas por decisao revisavel.

## Guardrails

- Nao renomear o legado em massa.
- Nao criar prefixos para tudo.
- Nao atravessar fronteiras de sub-vault sem aprovacao explicita.
- Usar hubs para conectar, nao para reescrever a taxonomia inteira.
- Manter `_staging/` e `_archive_review/` como estados operacionais claros.
