---
id: fonte-src-000156
titulo: Fonte - SRC-000156 - 00_rascunho
tipo: fonte
status: auditado
profundidade: indice
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-06-18
ultima_revisao: 2026-06-18
ciclo_integracao: CICLO-0023
fonte_id: SRC-000156
caminho_origem: Outras notas criadas por Kevyn/Notas/00_rascunho.md
sha256: 2de784260cf06ff12c9e7d8c9ae04285f0e7a498b265319bfcd6631751f942d4
bytes: 10170
camada_evidencia: documento_operacional
grau_confianca: alto
sensibilidade: alta
destino_principal: '[[Inteligencia artificial e automacao]]'
tags:
- tipo/fonte
- processo/integracao
- privacidade/restrita
aliases:
- 00_rascunho
---
# Fonte - SRC-000156 - 00_rascunho

## Escopo

Arquivo lido integralmente pelo ciclo automatizado.

## Achados relevantes

- O resultado deve abrir no `demo.bpmn.io` sem erro, com: - fluxo conectado visualmente; - piscina e raias quando necessário; - eventos, tarefas, gateways e fins coloridos; - layout legível; - BPMNDI completo; - setas visíveis entre os elementos.
- 1. Quantos `bpmn:sequenceFlow` existem? 2. Quantos `bpmndi:BPMNEdge` existem? 3. Os números são iguais? 4. Cada `sequenceFlow` tem um `BPMNEdge` correspondente? 5. Cada `BPMNEdge` tem pelo menos dois `di:waypoint`? 6. Quantos eventos, tarefas, gateways e docum...
- - XML começa com `<?xml version="1.0" encoding="UTF-8"?>`; - usa `bpmn:definitions`; - inclui namespaces `bpmn`, `bpmndi`, `dc`, `di`, `xsi`, `bioc` e `color`; - IDs são únicos; - IDs não têm acento, espaço ou caractere especial; - não existe `&` solto; - exis...
- - todo `sequenceFlow` tem `BPMNEdge`; - todo `BPMNEdge` tem waypoints; - todo elemento visível tem `BPMNShape`; - todo `BPMNShape` tem cor; - todo `BPMNShape` tem `Bounds`; - piscina e raias aparecem visualmente; - início está verde; - tarefas estão azuis; - g...

## Integracao no nucleo

- Destino principal: [[Inteligencia artificial e automacao]]
- Classificacao: integrado
- Motivo: categoria=study; score=64.0

## Limites

- O texto foi resumido com cautela.
- Trechos sensiveis foram redigidos quando necessario.

## Proveniencia

- `CICLO-0023`: `SRC-000156` foi lido integralmente e integrado em [[Inteligencia artificial e automacao]].
