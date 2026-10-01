---
id: guia-de-uso
titulo: Guia de uso
tipo: controle
status: curado
profundidade: intermediaria
versao_schema: '1.0'
versao_conteudo: '1.2'
idioma: pt-BR
data_criacao: 2026-06-17
ultima_revisao: 2026-06-25
notas_relacionadas:
  - '[[MOC Geral]]'
  - '[[Dashboard do cofre]]'
  - '[[Trilha de revisao de projetos]]'
  - '[[Trilha de preparacao para terapia]]'
tags:
- navegacao/guia
---
# Guia de uso

## Uso sem plugins

Todo o conteúdo principal funciona em Markdown puro. Navegue por [[MOC Geral]], [[Dashboard do cofre]], backlinks, busca e Canvas.

## Recursos nativos

- **Properties:** os campos YAML classificam tipo, status, confiança, sensibilidade e fontes.
- **Links e backlinks:** cada link relevante é acompanhado por uma explicação da relação.
- **Templates:** use os modelos em `90-Templates`.
- **Graph View:** a configuração em `.obsidian/graph.json` agrupa áreas temáticas.
- **Canvas:** abra os arquivos `.canvas` em `80-MOCs-e-Trilhas`.
- **Bases:** os arquivos `.base` em `85-Bases-e-Consultas` filtram notas por propriedades.
- **Dashboard:** [[Dashboard do cofre]] concentra o núcleo de leitura rápida e a visão operacional.

## Plugins comunitários permitidos

- **Dataview:** necessário apenas para as consultas dinâmicas de [[Consultas Dataview]].
- **Kanban:** necessário para renderizar [[Kanban de projetos]] e [[Kanban de pendencias]] como quadros. Sem o plugin, ambos continuam legíveis como listas Markdown.

Os plugins não estão embutidos no ZIP. Instale-os pelo navegador de plugins comunitários do Obsidian.

## Rotina de manutenção

1. Criar nota a partir de um template.
2. Preencher fonte, camada de evidência e sensibilidade.
3. Ligar a um MOC e explicar a relação.
4. Atualizar status e data de revisão.
5. Rodar `python 98-Infraestrutura/auditar_vault.py .` fora do Obsidian quando fizer mudanças estruturais.

## Referências rápidas

Consulte [[Glossario do cofre]] e [[LEIA-ME Anexos]] quando necessário.
