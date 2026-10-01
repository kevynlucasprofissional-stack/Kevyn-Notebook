---
name: obsidian-vault-ops
description: Use esta skill quando a tarefa envolver auditoria, limpeza, deduplicação, melhoria de navegabilidade, staging, relatórios ou refatoração segura de um vault Obsidian grande. Não use para fusão semântica autônoma de notas longas, nem para exclusão destrutiva em massa.
---

# Obsidian Vault Ops

## Finalidade
Executar operações seguras e reversíveis em vault Obsidian:
- inventário
- relatórios
- detecção de duplicatas exatas
- agrupamento de near-duplicates
- classificação de lixo/import/espelho
- reparo planejado de links
- geração de hubs/MOCs
- padronização mínima de frontmatter

## Regras de segurança
- Sempre ler `AGENTS.md` antes de agir.
- Sempre preferir gerar relatório antes de modificar.
- Nunca apagar em lote em tarefas iniciais.
- Se houver `.obsidian/` em uma subpasta, tratar como sub-vault e não cruzar automaticamente essa fronteira.
- Se houver Obsidian CLI disponível, preferir comandos do Obsidian para rename/move.
- Se Obsidian CLI não estiver disponível, restringir alterações a análises, manifestos, metadados e staging seguro.

## Sequência padrão
1. criar ou atualizar relatório em `reports/`
2. gerar ou atualizar changelog em `logs/`
3. aplicar somente o escopo pedido
4. revisar diff
5. resumir riscos e próximos passos

## Tipos de saída preferidos
- Markdown para relatório executivo
- JSON para listas de arquivos, clusters e manifestos
- CSV somente quando ajudar revisão em massa

## Heurísticas úteis
- duplicata exata = hash idêntico
- near-duplicate = similaridade textual alta, mas sem ação automática
- lixo provável = `.trash/`, nomes vazios, import mirrors, rascunhos genéricos
- prioridade de recuperação = notas centrais, hubs, áreas operacionais vivas

## Nunca fazer sem confirmação explícita
- excluir permanentemente
- consolidar dossiês longos
- mover conteúdo entre sub-vaults
- alterar o sentido de notas pessoais
