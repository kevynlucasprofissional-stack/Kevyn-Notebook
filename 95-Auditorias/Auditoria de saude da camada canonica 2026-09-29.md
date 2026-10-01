---
id: auditoria-saude-camada-canonica-2026-09-29
titulo: Auditoria de saúde da camada canônica — 2026-09-29
tipo: auditoria
status: auditado
profundidade: avancada
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-09-29
ultima_revisao: 2026-09-29
grau_confianca: alto
sensibilidade: media
camada_evidencia: documento_operacional
tags:
- tipo/auditoria
- infraestrutura/saude-do-vault
notas_relacionadas:
- '[[MOC Geral]]'
- '[[MOC Fontes e evidencias]]'
- '[[Changelog do vault]]'
---

# Auditoria de saúde da camada canônica — 2026-09-29

## Escopo e método

Auditoria da camada canônica (`00`–`08` + `80-MOCs-e-Trilhas`), considerando as zonas definidas em [[AGENTS.md]]. Foram verificados: links quebrados, notas órfãs, MOCs desatualizados, cobertura temporal e duplicação semântica.

## Métricas gerais

| Métrica | Valor |
|---|---|
| Notas canônicas | 130 |
| Links quebrados (fonte → destino) | 0 |
| Notas órfãs (sem backlink) | 2 → 0 após correção |
| MOCs com defasagem de revisão | 8 |
| Períodos ausentes na base | 2019, 2022, 2004–2017 |

## 1. Links

Nenhum wikilink quebrado na camada ativa (descontados falsos positivos em code spans e alvos que resolvem em `Processamento-Automatico`/`.json`).

## 2. Notas órfãs (corrigidas)

| Nota | Situação | Correção |
|---|---|---|
| `Revisao de autorregulacao 15 de junho de 2026` | sem backlink | ligada em [[Vontade SMART]] |
| `ACIRV - nota de transcricao` | sem backlink | ligada em [[ACIRV]] |

## 3. MOCs desatualizados

MOCs cuja `ultima_revisao` é anterior à nota mais recente que referenciam. Devem ser relidos/enriquecidos na próxima passagem:

- [[MOC Cronologia e memorias]]
- [[MOC Estudos e referencias]]
- [[MOC Perfil e autoconhecimento]]
- [[MOC Planos e decisoes]]
- [[MOC Relacionamentos e rede]] (atualizado nesta data)
- [[MOC Saude autocuidado e autorregulacao]]
- [[MOC Sonhos simbolos e espiritualidade]]
- [[MOC Trabalho vocacao e projetos]]
- [[Trilha de preparacao para terapia]]
- [[Trilha de revisao de projetos]]

## 4. Cobertura temporal

Anos citados por número de notas canônicas:

| Período | Notas | Leitura |
|---|---:|---|
| 2002–2003 | 16 | origem; data de nascimento consolidada (17/07/2003) |
| 2004–2017 | 0 | infância/adolescência sem fontes diretas (lacuna conhecida) |
| 2018 | 2 | menções pontuais |
| 2019 | 0 | ausente |
| 2020 | 1 | quase ausente |
| 2021 | 23 | início da autonomia material |
| 2022 | 0 | **ausente** |
| 2023 | 8 | diário Parte 01 (set–dez) |
| 2024 | 19 | diário Parte 01 (jan–abr) e derivados |
| 2025 | 39 | crise, Chá e Prosa, trabalhos |
| 2026 | 130 | recorte dominante |

Lacunas prioritárias continuam sendo **infância (2004–2017)** e **2022**, além de 2019–2020.

## 5. Duplicação semântica

Por similaridade de título, não há duplicatas reais. O único par próximo é `Estado atual - 17 de junho de 2026` ~ `Estado atual - 27 de junho de 2026` (retratos datados distintos, não duplicatas). A duplicação relevante que já existia (camada de backups em `Controle-Integracao`) foi retirada do índice na revisão de 29/09.

## 6. Recomendações

1. Reler e enriquecer os MOCs listados no item 3, começando por [[MOC Relacionamentos e rede]] e [[MOC Cronologia e memorias]].
2. Priorizar fontes que cubram **2022** e a infância (2004–2017) na próxima fila de curadoria.
3. Manter a rotina de verificação de links após cada rodada de curadoria.
4. Repetir esta auditoria a cada ciclo relevante e registrar mudanças em [[Changelog do vault]].

## Proveniência

- Método: análise automatizada do grafo de wikilinks e de metadados (`ultima_revisao`) da camada canônica.
- Data: `2026-09-29`.
