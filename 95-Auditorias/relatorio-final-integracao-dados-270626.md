---
id: relatorio-final-integracao-dados-270626
titulo: Relatorio final de integracao de dados 270626
tipo: relatorio
status: revisado
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-06-27
ultima_revisao: 2026-06-27
grau_confianca: medio_alto
sensibilidade: alta
camada_evidencia: sintese_derivada
tags:
  - tipo/relatorio
  - processo/integracao
  - privacidade/restrita
---

# Relatorio final de integracao de dados 270626

## Visao geral

O lote `270626 Dados novos` foi integrado no vault de trabalho `Kevyn Neo` com uma regra simples: a transcricao de 26/06/2026 entrou como fonte principal, enquanto as leituras derivadas ficaram como apoio documental. Isso preserva a hierarquia entre registro bruto, leitura interpretativa e sintese editorial.

## O que foi integrado

- 1 nota-fonte nova: `Fonte - Reuniao com psicologa Suzana 2026-06-26`
- 1 estado atual novo: `Estado atual - 27 de junho de 2026`
- 1 matriz de claims nova: `Matriz-Claims.csv`
- 1 manifesto de fontes atualizado
- 1 matriz de cobertura atualizada
- 1 decisao nova em `Registro-de-Decisoes.md`
- 1 atualização no changelog

## O que foi preservado sem inflar o nucleo

- 3 arquivos derivados do lote permaneceram como apoio documental
- a analise de discurso foi tratada como leitura secundária
- a analise de comunicacao nao verbal foi tratada como leitura secundaria
- a analise complementar de 12/06/2026 foi mantida como contexto historico, nao como substituto da transcricao

## Efeitos práticos

- 4 claims rastreaveis foram registradas;
- 2 notas novas foram criadas;
- 5 notas centrais receberam ajuste de proveniencia e contexto;
- a proxima sessao terapeutica ficou registrada para 10/07/2026;
- a separacao entre fato bruto e leitura derivada ficou mais clara no vault.

## Correção adicional

A `Controle-Revisao-100/Matriz-Revisao-100.csv` foi reconciliada para deixar de marcar `pendente_leitura` em registros que já estavam como `lido_integralmente` e `extraido`. O estado final passou a ser `analisado_nao_integrado`, removendo a contradição pedida pelo objetivo.

## Conclusao

A integracao cumpriu o objetivo do lote: curadoria do material novo sem transformar leitura automatizada em fato central, mantendo rastreabilidade, privacidade e separacao epistemica.
