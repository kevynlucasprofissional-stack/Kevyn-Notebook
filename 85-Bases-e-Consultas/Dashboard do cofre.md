---
id: dashboard-do-cofre
titulo: Dashboard do cofre
tipo: controle
status: curado
profundidade: intermediaria
versao_schema: '1.0'
versao_conteudo: '1.4'
idioma: pt-BR
data_criacao: 2026-06-17
ultima_revisao: 2026-06-25
fontes_primarias:
  - '[[Fonte - Briefing do projeto]]'
notas_relacionadas:
  - '[[MOC Geral]]'
  - '[[LEIA-ME]]'
  - '[[Guia de uso]]'
  - '[[Claims principais]]'
  - '[[Trilha rapida - quem e Kevyn]]'
  - '[[Kevyn Lucas]]'
  - '[[Portfolio de projetos]]'
  - '[[MOC Trabalho vocacao e projetos]]'
  - '[[MOC Saude autocuidado e autorregulacao]]'
  - '[[MOC Planos e decisoes]]'
  - '[[MOC Estudos e referencias]]'
  - '[[MOC Fontes e evidencias]]'
  - '[[Trilha de revisao de projetos]]'
  - '[[Trilha de auditoria das interpretacoes]]'
grau_confianca: alto
sensibilidade: alta
camada_evidencia: sintese_derivada
tags:
  - tipo/controle
  - obsidian/dataview
  - privacidade/restrita
---

# Dashboard do cofre

## Núcleo rápido

- [[MOC Geral]]
- [[Trilha rapida - quem e Kevyn]]
- [[Claims principais]]
- [[Kevyn Lucas]]
- [[Linha do tempo mestre]]
- [[Portfolio de projetos]]
- [[ACIRV]]
- [[Acompanhamento psicologico]]
- [[Cuidado de si]]
- [[MOC Trabalho vocacao e projetos]]
- [[MOC Saude autocuidado e autorregulacao]]
- [[MOC Planos e decisoes]]
- [[MOC Estudos e referencias]]
- [[MOC Fontes e evidencias]]
- [[Trilha de revisao de projetos]]

## Perguntas de entrada

- Quem é Kevyn hoje? Use [[Claims principais]] e [[Kevyn Lucas]].
- Como ele mudou? Use [[Linha do tempo mestre]] e [[MOC Cronologia e memorias]].
- O que está em execução? Use [[Portfolio de projetos]] e [[MOC Trabalho vocacao e projetos]].
- Onde o cuidado pesa? Use [[Cuidado de si]], [[Acompanhamento psicologico]] e [[MOC Saude autocuidado e autorregulacao]].
- Onde a leitura ainda é hipótese? Use [[Trilha de auditoria das interpretacoes]] e [[MOC Fontes e evidencias]].

## Situação atual

O vault já não depende só de inventário ou de fonte bruta para fazer sentido. O núcleo útil agora passa por claims, biografia, cronologia, projetos, cuidado e decisão. Se uma leitura não toca esses eixos, ela tende a ser periférica.

## Atualizações recentes

```dataview
TABLE WITHOUT ID
  file.link AS "Nota",
  tipo AS "Tipo",
  ultima_revisao AS "Revisão"
FROM "00-Inicio" OR "01-Perfil-e-Autoconhecimento" OR "02-Cronologia-e-Memorias" OR "03-Relacionamentos-e-Rede" OR "04-Trabalho-Vocacao-e-Projetos" OR "05-Sonhos-Simbolos-e-Espiritualidade" OR "06-Saude-Autocuidado-e-Autorregulacao" OR "07-Planos-e-Decisoes" OR "08-Estudos-e-Referencias" OR "80-MOCs-e-Trilhas" OR "85-Bases-e-Consultas"
SORT ultima_revisao DESC
LIMIT 12
```

## Projetos ativos

```dataview
TABLE WITHOUT ID
  file.link AS "Projeto",
  ultima_evidencia AS "Evidência"
FROM "04-Trabalho-Vocacao-e-Projetos"
WHERE tipo = "projeto" AND estado_projeto = "ativo"
SORT ultima_evidencia DESC
```

## Se o plugin não carregar

Use esta rota manual:

- [[Claims principais]]
- [[Trilha rapida - quem e Kevyn]]
- [[Kevyn Lucas]]
- [[Portfolio de projetos]]
- [[MOC Trabalho vocacao e projetos]]
- [[MOC Saude autocuidado e autorregulacao]]
- [[MOC Planos e decisoes]]
- [[MOC Estudos e referencias]]
- [[MOC Fontes e evidencias]]
- [[Trilha de revisao de projetos]]
- [[Trilha de auditoria das interpretacoes]]
- [[Trilha de preparacao para terapia]]

## Leitura rápida

Se o objetivo for entender Kevyn agora, comece por biografia, claims e projetos. Se o objetivo for entender custo de vida e execução, vá para cuidado, terapia e decisão. Se o objetivo for entender o mecanismo do vault, volte ao `MOC Geral`.
