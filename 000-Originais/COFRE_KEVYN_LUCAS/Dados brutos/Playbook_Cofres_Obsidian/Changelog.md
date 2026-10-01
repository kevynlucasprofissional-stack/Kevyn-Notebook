---
titulo: "Changelog do Playbook para Construção de Cofres no Obsidian"
tipo: changelog
versao: "1.0"
data: 2026-06-17
---

# Changelog

## 1.0 — 17 de junho de 2026

### Adicionado

- manual universal com 18 fases de construção;
- estudo de caso do vault Filosofia Pós-Nietzsche;
- distinção entre práticas universais e dependentes do tema;
- matriz de recursos nativos, comunitários, obrigatórios e opcionais;
- schemas YAML e modelos por tipo de nota;
- taxonomia de relações semânticas;
- algoritmo de criação de links;
- padrões de MOC, trilhas, Graph View e Canvas;
- decisão Bases versus Dataview versus DataviewJS;
- biblioteca de consultas;
- checklists de produção, auditoria e release;
- prompt mestre reutilizável;
- templates Markdown;
- auditor estático em Python;
- relatórios reproduzíveis do estudo de caso;
- teste de compactação e reextração do próprio pacote.

### Decisões

- Markdown é o formato principal por ser nativo do Obsidian e facilmente reutilizável por IAs.
- O pacote é entregue como uma pasta que também pode ser aberta como vault de referência.
- Dataview e Templater são tratados como dependências opcionais.
- Bases é considerado recurso nativo prioritário para vistas editáveis.
- Auditorias narrativas precisam ser acompanhadas por dados verificáveis.

### Limitações conhecidas

- o script não executa o aplicativo Obsidian nem plugins;
- os templates exigem substituir os IDs marcados;
- exemplos de domínio precisam ser adaptados ao tema real;
- documentação técnica deve ser revalidada quando o Obsidian ou plugins mudarem.
