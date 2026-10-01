# Future Structure 06

- Gerado em: 2026-04-04T12:00:00-03:00
- Objetivo: Propor uma camada leve de estrutura futura para o vault, convivendo com o legado sem reorganizacao em lote.

## Metodo

- Leitura do `AGENTS.md`, da skill `obsidian-vault-ops` e dos relatorios ja existentes.
- Consideracao explicita das fronteiras de sub-vault detectadas por pastas com `.obsidian/`.
- Proposta orientada a overlay: novas convencoes para conteudo novo e para melhoria gradual de navegabilidade.

## Criterios

- Nao mover ou renomear o vault inteiro.
- Nao atravessar fronteiras de sub-vault em batch refactors.
- Reaproveitar areas ja existentes como `_staging/` e `_archive_review/`.
- Manter a estrutura sugerida pequena, legivel e opcional para o legado.

## Arquivos afetados

- `reports/06-future-structure.md`
- `logs/06-future-structure.md`
- `templates/suggested/README.md`
- `templates/suggested/CONVENTIONS.md`
- `templates/suggested/00-inbox-capture.md`
- `templates/suggested/01-note-default.md`
- `templates/suggested/02-hub-moc.md`
- `templates/suggested/03-area-home.md`
- `templates/suggested/04-archive-record.md`

## Riscos

- Se a estrutura sugerida for aplicada sem escopo, pode competir com organizacoes locais ja existentes.
- Prefixos e tipos novos podem coexistir por muito tempo com nomes legados inconsistentes.
- Alguns sub-vaults podem precisar de variacoes locais, nao de um padrao unico centralizado.

## Proximos passos

- Adotar os templates apenas para notas novas ou notas tocadas manualmente.
- Criar primeiro 1 hub raiz e 1 hub por area viva prioritaria, sem migracao em massa.
- Testar o frontmatter minimo em uma area piloto antes de qualquer padronizacao maior.

## Principio da Camada Futura

A proposta nao substitui a estrutura atual. Ela adiciona uma camada leve para operacao futura:

- captura e triagem entram por uma inbox clara
- areas vivas ganham uma pagina-home opcional
- hubs/MOCs passam a ser pontos de navegacao, nao um sistema de refatoracao total
- arquivo continua separado de material ativo
- frontmatter fica minimo e util

## Estrutura Sugerida

Estrutura base sugerida na raiz do vault principal:

```text
_staging/
  inbox/
  review/
  manifests/

_hubs/
  MOC - Inicio.md
  MOC - Areas Vivas.md
  MOC - Arquivo e Revisao.md

_archive_review/
  ...

templates/
  suggested/
```

Observacoes:

- `_staging/` ja existe e deve continuar como zona de entrada, triagem e manifestos temporarios.
- `_archive_review/` ja existe e continua como destino seguro para material que saiu do fluxo ativo mas ainda precisa de revisao humana.
- `_hubs/` e opcional. Se preferir menor impacto, os MOCs podem nascer dentro das areas vivas, sem pasta central.
- Areas operacionais vivas nao precisam ser movidas. Cada area ativa pode ganhar apenas uma nota-home local.

## Como Conviver com o Legado

Em vez de reorganizar tudo, usar regras de convivencia:

- notas novas seguem a nova convencao
- notas antigas so mudam quando forem revisadas por motivo real
- hubs apontam para o legado como ele esta hoje
- arquivo e staging recebem novos fluxos, nao retrofits totais
- sub-vaults mantem autonomia local

## Areas Operacionais Vivas

A unidade minima sugerida para uma area viva e:

- uma pasta ou area ja existente que continua no lugar atual
- uma nota-home chamada `AREA - Nome da Area`
- um pequeno bloco com foco, filas e links principais

Estrutura interna sugerida para cada area viva:

```text
AREA - Nome da Area.md
Projetos/
Notas/
Referencias/
```

Isto e um alvo futuro, nao um requisito de migracao. Onde a pasta ja existe com outro nome, a nota-home pode ser adicionada sem renomear nada.

## Arquivo

Separacao leve:

- ativo: o que recebe trabalho, links e revisao recorrente
- staging: captura bruta, rascunhos, importacoes e triagem
- archive review: material fora do fluxo ativo, mas preservado para decisao posterior

Regra pratica:

- nao apagar no inicio
- mover apenas por decisao local e revisavel
- preservar contexto original no arquivo quando houver duvida

## Staging e Inbox

Uso sugerido para `_staging/`:

- `inbox/`: entradas novas, capturas rapidas, notas sem destino final
- `review/`: lotes temporarios de limpeza, clusters, listas de links ou dedupe
- `manifests/`: saidas operacionais para revisao humana

Convencao leve de fluxo:

1. capturar em `inbox/`
2. classificar para area viva, referencia ou arquivo
3. se houver incerteza, manter em staging
4. so promover para uma area quando a nota ganhar contexto

## Hubs e MOCs

MOCs devem ser navegacionais, nao enciclopedicos. Sugestao de camadas:

- `MOC - Inicio`: entrada raiz do vault principal
- `MOC - Areas Vivas`: ponte para areas operacionais ativas
- `MOC - Arquivo e Revisao`: ponte para staging, arquivo e processos de manutencao
- MOCs locais por dominio, quando uma area ficar grande demais

Cada MOC deve:

- listar poucos links fortes
- apontar para notas-home de areas
- evitar virarem dump de centenas de links
- incluir uma pequena secao `Proximos movimentos`

## Frontmatter Minimo

Para conteudo novo ou revisado manualmente, o minimo sugerido e:

```yaml
---
title: "{{title}}"
type: note
status: active
created: {{date:YYYY-MM-DD}}
updated: {{date:YYYY-MM-DD}}
---
```

Campos opcionais, so quando ajudarem:

- `area`
- `aliases`
- `tags`
- `source`

Convencoes de valor:

- `type`: `note`, `moc`, `area`, `inbox`, `archive`
- `status`: `active`, `staged`, `reference`, `archived`

## Convencoes de Nome

Convencoes sugeridas apenas para conteudo novo:

- areas: `AREA - Nome da Area`
- hubs: `MOC - Tema`
- inbox: `YYYY-MM-DD HHmm - Titulo curto`
- notas gerais: `Titulo natural`
- arquivo: manter nome original; se precisar contextualizar, adicionar prefixo no frontmatter, nao no titulo

Regras leves:

- evitar `Untitled`, `Sem titulo`, `Nova nota`
- evitar nomes com versoes no titulo quando isso puder ir para frontmatter ou changelog
- evitar prefixos numericos exceto quando a ordem for parte real do uso
- preferir titulos humanos e buscaveis

## Templates Sugeridos

Foram adicionados templates minimos para:

- inbox capture
- note default
- hub/MOC
- area home
- archive record

Eles servem como padrao de adocao gradual e nao exigem mudanca retroativa.

## Recomendacao de Adocao

Fase 1:

- usar os templates apenas em notas novas
- criar `MOC - Inicio`
- criar 1 nota `AREA - ...` para cada area realmente viva

Fase 2:

- ligar orfaos prioritarios aos novos hubs
- promover capturas relevantes da inbox para areas
- registrar excecoes locais por sub-vault

Fase 3:

- revisar se vale criar variacoes de template por dominio
- expandir frontmatter minimo apenas onde trouxer beneficio operacional real
