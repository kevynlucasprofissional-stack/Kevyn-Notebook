---
id: bases-e-consultas-guia
titulo: Bases e consultas — guia
tipo: infraestrutura
status: auditado
profundidade: intermediaria
versao_schema: '1.0'
versao_conteudo: '1.1'
idioma: pt-BR
data_criacao: 2026-06-17
ultima_revisao: 2026-06-25
fontes_primarias:
- '[[Fonte - Briefing do projeto]]'
grau_confianca: alto
sensibilidade: baixa
camada_evidencia: sintese_derivada
tags:
- tipo/infraestrutura
- obsidian/bases
- obsidian/dataview
aliases:
- Bases e consultas — guia
notas_relacionadas:
- '[[Dashboard do cofre]]'
- '[[Consultas Dataview]]'
- '[[MOC Geral]]'
- '[[Claims principais]]'
- '[[Trilha de auditoria das interpretacoes]]'
- '[[Guia de uso]]'
---
# Bases e consultas — guia

## Recursos

| Arquivo | Recurso | Função |
|---|---|---|
| `Conteudo.base` | Bases nativo | visão geral das notas de conteúdo |
| `Projetos.base` | Bases nativo | projetos com status e evidência |
| `Linha-do-Tempo.base` | Bases nativo | eventos datados |
| `Pessoas.base` | Bases nativo | pessoas e papéis |
| `Fontes.base` | Bases nativo | fontes selecionadas |
| [[Dashboard do cofre]] | Markdown + Dataview | visão operacional |
| [[Consultas Dataview]] | Dataview | consultas de auditoria e revisão |

## Modo degradado

As notas e MOCs permanecem legíveis sem plugins. Arquivos `.base` dependem do recurso nativo Bases do Obsidian. Blocos `dataview` exigem o plugin comunitário Dataview.

## Campos

As vistas usam propriedades controladas descritas em [[Schema YAML]] e [[Vocabularios controlados]]. Ao renomear pasta ou propriedade, revisar todos os arquivos `.base`, consultas e Canvas.
