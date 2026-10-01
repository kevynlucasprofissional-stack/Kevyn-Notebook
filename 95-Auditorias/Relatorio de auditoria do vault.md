---
id: relatorio-de-auditoria-do-vault
titulo: Relatório de auditoria do vault
tipo: auditoria
status: auditado
profundidade: avancada
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-06-17
ultima_revisao: 2026-06-17
grau_confianca: alto
sensibilidade: alta
camada_evidencia: documento_operacional
tags:
- tipo/auditoria
- auditoria/tecnica
---

# Relatório de auditoria do vault

## Resultado técnico pré-release

| Verificação | Resultado |
|---|---:|
| arquivos auditados (exclui o próprio JSON de saída) | 284 |
| notas Markdown | 252 |
| arquivos Canvas | 4 |
| frontmatter ausente | 0 |
| YAML ou UTF-8 inválido | 0 |
| IDs duplicados | 0 |
| basenames duplicados | 0 |
| links internos | 945 |
| links quebrados | 0 |
| links ambíguos | 0 |
| notas isoladas | 0 |
| erros Canvas | 0 |
| referências Canvas quebradas | 0 |
| nomes corrompidos `#Uxxxx` | 0 |

## Auditoria complementar

`auditoria-customizada-final.json` verificou campos universais, vocabulários controlados, JSON, Bases, arquivos vazios, nomes, consultas e preservação das entradas. Resultado: **aprovado, zero falhas bloqueantes**.

## Evidências

- `95-Auditorias/auditoria-estatica-final.json`
- `95-Auditorias/auditoria-customizada-final.json`
- [[Auditoria de fontes]]
- [[Auditoria de privacidade]]
- [[Auditoria de versoes]]
- [[Auditoria editorial e de evidencias]]
- [[Matriz de cobertura]]
- [[Checklist de release]]

## Limitações

A auditoria é estática. O ambiente não executou o aplicativo Obsidian, o índice Dataview nem a renderização Kanban. Os arquivos `.base`, JSON, Canvas, YAML, caminhos, consultas e declarações de plugin foram validados estruturalmente.

## Critério de release

O ZIP final deve ser extraído em diretório limpo, ter a mesma árvore e os mesmos hashes do diretório produzido, e repetir as auditorias sem falhas bloqueantes.

## Validação por extração limpa

O pacote inicial foi extraído e comparado com a origem: **285 arquivos**, zero ausências, zero extras e zero divergências SHA-256. A auditoria da cópia retornou zero links quebrados e zero bloqueantes. O release final repete esse gate após a atualização dos relatórios internos.
