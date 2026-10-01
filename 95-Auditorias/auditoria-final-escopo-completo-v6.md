---
id: auditoria-final-escopo-completo-v6
titulo: Auditoria final do escopo completo v6
tipo: auditoria
status: concluido
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-06-30
ultima_revisao: 2026-06-30
escopo: completo
---

# Auditoria final do escopo completo v6

## Resumo executivo

O escopo completo continua carregando o ruido historico esperado de um vault vivo: backups, arquivos herdados, registros brutos e copias de revisao.

## Indicadores do recorte completo

| Indicador | Valor |
|---|---:|
| Arquivos totais | 1886 |
| Markdown | 1427 |
| Canvas | 4 |
| Frontmatter ausente | 233 |
| YAML ou UTF-8 invalido | 0 |
| IDs duplicados | 27 |
| Basenames duplicados | 35 |
| Aliases compartilhados | 35 |
| Wikilinks ocorrencias | 9541 |
| Wikilinks quebrados | 155 |
| Wikilinks ambiguos | 3703 |
| Sem links de entrada | 409 |
| Sem links de saida | 1105 |
| Isoladas | 296 |
| Arquivos maiores que 1 MB | 20 |

## Onde o ruido fica

- `70-Fontes-Brutas`
- `Controle-Integracao/Ciclos`
- `Controle-Integracao/Backups-Revisao`
- arquivos de revisao historica, backups de notas e artefatos temporarios

## Leitura correta

Os problemas do escopo completo nao derrubam o nucleo curado. Eles descrevem historia, copia, revisao e redundancia. O erro seria tratar esse ruido como se fosse o estado editorial do recorte ativo.

## Conclusao

O escopo completo segue aprovado com ressalvas, e o volume de ruido continua compatível com o historico do projeto.
