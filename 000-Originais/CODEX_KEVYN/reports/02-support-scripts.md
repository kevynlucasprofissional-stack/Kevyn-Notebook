# Support Scripts 02

- Gerado em: 2026-04-04
- Objetivo: criar a base de scripts pedida para inventário, deduplicação exata, near-duplicate, auditoria de links, triagem para quarentena e frontmatter mínimo.

## Método

- Criação de um módulo utilitário compartilhado em `scripts/_vault_utils.py`.
- Implementação de seis scripts Python com saída padrão em `reports/` e `logs/`.
- Adoção de defaults conservadores: leitura apenas por padrão, sem delete, sem merge automático e sem cruzar sub-vaults aninhados em mudanças.

## Critérios

- `inventory.py` cobre contagens, orfandade estrutural, nomes ruins, `.trash`, sub-vaults e áreas espelho/import.
- `exact_dedupe.py` trabalha com hash de conteúdo, grupos exatos e sugestão de canônico sem apagar nada.
- `near_dedupe.py` gera pares e clusters revisáveis por similaridade, com score e frases em comum.
- `link_audit.py` lista links quebrados, alvos não resolvidos, órfãos prioritários e hubs/MOCs sugeridos.
- `quarantine_candidates.py` produz manifesto revisável para `_archive_review/`, sem mover nada.
- `frontmatter_minimum.py` fica em dry-run por padrão e só escreve com `--apply`.

## Arquivos afetados

- `scripts/_vault_utils.py`
- `scripts/inventory.py`
- `scripts/exact_dedupe.py`
- `scripts/near_dedupe.py`
- `scripts/link_audit.py`
- `scripts/quarantine_candidates.py`
- `scripts/frontmatter_minimum.py`
- `reports/02-support-scripts.json`
- `reports/02-support-scripts.md`
- `logs/02-support-scripts.md`

## Riscos

- `frontmatter_minimum.py` usa parser YAML propositalmente conservador; frontmatter complexo é pulado.
- Heurísticas de links, espelho/import e near-duplicate podem gerar falsos positivos e exigem revisão humana.
- A etapa atual entrega scripts e artefatos de validação, mas não cria checkpoint Git automaticamente.

## Próximos passos

- Criar checkpoint Git antes de novas execuções que gerem ou atualizem artefatos de relatório.
- Rodar `frontmatter_minimum.py` primeiro sem `--apply` e revisar o manifesto.
- Priorizar revisão dos relatórios `03` a `07` antes de qualquer ação sobre o vault.

## Validação

- `python -m py_compile` executado com sucesso para `scripts/_vault_utils.py` e os seis scripts pedidos.
- `git status --short` confirmou worktree ativo nesta sessão.

## Escopo Entregue

- `inventory.py`: inventário estrutural e triagem de navegação.
- `exact_dedupe.py`: duplicatas exatas por SHA-256 com sugestão de arquivo canônico.
- `near_dedupe.py`: clusters revisáveis por MinHash + Jaccard.
- `link_audit.py`: quebra de links, órfãos prioritários e hubs.
- `quarantine_candidates.py`: candidatos a quarentena por heurística.
- `frontmatter_minimum.py`: plano e aplicação opcional de frontmatter mínimo.
