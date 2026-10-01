# AGENTS.md

## Objetivo do repositório
Este repositório é um vault Obsidian grande e heterogêneo. O objetivo do agente NÃO é "reorganizar tudo" de forma autônoma.
O objetivo é:
1. auditar
2. gerar relatórios
3. aplicar correções mecânicas seguras e reversíveis
4. melhorar navegabilidade
5. só então propor consolidações semânticas para revisão humana

## Princípios obrigatórios
- Sempre trabalhar com Git e propor checkpoints claros.
- Nunca apagar em lote no começo. Preferir mover para `_archive_review/` ou gerar manifesto de revisão.
- Nunca fundir automaticamente notas longas, dossiês ou material pessoal denso.
- Nunca mover ou renomear em lote atravessando fronteiras de sub-vault sem aprovação explícita.
- Se houver Obsidian CLI disponível, preferir renames/moves via Obsidian em vez de filesystem cru.
- Se Obsidian CLI não estiver disponível, limitar-se a relatórios, manifestos e mudanças mecânicas de baixo risco.
- Toda tarefa em lote deve gerar changelog em `logs/`.
- Toda análise deve produzir saída em `reports/`.
- Toda decisão semântica deve vir como sugestão revisável, não como ação irreversível.

## Fronteiras e zonas sensíveis
Trate como fronteiras de sub-vault qualquer pasta que contenha `.obsidian/`.
Não atravesse essas fronteiras em batch refactors sem aprovação explícita.

Áreas com maior chance de espelho, importação, lixo ou redundância:
- `Google Drive (Not synced)/`
- `HOME/Clones/`
- `.trash/`
- arquivos `Untitled*`, `Sem título*`, nomes vazios ou genéricos
- cópias aparentes de vaults dentro do próprio vault

## Ordem de trabalho
1. Inventário
2. Quarentena de áreas espelho/lixo/import
3. Duplicatas exatas
4. Candidatos a near-duplicate
5. Links quebrados / aliases / orfandade prioritária
6. Hubs/MOCs
7. Estrutura futura (templates, frontmatter, convenções)

## Definição de “feito”
Uma tarefa só está concluída quando:
- há relatório em `reports/`
- há changelog em `logs/`
- há diff revisável
- não houve alteração destrutiva fora do escopo pedido

## Formato dos relatórios
Cada relatório deve incluir:
- objetivo
- método
- critérios
- arquivos afetados
- riscos
- próximos passos

## Convenções de saída
- `reports/*.md` para relatórios humanos
- `reports/*.json` para dados estruturados
- `logs/*.md` para changelog por tarefa
- `_staging/` para manifestos temporários
- `_archive_review/` para material movido para revisão
- `_merge_candidates/` para clusters de notas parecidas

## Tarefas proibidas sem nova instrução explícita
- apagar em lote
- mover milhares de arquivos
- reescrever notas pessoais densas
- mesclar automaticamente dossiês ou cronologias extensas
- padronizar semanticamente o cofre inteiro de uma vez

## Regra de operação do vault
- Sempre preferir Obsidian CLI para operações que dependam da integridade dos links do vault.
- Antes de usar filesystem cru para mover ou renomear notas, tentar primeiro comandos do Obsidian CLI.
- Teste inicial obrigatório: `obsidian help`