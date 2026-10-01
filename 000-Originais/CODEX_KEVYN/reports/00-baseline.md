# 00 Baseline

## Objetivo
Estabelecer um baseline operacional do vault atual, validar a infraestrutura mínima de trabalho e registrar riscos iniciais sem alterar nenhuma nota do vault.

## Método
- Leitura de `AGENTS.md` e do skill local `obsidian-vault-ops`
- Inspeção da raiz do repositório e da árvore de diretórios com PowerShell
- Identificação de fronteiras de sub-vault pela presença de `.obsidian/`
- Levantamento inicial de volumes por tipo de arquivo e de áreas sensíveis já previstas em `AGENTS.md`
- Verificação do estado Git para preservar trabalho pré-existente

## Critérios
- Não alterar notas do vault
- Limitar alterações a infraestrutura operacional e artefatos em `reports/` e `logs/`
- Tratar qualquer pasta com `.obsidian/` como fronteira de sub-vault
- Considerar `Google Drive (Not synced)/`, `HOME/Clones/`, `.trash/` e nomes genéricos como zonas prioritárias de auditoria

## O que foi encontrado
- O vault já possui a infraestrutura mínima pedida: `AGENTS.md`, `.agents/skills/obsidian-vault-ops/SKILL.md`, `scripts/`, `reports/`, `logs/`, `_staging/`, `_archive_review/` e `_merge_candidates/`.
- `AGENTS.md` e o skill local existiam, mas estavam com texto corrompido por encoding; a correção para UTF-8 legível foi o único ajuste estrutural aplicado.
- Há trabalho operacional anterior já registrado em `reports/`, `logs/` e `scripts/`; o repositório não está limpo e esses artefatos foram preservados.
- Foram identificadas 7 fronteiras de sub-vault pela presença de `.obsidian/`.

## Inventário inicial
- Total de arquivos observados no repositório: 6977
- Arquivos Markdown: 3595
- Arquivos Canvas: 5
- PDFs: 36
- Imagens raster/vetoriais detectadas por extensão comum: 22

## Distribuição inicial por áreas
- `HOME/`: 3274 arquivos
- `Google Drive (Not synced)/`: 205 arquivos
- `ACIRV/`: 200 arquivos
- `reports/`: 17 arquivos
- `logs/`: 9 arquivos
- `scripts/`: 9 arquivos

## Fronteiras de sub-vault detectadas
- `C:\Users\Kevyn Lucas\Documents\Codex Kevyn\.obsidian`
- `C:\Users\Kevyn Lucas\Documents\Codex Kevyn\Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\.obsidian`
- `C:\Users\Kevyn Lucas\Documents\Codex Kevyn\HOME\Kevyn Lucas\.obsidian`
- `C:\Users\Kevyn Lucas\Documents\Codex Kevyn\HOME\Neuron\Neuron Obsidian\.obsidian`
- `C:\Users\Kevyn Lucas\Documents\Codex Kevyn\HOME\O Professor\00_Aleatórios\Cérebro Atômico\.obsidian`
- `C:\Users\Kevyn Lucas\Documents\Codex Kevyn\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\.obsidian`
- `C:\Users\Kevyn Lucas\Documents\Codex Kevyn\HOME\Ágora\Ágora Obsidian\.obsidian`

## Sinais iniciais de risco
- `Google Drive (Not synced)/` é uma zona sensível óbvia de espelho/importação e deve ser tratada como área prioritária de quarentena lógica antes de qualquer refactor em lote.
- Existem múltiplas pastas `.trash/` dentro de espelhos/importações no Google Drive.
- Há muitos arquivos com nome genérico `Untitled*` e `Sem título*`, concentrados principalmente em `.trash/`, além de alguns fora dela.
- O repositório possui alterações anteriores não relacionadas em `.obsidian/`, `reports/`, `logs/` e `scripts/`; qualquer nova tarefa deve trabalhar sem reverter esse estado.

## Ajustes mínimos necessários
- Corrigir a codificação de `AGENTS.md` e `.agents/skills/obsidian-vault-ops/SKILL.md` para texto legível.
- Nenhum ajuste semântico adicional em `AGENTS.md` se mostrou necessário neste baseline; as guardrails já estão adequadas para a próxima etapa de inventário/auditoria.

## Arquivos afetados
- `AGENTS.md`
- `.agents/skills/obsidian-vault-ops/SKILL.md`
- `reports/00-baseline.md`
- `logs/00-baseline.md`

## Riscos
- Os números acima incluem arquivos operacionais e possivelmente parte de estruturas espelhadas/importadas; não devem ser lidos ainda como inventário curado.
- Há sub-vaults internos e espelhos aparentes; mover ou renomear em lote sem segmentação por fronteira seria de alto risco.
- O estado Git atual já contém modificações prévias, então qualquer checkpoint deve ser feito com revisão de diff.

## Próximos passos
- Executar inventário estruturado por fronteira de sub-vault e por área sensível.
- Produzir manifesto específico de quarentena lógica para espelhos/importações, sem mover arquivos ainda.
- Em seguida, avançar para duplicatas exatas e somente depois near-duplicates.
