# 08 — Pendências e Bloqueios

## Bloqueios ativos

| ID | Arquivo | Motivo | Ação necessária |
|---|---|---|---|
| BLQ-001 | SRC-000103 (DS21 - Lançamento semente) | Contém credenciais (senhas, tokens) | Manter [SEGREDO REDIGIDO]. Não reler. |

## Pendências do planejamento

| ID | Descrição | Impacto | Resolução |
|---|---|---|---|
| PEN-001 | Fichas ARQ-001 a ARQ-100 não criadas | Bloqueia início dos ciclos | Gerar via script a partir do manifesto e da lista dos 100 |
| PEN-002 | Manifesto-Fontes.csv com 2.697 entradas históricas vs 2.923 atuais | Divergência documentada | Já resolvido — inventário incremental cobre 2.923 |
| PEN-003 | auditar_vault.py não executável (PyYAML) | Auditoria limitada a scripts PS | Manter scripts complementares; não instalar dependências globais |
| PEN-004 | Nota Kevyn Lucas com risco de sobrecarga | Pode precisar ser dividida durante R02 | Monitorar; decidir durante a execução |
| PEN-005 | Alguns SRC IDs na lista têm duplicatas em TODAS AS NOTAS | Já classificadas | Referenciar apenas o original (não a duplicata) |
| PEN-006 | Arquivos do Primeiro Segundo Cérebro com caminhos não canônicos | Navegação | Usar caminho do manifesto como autoridade |

## Pendências globais do projeto

| ID | Descrição |
|---|---|
| GBL-001 | Relatório Executivo e Relatório de Auditoria não refletem o estado pós-integração incremental |
| GBL-002 | CHECKSUMS.txt original da entrega não foi regenerado |
| GBL-003 | Changelog do vault não reflete modificações dos ciclos 0001-0036 |
| GBL-004 | Kanban de pendências não atualizado com as descobertas da integração |
