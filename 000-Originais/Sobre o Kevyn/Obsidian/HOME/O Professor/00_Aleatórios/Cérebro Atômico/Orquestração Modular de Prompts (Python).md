---
Resumo: Metodologia para superar limites de contexto em LLMs via scripts externos.
Contexto: Arquivo 'Como criar o ECO V3.md', discussão sobre arquitetura de IA.
tags:
  - "#IA"
  - "#engenharia_de_prompt"
  - "#python"
ID único: 20251123022106-7p1fr7
created: 2025-11-23
---
# Orquestração Modular de Prompts (Python)

## Conceito
Em sistemas complexos de IA, prompts monolíticos falham devido à complexidade e limites de contexto. A solução é a 'Orquestração Modular': dividir o prompt em arquivos especializados (ex: Analista DISC, Analista Eneagrama) e usar um script externo (Python) para gerenciar o fluxo. O script atua como um 'Chef', lendo a 'receita' (prompt), buscando os 'ingredientes' (dados), processando cada etapa isoladamente e, crucialmente, injetando o *output* da Etapa A como *contexto* na Etapa B. Isso move a lógica de citação e memória da 'janela de contexto' da IA para a memória do script.

## Importância
Permite criar sistemas de IA escaláveis, auditáveis e capazes de tarefas muito mais complexas do que uma única interação de chat permitiria.

## Insight
Isso se conecta com [[Sistema 2 (Pensamento Lento)]] porque o script força a IA a processar passo-a-passo (deliberativo) em vez de tentar alucinar uma resposta rápida (Sistema 1).

### Conexões:
- [[Sistema 2 (Pensamento Lento)]]
- [[Metodologia de Curadoria de IA]]

## Ação
- [ ] Refatorar prompts longos quebrando-os em tarefas atômicas e criando um script para encadear as saídas.

## Flashcards

Na orquestração modular, quem gerencia o fluxo de dados entre os prompts?::O script externo (ex: Python), não a própria IA.
<!--SR:!2025-11-26,2,248-->

Qual a vantagem da orquestração modular sobre prompts monolíticos?::Contornar limites de contexto, maior controle, facilidade de manutenção e especialização das tarefas.
<!--SR:!2025-11-24,1,230-->

O papel do script Python na orquestração é atuar como um ==maestro/orquestrador== que conecta inputs e outputs.
