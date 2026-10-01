# 01 Baseline

- Gerado em: 2026-04-04T16:20:04.394546-03:00
- Objetivo: Estabelecer um baseline factual e reproduzivel do vault sem alterar o conteudo semantico das notas.

## Método

- Varredura recursiva do vault com exclusao apenas de diretorios operacionais do proprio fluxo de auditoria.
- Contagem de arquivos por pasta e por extensao a partir do estado atual do filesystem.
- Deteccao de sub-vaults pela presenca de `.obsidian/`, de diretorios `.trash/`, de nomes genericos e de areas espelho/import por heuristicas de caminho e nome.
- Analise heuristica de links internos em Markdown e wikilinks, com suporte basico a aliases de frontmatter quando presentes.

## Critérios

- Nenhuma nota foi movida, renomeada, reescrita ou apagada.
- Pastas com `.obsidian/` foram tratadas como fronteiras de sub-vault apenas para classificacao e risco.
- Backlinks e links quebrados foram calculados de forma heuristica e revisavel.

## Arquivos afetados

- `reports/01-baseline.json`
- `reports/01-baseline.md`
- `logs/01-baseline.md`
- `scripts/baseline_01.py`
- `scripts/run_baseline_01.ps1`

## Riscos

- Backlinks e links quebrados podem conter falsos positivos quando o vault depende de convencoes do Obsidian nao materializadas em links ou aliases.
- Areas espelho/import e copias aparentes sao classificadas por heuristica de caminho e nome, nao por validacao semantica.
- Os totais excluem diretorios operacionais da propria auditoria para manter reprodutibilidade do baseline.

## Próximos passos

- Usar o JSON para revisar primeiro as fronteiras de sub-vault e as areas espelho/import com maior volume.
- Separar eventuais falsos positivos de links quebrados antes de qualquer plano de correcao mecanica.
- Congelar este baseline em um checkpoint Git antes de avancar para quarentena logica, duplicatas e navegabilidade.

## Resumo

- Arquivos auditados: 3416
- Notas Markdown: 3350
- Diretorios auditados: 220
- Sub-vaults detectados: 7
- Diretorios `.trash`: 4
- Arquivos com nome generico: 8
- Areas espelho/import: 9
- Notas sem links de saida: 2071
- Notas sem backlinks: 1192
- Notas possivelmente orfas: 877
- Links nao resolvidos: 697

## Top Pastas

- `HOME\Segundo Cérebro`: 717 arquivos, 716 markdown
- `HOME\Segundo Cérebro\SC`: 706 arquivos, 706 markdown
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas`: 298 arquivos, 298 markdown
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico`: 182 arquivos, 182 markdown
- `HOME\Cérebro Profissional\Notas`: 154 arquivos, 152 markdown
- `ACIRV\Notas`: 129 arquivos, 129 markdown
- `HOME\ACIRV\Notas`: 106 arquivos, 106 markdown
- `HOME\O Professor\02_EGO - O MAGUS\A guerra da arte`: 86 arquivos, 85 markdown
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações`: 85 arquivos, 85 markdown
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta`: 65 arquivos, 65 markdown
- `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio`: 59 arquivos, 58 markdown
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\O Pequeno Príncipe`: 53 arquivos, 53 markdown
- `HOME\Kevyn Lucas\Outros\Integrados`: 49 arquivos, 49 markdown
- `HOME\Kevyn Lucas\Outros\Não integrados`: 35 arquivos, 35 markdown
- `HOME\Muad’Dib\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PARTE I - Técnicas fundamentais para lidar com as pessoas\temp`: 35 arquivos, 35 markdown
- `HOME\BioVision\Notas`: 26 arquivos, 25 markdown
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações`: 21 arquivos, 21 markdown
- `HOME\ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações`: 21 arquivos, 21 markdown
- `HOME\Obsidian doc\tudo em um lugar`: 21 arquivos, 20 markdown
- `HOME\Ágora\Ágora Obsidian`: 19 arquivos, 16 markdown
- `HOME\Neuron\Neuron Obsidian`: 18 arquivos, 13 markdown
- `HOME\SaaS com Kelvyn\TPM\TPM Obsidian`: 18 arquivos, 13 markdown
- `HOME\Cérebro Criador\Notas`: 16 arquivos, 16 markdown
- `HOME\Clones\_ECO`: 14 arquivos, 14 markdown
- `HOME\Clones\_ECO\ECO V3\input_data\kotler`: 14 arquivos, 3 markdown

## Top Extensoes

- `.md`: 3350
- `.pdf`: 34
- `.png`: 21
- `.canvas`: 4
- `.json`: 2
- `.txt`: 1
- `.base`: 1
- `.svg`: 1
- `.sheet`: 1
- `.psd`: 1

## Sub-vaults Detectados

- `.`
- `HOME\Kevyn Lucas`
- `HOME\Neuron\Neuron Obsidian`
- `HOME\Ágora\Ágora Obsidian`
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico`
- `HOME\SaaS com Kelvyn\TPM\TPM Obsidian`
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian`

## Diretorios Trash

- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash`: 0 arquivos descendentes
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash`: 0 arquivos descendentes
- `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash`: 0 arquivos descendentes
- `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash`: 0 arquivos descendentes

## Areas Espelho ou Import

- `HOME\Clones`: 183 arquivos, motivos ["keyword-boundary", "mirror-like-directory-name"]
- `HOME\ACIRV`: 175 arquivos, motivos ["nested-name-matches-top-level:ACIRV"]
- `Google Drive (Not synced)`: 14 arquivos, motivos ["keyword-boundary", "mirror-like-directory-name"]
- `Google Drive (Not synced)\Meu Drive\HOME`: 11 arquivos, motivos ["nested-name-matches-top-level:HOME"]
- `HOME\SaaS com Kelvyn\TPM\Arquivos`: 5 arquivos, motivos ["keyword-boundary"]
- `HOME\Neuron\ARQUIVOS`: 4 arquivos, motivos ["keyword-boundary"]
- `Google Drive (Not synced)\Meu Drive\ACIRV`: 3 arquivos, motivos ["nested-name-matches-top-level:ACIRV"]
- `Google Drive (Not synced)\Meu Drive\HOME\ACIRV`: 0 arquivos, motivos ["nested-name-matches-top-level:ACIRV"]
- `Google Drive (Not synced)\Meu Drive\HOME\Clones`: 0 arquivos, motivos ["mirror-like-directory-name"]

## Nomes Genericos

- `ACIRV\Notas\00_rascunho.md`
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\00_rascunho.md`
- `HOME\ACIRV\Notas\00_rascunho.md`
- `HOME\BioVision\Notas\00_rascunho.md`
- `HOME\Clones\_Rascunho\Rascunho.md`
- `HOME\Gestão de Tempo\Untitled.sheet`
- `HOME\Kevyn Lucas\Outros\Não integrados\00_rascunho.md`
- `HOME\Ágora\Ágora Obsidian\00_rascunho.md`

## Notas Sem Links de Saida

- `ACIRV\Diário\2025\11 - novembro\18 - terça-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\12 - sexta-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md`
- `ACIRV\Diário\Diário.md`
- `ACIRV\Notas\(Desatualizado) Padrão de qualidade do novo tom de voz.md`
- `ACIRV\Notas\(MÉTRICAS) - 2025.md`
- `ACIRV\Notas\(PLANEJAMENTO ANUAL) CONECTA ACIRV 2026.md`
- `ACIRV\Notas\(RELATÓRIO MÉTRICAS PARA DIRETORIA) - Janeiro.md`
- `ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Fevereiro.md`
- `ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Janeiro.md`
- `ACIRV\Notas\(RELATÓRIO MÉTRICAS) - Março.md`
- `ACIRV\Notas\(RELEASE) Seminário Multiplicadores de Sucesso.md`
- `ACIRV\Notas\00_rascunho.md`
- `ACIRV\Notas\0304261451 - Ajustes 03 do SaaS.md`
- `ACIRV\Notas\050126 - Carta a Vivi.md`
- `ACIRV\Notas\050226 - Reunião sobre a SudoExpo.md`
- `ACIRV\Notas\100226 - Gustavo Lacerda visita IF Goiano.md`
- `ACIRV\Notas\110326 - diagnóstico da atual gestão do tempo.md`
- `ACIRV\Notas\110326 - Insight completo sobre como estou usando meu tempo.md`
- `ACIRV\Notas\12 possíveis indicações para o Núcleo de Esporte e Cultura.md`
- `ACIRV\Notas\181125 - Roteiro Minuto ACIRV.md`
- `ACIRV\Notas\1º Fórum de IA da ACIRV - Planejamento Social Media.md`
- `ACIRV\Notas\250226 - ROTEIRO DE CERIMONIAL CAFÉ ENTRE AMIGOS - Reforma tributária.md`
- `ACIRV\Notas\251125 - Minuto ACIRV sobre o Conecta Saúde.md`
- `ACIRV\Notas\300126 - Pedido do Raphael.md`

## Notas Sem Backlinks

- `ACIRV\Diário\2025\11 - novembro\14 - sexta-feira.md`
- `ACIRV\Diário\2025\11 - novembro\17 - segunda-feira.md`
- `ACIRV\Diário\2025\11 - novembro\18 - terça-feira.md`
- `ACIRV\Diário\2025\11 - novembro\19 - quarta-feira.md`
- `ACIRV\Diário\2025\11 - novembro\24 - segunda-feira.md`
- `ACIRV\Diário\2025\11 - novembro\25 - terça-feira.md`
- `ACIRV\Diário\2025\11 - novembro\27 - quinta-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\01 - segunda-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\02 - terça-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\03 - quarta-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\04 - quinta-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\05 - sexta-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\08 - segunda-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\09 - terça-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\10 - quarta-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\12 - sexta-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\29 - segunda-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\07 - quarta-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\08 - quinta-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\13 - terça-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\15 - quinta-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\16 - sexta-feira.md`
- `ACIRV\Diário\2026\02 - fevereiro\18 - quarta-feira.md`
- `ACIRV\Diário\2026\03 - março\05 - quinta-feira.md`

## Links Nao Resolvidos

- `HOME\Cérebro Profissional\Notas\Notas de uma conversa com o Copilot, não lembro o dia..md` -> `$100M Branding Playbook_PT-BR` (wikilink)
- `HOME\Cérebro Profissional\Notas\Notas de uma conversa com o Copilot, não lembro o dia..md` -> `$100M Branding Playbook_PT-BR` (wikilink)
- `HOME\Cérebro Profissional\Notas\Notas de uma conversa com o Copilot, não lembro o dia..md` -> `$100M Goated Ads Playbook_PT-BR` (wikilink)
- `HOME\Cérebro Profissional\Notas\Notas de uma conversa com o Copilot, não lembro o dia..md` -> `$100M Goated Ads Playbook_PT-BR` (wikilink)
- `HOME\Cérebro Profissional\Notas\Notas de uma conversa com o Copilot, não lembro o dia..md` -> `$100M Marketing Machine_PT-BR` (wikilink)
- `HOME\Cérebro Profissional\Notas\Notas de uma conversa com o Copilot, não lembro o dia..md` -> `$100M Marketing Machine_PT-BR` (wikilink)
- `HOME\Cérebro Profissional\Notas\O ebook é uma isca.md` -> `O segredo da mentalidade magra` (wikilink)
- `HOME\Cérebro Profissional\Notas\O ebook é uma isca.md` -> `O segredo da mentalidade magra` (wikilink)
- `HOME\Cérebro Profissional\Notas\Workshop com Alan Nicolas.md` -> `Pasted Image 20250826202725_931.png` (wikilink)
- `HOME\Cérebro Profissional\Notas\Workshop com Alan Nicolas.md` -> `Pasted Image 20250828195454_871.png` (wikilink)
- `HOME\Kevyn Lucas\Kevyn Lucas - Contexto completo.md` -> `Adunaico` (wikilink)
- `HOME\Kevyn Lucas\Kevyn Lucas - Contexto completo.md` -> `Anéis de Poder` (wikilink)
- `HOME\Kevyn Lucas\Kevyn Lucas - Contexto completo.md` -> `Aragorn` (wikilink)
- `HOME\Kevyn Lucas\Kevyn Lucas - Contexto completo.md` -> `Numenor` (wikilink)
- `HOME\Kevyn Lucas\Kevyn Lucas - Contexto completo.md` -> `Projeto de Transformação da Psique` (wikilink)
- `HOME\Kevyn Lucas\Kevyn Lucas - Contexto extra.md` -> `Adunaico` (wikilink)
- `HOME\Kevyn Lucas\Kevyn Lucas - Contexto extra.md` -> `Anéis de Poder` (wikilink)
- `HOME\Kevyn Lucas\Kevyn Lucas - Contexto extra.md` -> `Aragorn` (wikilink)
- `HOME\Kevyn Lucas\Kevyn Lucas - Contexto extra.md` -> `Numenor` (wikilink)
- `HOME\Kevyn Lucas\Kevyn Lucas - Contexto extra.md` -> `Projeto de Transformação da Psique` (wikilink)
- `HOME\Kevyn Lucas\Outros\Integrados\Sobre a simbiose romântica, minhas tribos e a Odisséia psicológica.md` -> `Adunaico` (wikilink)
- `HOME\Kevyn Lucas\Outros\Integrados\Sobre a simbiose romântica, minhas tribos e a Odisséia psicológica.md` -> `Anéis de Poder` (wikilink)
- `HOME\Kevyn Lucas\Outros\Integrados\Sobre a simbiose romântica, minhas tribos e a Odisséia psicológica.md` -> `Aragorn` (wikilink)
- `HOME\Kevyn Lucas\Outros\Integrados\Sobre a simbiose romântica, minhas tribos e a Odisséia psicológica.md` -> `Numenor` (wikilink)
- `HOME\Kevyn Lucas\Outros\Visão Geral\Passo 01 - Cronologia e fatos.md` -> `03 - quinta-feira.md` (wikilink)
