---
id: consultas-dataview
titulo: Consultas Dataview
tipo: consulta
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
- tipo/consulta
- obsidian/dataview
notas_relacionadas:
- '[[Bases e consultas - guia]]'
- '[[Dashboard do cofre]]'
- '[[MOC Geral]]'
- '[[Claims principais]]'
- '[[Trilha de auditoria das interpretacoes]]'
- '[[MOC Fontes e evidencias]]'
---
# Consultas Dataview

## Notas com pendências

```dataview
TABLE WITHOUT ID
  file.link AS "Nota",
  tipo AS "Tipo",
  pendencias AS "Pendências",
  ultima_revisao AS "Revisão"
FROM "01-Perfil-e-Autoconhecimento" OR "02-Cronologia-e-Memorias" OR "03-Relacionamentos-e-Rede" OR "04-Trabalho-Vocacao-e-Projetos" OR "05-Sonhos-Simbolos-e-Espiritualidade" OR "06-Saude-Autocuidado-e-Autorregulacao" OR "07-Planos-e-Decisoes" OR "08-Estudos-e-Referencias"
WHERE pendencias AND length(pendencias) > 0
SORT ultima_revisao DESC
```

## Projetos por estado

```dataview
TABLE WITHOUT ID
  file.link AS "Projeto",
  estado_projeto AS "Estado",
  ultima_evidencia AS "Última evidência",
  grau_confianca AS "Confiança"
FROM "04-Trabalho-Vocacao-e-Projetos"
WHERE tipo = "projeto"
SORT estado_projeto ASC, file.name ASC
```

## Eventos cronológicos

```dataview
TABLE WITHOUT ID
  file.link AS "Evento",
  data_inicio AS "Início",
  data_fim AS "Fim",
  grau_confianca AS "Confiança"
FROM "02-Cronologia-e-Memorias"
WHERE tipo = "evento"
SORT data_inicio ASC
```

## Fontes selecionadas por camada

```dataview
TABLE WITHOUT ID
  file.link AS "Fonte",
  formato_origem AS "Formato",
  data_fonte AS "Data",
  camada_evidencia AS "Camada",
  sensibilidade AS "Sensibilidade"
FROM "09-Fontes-e-Evidencias"
WHERE tipo = "fonte"
SORT data_fonte DESC, file.name ASC
```

## Notas de sensibilidade muito alta

```dataview
TABLE WITHOUT ID
  file.link AS "Nota",
  tipo AS "Tipo",
  camada_evidencia AS "Camada"
FROM "01-Perfil-e-Autoconhecimento" OR "02-Cronologia-e-Memorias" OR "03-Relacionamentos-e-Rede" OR "04-Trabalho-Vocacao-e-Projetos" OR "05-Sonhos-Simbolos-e-Espiritualidade" OR "06-Saude-Autocuidado-e-Autorregulacao" OR "07-Planos-e-Decisoes" OR "08-Estudos-e-Referencias" OR "09-Fontes-e-Evidencias"
WHERE sensibilidade = "muito_alta"
SORT file.name ASC
```

## Notas sem fonte declarada

```dataview
TABLE WITHOUT ID
  file.link AS "Nota",
  tipo AS "Tipo",
  grau_confianca AS "Confiança"
FROM "01-Perfil-e-Autoconhecimento" OR "02-Cronologia-e-Memorias" OR "03-Relacionamentos-e-Rede" OR "04-Trabalho-Vocacao-e-Projetos" OR "05-Sonhos-Simbolos-e-Espiritualidade" OR "06-Saude-Autocuidado-e-Autorregulacao" OR "07-Planos-e-Decisoes" OR "08-Estudos-e-Referencias"
WHERE (!fontes_primarias OR length(fontes_primarias) = 0) AND (!fontes_derivadas OR length(fontes_derivadas) = 0)
SORT file.name ASC
```

## Limitações

Dataview é somente uma camada de leitura. Correções devem ser feitas no frontmatter das notas. As consultas não substituem a auditoria estática em `95-Auditorias`.
