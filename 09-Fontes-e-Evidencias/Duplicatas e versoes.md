---
id: duplicatas-e-versoes
titulo: Duplicatas e versões
tipo: auditoria
status: auditado
profundidade: avancada
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-06-17
ultima_revisao: 2026-06-17
fontes_primarias:
- '[[Fonte - Conversas com ChatGPT]]'
grau_confianca: alto
sensibilidade: alta
camada_evidencia: sintese_derivada
tags:
- tipo/auditoria
- tema/fontes
- privacidade/restrita
aliases:
- Duplicatas e versões
---
# Duplicatas e versões

## Achado

A inspeção detectou 709 grupos de arquivos com conteúdo exatamente idêntico, envolvendo 2.202 arquivos. Também foram encontrados 718 grupos de basenames Markdown repetidos e 87 arquivos vazios.

## Causa provável

O acervo contém exportações consolidadas, cópias de cofres, versões de notas e agregações em pastas diferentes. Duplicata técnica não implica necessariamente duplicata de intenção, mas torna inadequada a importação indiscriminada.

## Tratamento

- preservar integralmente o ZIP original;
- registrar SHA-256 e caminhos no manifesto;
- selecionar uma representação legível para fontes centrais;
- não apagar nem modificar originais;
- produzir notas temáticas novas em vez de escolher silenciosamente uma “versão verdadeira”;
- registrar conflitos de conteúdo em [[Registro de conflitos e incertezas]].

## Release

O vault produzido não deve conter basenames Markdown duplicados não intencionais.
