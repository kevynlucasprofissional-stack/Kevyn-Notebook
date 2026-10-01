# 02 Classification

## Objetivo
Classificar o vault inteiro nas classes `core`, `archive`, `mirror`, `noise` e `boundary` com base no baseline e nas auditorias j? existentes, sem mover nenhum item.

## M?todo
- Reuso do baseline e dos relat?rios 02-inventory, 02-quarantine-candidates, 03-exact-dedupe, 04-near-dedupe e 05-navigation-plan.
- Aplica??o de regras por preced?ncia: boundary > noise > mirror > archive > core.
- Classifica??o por escopos de pasta e overrides de arquivo de baixo risco j? detectados na quarentena l?gica.
- Contagem final calculada sobre todos os arquivos do workspace, com subtotal separado para o vault+opera??es sem `.git` e `.venv`.

## Crit?rios
- core = conhecimento vivo, operacional ou estruturalmente central.
- archive = ?til, mas pouco ativo.
- mirror = espelho, import ou c?pia externa/interna redundante.
- noise = lixo, rascunho vazio, nome gen?rico ou res?duo t?cnico.
- boundary = sub-vault ou ?rea que exige tratamento separado.
- Nenhum arquivo foi movido, apagado ou renomeado nesta rodada.

## Resumo
- Arquivos no workspace considerado: 7793
- Markdown no workspace considerado: 4310
- Subtotal vault+opera??es sem `.git` e `.venv`: 4453 arquivos / 4308 markdown
- Refer?ncia do invent?rio 02: 4132 arquivos / 3576 markdown
- Sub-vaults detectados: 7
- Grupos de duplicata exata usados como evid?ncia: 944
- Arquivos em duplicatas exatas: 2169
- Clusters near-duplicate usados como evid?ncia: 368

### Contagem por classe no vault+opera??es
- `core`: 1917 arquivos (1872 markdown)
- `archive`: 866 arquivos (834 markdown)
- `mirror`: 1096 arquivos (1082 markdown)
- `noise`: 160 arquivos (156 markdown)
- `boundary`: 414 arquivos (364 markdown)

### Contagem por classe no workspace completo
- `core`: 4774 arquivos (1872 markdown)
- `archive`: 866 arquivos (834 markdown)
- `mirror`: 1096 arquivos (1082 markdown)
- `noise`: 643 arquivos (158 markdown)
- `boundary`: 414 arquivos (364 markdown)

## Leitura da Taxonomia
- `core` = Conhecimento vivo, operacional ou estruturalmente central para o vault e sua manuten??o.
- `archive` = Conte?do ?til, por?m menos ativo ou perif?rico ao n?cleo operacional atual.
- `mirror` = Espelho, import ou c?pia externa/interna redundante frente a uma ?rea preferencial.
- `noise` = Lixo, rascunho vazio, res?duo t?cnico ou conte?do explicitamente descartado.
- `boundary` = Sub-vault ou ?rea que exige tratamento separado.

## Escopos Classificados
### Core
- `.agents` (folder, 1 arquivos, confian?a high): Infraestrutura de skill local e suporte operacional do vault.
- `.git` (folder, 2857 arquivos, confian?a high): Checkpoint obrigat?rio do fluxo seguro definido em AGENTS.md.
- `AGENTS.md` (file, 1 arquivos, confian?a high): Contrato operacional central para qualquer interven??o no vault.
- `HOME\ACIRV` (folder, 175 arquivos, confian?a high): ?rea operacional viva destacada no plano de navega??o e preferida frente a ACIRV.
- `HOME\Cérebro Profissional` (folder, 175 arquivos, confian?a high): Plano de navega??o a identifica como ?rea de alto valor, IA, opera??es e projetos.
- `HOME\Muad’Dib` (folder, 45 arquivos, confian?a medium): ?rea ativa de trabalho conceitual/operacional fora das zonas de mirror conhecidas.
- `HOME\O Professor` (folder, 857 arquivos, confian?a high): Maior polo conceitual vivo do vault, com notas centrais destacadas no plano de navega??o.
- `HOME\SaaS com Kelvyn` (folder, 35 arquivos, confian?a medium): ?rea de projeto ativa, embora parte do conte?do exija separa??o por sub-vault e arquivos auxiliares.
- `logs` (folder, 24 arquivos, confian?a high): Changelog obrigat?rio para qualquer tarefa em lote.
- `reports` (folder, 42 arquivos, confian?a high): Sa?da humana prim?ria das auditorias do vault.
- `scripts` (folder, 15 arquivos, confian?a high): Ferramental de auditoria e corre??es mec?nicas seguras.
- `templates` (folder, 8 arquivos, confian?a medium): Suporte estrutural para padroniza??o futura e navegabilidade.
- `_archive_review` (folder, 249 arquivos, confian?a high): Zona operacional definida em AGENTS.md para revis?o segura de material deslocado.
- `_merge_candidates` (folder, 664 arquivos, confian?a high): Zona operacional de staging para consolida??es revis?veis.
- `_staging` (folder, 6 arquivos, confian?a high): Zona operacional de manifestos e prepara??o revers?vel.

### Archive
- `HOME\AULAS FGV - FUNDAÇÃO GETÚLIO VARGAS` (folder, 20 arquivos, confian?a medium): Cole??o ?til e delimitada por curso, com baixa centralidade operacional atual.
- `HOME\BioVision` (folder, 29 arquivos, confian?a medium): ?rea tem?tica pequena e ?til, mas sem sinais de centralidade estrutural no baseline.
- `HOME\Cérebro Criador` (folder, 17 arquivos, confian?a medium): Conhecimento reaproveit?vel, por?m menos central que C?rebro Profissional e O Professor.
- `HOME\Gestão de Tempo` (folder, 2 arquivos, confian?a medium): Conjunto pequeno e ?til, sem sinais de uso operacional intenso.
- `HOME\Kevyn Lucas\Outros\Arquivados` (folder, 5 arquivos, confian?a high): Sub?rea explicitamente arquivada dentro do sub-vault pessoal.
- `HOME\Neuron\ARQUIVOS` (folder, 4 arquivos, confian?a medium): Dep?sito auxiliar de arquivos, ?til mas fora do n?cleo vivo de notas.
- `HOME\Nova Acrópole` (folder, 13 arquivos, confian?a medium): Cole??o tem?tica ?til e relativamente est?vel, com baixa centralidade atual.
- `HOME\Obsidian doc` (folder, 38 arquivos, confian?a medium): Refer?ncia ?til/documental, por?m perif?rica ao trabalho operacional atual.
- `HOME\ReValor` (folder, 3 arquivos, confian?a medium): Projeto pequeno e ?til, mas sem sinais de centralidade operacional no baseline.
- `HOME\SaaS com Kelvyn\ANTECIPA` (folder, 4 arquivos, confian?a medium): Sub?rea pequena, ?til, mas sem evid?ncia de atividade estrutural forte.
- `HOME\SaaS com Kelvyn\TPM\Arquivos` (folder, 5 arquivos, confian?a medium): Dep?sito auxiliar de arquivos, fora do fluxo principal de notas.
- `HOME\Segundo Cérebro` (folder, 1431 arquivos, confian?a high): Base de conhecimento extensa e ?til, mas hoje cercada por duplica??o interna e menor centralidade operacional.
- `HOME\Solara` (folder, 2 arquivos, confian?a medium): Projeto pequeno e ?til, sem sinais de atividade estrutural dominante.
- `HOME\Ágora\Documentos` (folder, 5 arquivos, confian?a medium): Documentos auxiliares fora do n?cleo de notas do sub-vault.

### Mirror
- `ACIRV` (folder, 203 arquivos, confian?a high): Duplicatas exatas e near-duplicates fortes apontam HOME\ACIRV como c?pia operacional preferencial.
- `Google Drive (Not synced)` (folder, 18 arquivos, confian?a high): Baseline e quarentena j? marcaram a ?rea como espelho/import sens?vel.
- `HOME\Clones` (folder, 183 arquivos, confian?a high): Pasta explicitamente rotulada como clones e j? listada na quarentena l?gica.
- `HOME\Segundo Cérebro\SC` (folder, 706 arquivos, confian?a high): Duplicatas exatas em massa mostram SC como espelho interno do pr?prio Segundo C?rebro.

### Noise
- `.venv` (folder, 483 arquivos, confian?a high): Res?duo t?cnico local, n?o faz parte do conhecimento do vault.
- `HOME\Muad’Dib\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PARTE I - Técnicas fundamentais para lidar com as pessoas\temp` (folder, 35 arquivos, confian?a high): Subpasta tempor?ria/residual dentro de uma ?rea de conhecimento viva.
- `scripts\__pycache__` (folder, 3 arquivos, confian?a high): Cache transit?rio do Python.

### Boundary
- `.obsidian` (folder, 5 arquivos, confian?a high): Configura??o do vault raiz; exige tratamento separado de conte?do.
- `HOME\Kevyn Lucas` (folder, 111 arquivos, confian?a high): Sub-vault pr?prio com .obsidian; requer tratamento separado por sensibilidade pessoal.
- `HOME\Neuron\Neuron Obsidian` (folder, 22 arquivos, confian?a high): Sub-vault detectado pelo invent?rio; deve ser tratado em trilha pr?pria.
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico` (folder, 191 arquivos, confian?a high): Sub-vault aninhado em ?rea sens?vel e de alta densidade conceitual.
- `HOME\SaaS com Kelvyn\TPM\TPM Obsidian` (folder, 25 arquivos, confian?a high): Sub-vault detectado; deve ser operado isoladamente.
- `HOME\Ágora\Ágora Obsidian` (folder, 47 arquivos, confian?a high): Sub-vault detectado; tratamento precisa ser separado.
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian` (folder, 13 arquivos, confian?a high): Sub-vault aninhado dentro do espelho do Google Drive; requer trilha pr?pria.

## ?reas Mistas
- `HOME`: Agrupa ?reas core, archive, mirror e boundary; a classifica??o v?lida precisa acontecer por sub?rvore.
  - HOME\Cérebro Profissional -> core
  - HOME\Segundo Cérebro -> archive
  - HOME\Clones -> mirror
  - HOME\Kevyn Lucas -> boundary
- `HOME\SaaS com Kelvyn`: A raiz ? operacional, mas cont?m sub-vault e dep?sitos auxiliares.
  - HOME\SaaS com Kelvyn -> core
  - HOME\SaaS com Kelvyn\TPM\TPM Obsidian -> boundary
  - HOME\SaaS com Kelvyn\TPM\Arquivos -> archive
- `HOME\Ágora`: Mistura sub-vault de notas e documentos auxiliares.
  - HOME\Ágora\Ágora Obsidian -> boundary
  - HOME\Ágora\Documentos -> archive
- `HOME\Neuron`: Mistura sub-vault e pasta auxiliar de arquivos.
  - HOME\Neuron\Neuron Obsidian -> boundary
  - HOME\Neuron\ARQUIVOS -> archive

## Arquivos Afetados
- `reports/02-classification.md`
- `reports/02-classification.json`
- `_staging/manifests/classification-manifest.json`
- `logs/02-classification.md`

## Riscos
- A classifica??o ? estrutural e heur?stica; n?o substitui revis?o humana de conte?do sens?vel.
- Sub-vaults foram isolados por boundary, ent?o a classe n?o implica a??o dentro deles.
- Algumas ?reas pequenas sem hist?rico forte foram classificadas como archive por baixa centralidade observ?vel, n?o por obsolesc?ncia confirmada.
- Os totais do workspace incluem infraestrutura operacional local; por isso o relat?rio tamb?m separa o subtotal sem `.git` e `.venv`.

## Pr?ximos Passos
- Usar o manifesto para revisar primeiro as zonas mirror e noise de menor risco.
- Separar futuras a??es por fronteira boundary, sem batch refactor cruzando sub-vaults.
- Se aprovado, derivar manifestos de navega??o e quarentena a partir desta taxonomia.

## Evid?ncias Principais
- `Google Drive (Not synced)` e `HOME/Clones` j? tinham marca??o pr?via de espelho/import no baseline e na quarentena l?gica.
- `ACIRV` versus `HOME/ACIRV`, al?m de `HOME/Segundo C?rebro` versus `HOME/Segundo C?rebro/SC`, aparecem repetidamente em duplicatas exatas e near-duplicates.
- `HOME/C?rebro Profissional`, `HOME/O Professor` e `HOME/ACIRV` aparecem como ?reas de maior valor no plano de navega??o.
- Todas as ra?zes com `.obsidian/` foram tratadas como `boundary` por regra de seguran?a.
