---
id: checklist-de-release
titulo: Checklist de release
tipo: auditoria
status: auditado
profundidade: avancada
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-06-17
ultima_revisao: 2026-06-17
grau_confianca: alto
sensibilidade: baixa
camada_evidencia: documento_operacional
tags:
- tipo/auditoria
- auditoria/release
---

# Checklist de release

## Gates concluídos

- [x] arquivo original preservado por SHA-256;
- [x] briefing preservado por SHA-256;
- [x] todas as notas com frontmatter;
- [x] YAML e UTF-8 válidos;
- [x] IDs e basenames sem duplicação;
- [x] vocabulários controlados válidos;
- [x] wikilinks sem destinos quebrados;
- [x] Canvas estruturalmente válidos;
- [x] referências de arquivo em Canvas existentes;
- [x] JSON e Bases parseáveis;
- [x] consultas sem pastas inexistentes;
- [x] inventário e métricas produzidos;
- [x] ZIP extraído em diretório limpo;
- [x] 285 arquivos comparados por caminho e SHA-256;
- [x] zero ausências, extras ou divergências de hash;
- [x] auditorias repetidas sobre a cópia extraída.

## Evidência da primeira extração limpa

- teste de integridade ZIP: aprovado;
- retorno do auditor estático: `0`;
- links quebrados após extração: `0`;
- bloqueantes da auditoria complementar: `0`.

## Limitação

O ambiente não abriu o aplicativo Obsidian nem executou Dataview/Kanban. Foram realizados testes estáticos dos arquivos, configurações e dependências declaradas.
