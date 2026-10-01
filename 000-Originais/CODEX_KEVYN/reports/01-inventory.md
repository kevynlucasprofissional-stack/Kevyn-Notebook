# Inventory 01

- Gerado em: 2026-04-04T11:33:34.263299-03:00
- Objetivo: Auditar o vault sem alterar conteudo semantico, com inventario estrutural e triagem inicial de risco.

## Método

- Varredura recursiva excluindo areas operacionais do proprio fluxo de auditoria.
- Contagem de arquivos por pasta e por extensao a partir do filesystem atual.
- Identificacao de sub-vaults por presenca de `.obsidian`, de diretorios `.trash`, de nomes genericos e de areas espelho/import por heuristica de caminho.
- Resolucao heuristica de links internos por wikilink e Markdown link para estimar links nao resolvidos e notas possivelmente orfas.

## Critérios

- Nenhum arquivo foi movido, renomeado ou apagado.
- Notas sem backlinks, sem links de saida ou sem conexoes sao tratadas como triagem, nao como verdade semantica.
- Sub-vaults sao detectados por presenca de `.obsidian`.

## Arquivos afetados

- `reports/01-inventory.json`
- `reports/01-inventory.md`
- `logs/01-inventory.md`

## Riscos

- Backlinks, orfandade e links quebrados dependem de resolucao heuristica e podem conter falsos positivos.
- Areas espelho/import sao inferidas por nome de caminho.

## Próximos passos

- Usar o JSON para revisar por area os pontos com maior volume antes de qualquer acao mecanica.
- Executar auditorias especificas de duplicatas e links so depois de validar as fronteiras de sub-vault e espelho/import.

## Resumo

- Arquivos auditados: 3649
- Notas Markdown: 3574
- Sub-vaults detectados: 7
- Diretorios `.trash`: 5
- Arquivos com nome generico: 65
- Areas espelho/import: 4
- Notas sem link de saida: 2301
- Notas sem backlinks: 1447
- Notas possivelmente orfas: 1124
- Links nao resolvidos: 3926

## Top Pastas

- `HOME\Segundo Cérebro`: 716 arquivos, 715 markdown
- `HOME\Segundo Cérebro\SC`: 715 arquivos, 715 markdown
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas`: 298 arquivos, 298 markdown
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico`: 182 arquivos, 182 markdown
- `HOME\Cérebro Profissional\Notas`: 155 arquivos, 153 markdown
- `ACIRV\Notas`: 127 arquivos, 127 markdown
- `HOME\ACIRV\Notas`: 106 arquivos, 106 markdown
- `HOME\O Professor\02_EGO - O MAGUS\A guerra da arte`: 86 arquivos, 85 markdown
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações`: 85 arquivos, 85 markdown
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta`: 65 arquivos, 65 markdown
- `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio`: 59 arquivos, 58 markdown
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\O Pequeno Príncipe`: 53 arquivos, 53 markdown
- `HOME\Kevyn Lucas\Outros\Integrados`: 49 arquivos, 49 markdown
- `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash`: 41 arquivos, 41 markdown
- `HOME\Clones\ECO - Contexto Completo`: 39 arquivos, 37 markdown
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash`: 35 arquivos, 34 markdown
- `HOME\Kevyn Lucas\Outros\Não integrados`: 35 arquivos, 35 markdown
- `HOME\Muad’Dib\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PARTE I - Técnicas fundamentais para lidar com as pessoas\temp`: 35 arquivos, 35 markdown
- `HOME\BioVision\Notas`: 26 arquivos, 25 markdown
- `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash`: 22 arquivos, 22 markdown

## Top Extensoes

- `.md`: 3574
- `.pdf`: 36
- `.png`: 21
- `.py`: 6
- `.canvas`: 5
- `.json`: 2
- `.txt`: 1
- `.base`: 1
- `.svg`: 1
- `.sheet`: 1
- `.psd`: 1

## Notas Possivelmente Orfas

- `ACIRV\Diário\2025\11 - novembro\18 - terça-feira.md`
- `ACIRV\Diário\2025\12 - dezembro\12 - sexta-feira.md`
- `ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md`
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
- `ACIRV\Notas\12 possíveis indicações para o Núcleo de Esporte e Cultura.md`
- `ACIRV\Notas\181125 - Roteiro Minuto ACIRV.md`
- `ACIRV\Notas\250226 - ROTEIRO DE CERIMONIAL CAFÉ ENTRE AMIGOS - Reforma tributária.md`
- `ACIRV\Notas\251125 - Minuto ACIRV sobre o Conecta Saúde.md`
- `ACIRV\Notas\300126 - Pedido do Raphael.md`
- `ACIRV\Notas\A Única Coisa que você tem que fazer agora é.md`
- `ACIRV\Notas\Acessos site.md`
- `ACIRV\Notas\Ajustes site.md`
- `ACIRV\Notas\CERIMONIAL - Café entre amigos 27.11.md`
- `ACIRV\Notas\Como criar o novo backdrop.md`
- `ACIRV\Notas\Como melhorar o manual de cerimonial.md`
- `ACIRV\Notas\Como melhorar o novo tom de voz da ACIRV.md`
- `ACIRV\Notas\Como melhorar o relatório mensal.md`
- `ACIRV\Notas\Como é realizado a reunião de apresentação de Métricas de todo dia 30 - Modelo da Vivi.md`

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
- `ACIRV\Notas\(1º Conecta de 2026) Planejamento.md`
- `ACIRV\Notas\(Desatualizado) Padrão de qualidade do novo tom de voz.md`
- `ACIRV\Notas\(MÉTRICAS) - 2025.md`
- `ACIRV\Notas\(PLANEJAMENTO ANUAL) CONECTA ACIRV 2026.md`
- `ACIRV\Notas\(RELATÓRIO MÉTRICAS PARA DIRETORIA) - Janeiro.md`

## Arquivos com Nome Ruim

- `ACIRV\Notas\00_rascunho.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\novo.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 12.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 15.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 16.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 17.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 2.canvas`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 25.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 31.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 34.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 37.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 39.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 40.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 41.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 42.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 43.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 46.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 47.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 48.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título 50.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Sem título.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Untitled 1.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Untitled.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\Notas\Sem título.md`
- `Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS\Sem título.md`
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\novo.md`
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 12.md`
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 15.md`
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 16.md`
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash\Sem título 17.md`

## Sub-vaults Detectados

- `.`
- `HOME\Kevyn Lucas`
- `HOME\Ágora\Ágora Obsidian`
- `HOME\Neuron\Neuron Obsidian`
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico`
- `HOME\SaaS com Kelvyn\TPM\TPM Obsidian`
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian`

## Diretorios Trash

- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash`: 35 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\Cérebro Profissional\.trash\Transcrição da reunião de Análise do Lançamento Semente - Ocorrida no dia 22\09`: 1 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash`: 18 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\Nova Acrópole\.trash`: 22 arquivos
- `Google Drive (Not synced)\Meu Drive\HOME\Segundo Cérebro\.trash`: 41 arquivos

## Areas Espelho/Import

- `HOME\Clones`: 232 arquivos
- `Google Drive (Not synced)`: 201 arquivos
- `HOME\SaaS com Kelvyn\TPM\Arquivos`: 6 arquivos
- `HOME\Neuron\ARQUIVOS`: 5 arquivos

## Links Nao Resolvidos

- `ACIRV\Notas\(1º Conecta de 2026) Planejamento.md` -> `https://docs.google.com/document/d/1ramwGS6Cjpe7ghisLo4_smumlOzx7cXK/edit` (markdown)
- `ACIRV\Notas\A fazer.md` -> `https://www.instagram.com/p/DV1sUYlCQP9/?img_index=1&igsh=OXg5enQzeHQ0MTBv` (markdown)
- `ACIRV\Notas\BRIEFING COMPLETO – PASTA ENVELOPE INSTITUCIONAL ACIRV.md` -> `http://www.acirv.com.br` (markdown)
- `ACIRV\Notas\BRIEFING COMPLETO – PASTA ENVELOPE INSTITUCIONAL ACIRV.md` -> `mailto:acirv@acirv.com.br` (markdown)
- `ACIRV\Notas\Conteúdos que precisam se repetir em 2026.md` -> `https://drive.google.com/file/d/1S5aZsX6LkI5T4XQ7QvRgEgV8ed9030PP/view?usp=sharing` (markdown)
- `ACIRV\Notas\Conteúdos que precisam se repetir em 2026.md` -> `https://www.calendarr.com/brasil/dia-da-gratidao/` (markdown)
- `ACIRV\Notas\Conteúdos que precisam se repetir em 2026.md` -> `https://www.calendarr.com/brasil/dia-nacional-gracas-a-deus-e-segunda-feira/` (markdown)
- `ACIRV\Notas\DADOS SOBRE LOCAÇÃO DE AUDITÓRIO.md` -> `https://www.instagram.com/explore/tags/acirv/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/acirvoficial/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/diegomodolo/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/acirv/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/acirv/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/acirv/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/acirve/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/acirveventos/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/acirveventos/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/desenvolvimento/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/eventoscorporativos/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/experi%C3%AAnciaplaza/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/f%C3%B3rumdeia/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/f%C3%B3rumdeiadaacirv/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/f%C3%B3rumia/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/forumdeia/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/gest%C3%A3oempresarial/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/gratid%C3%A3o/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/hubgoi%C3%A1s/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/ia/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/inova%C3%A7%C3%A3o/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/inova%C3%A7%C3%A3o/` (markdown)
- `ACIRV\Notas\Dados sobre o Fórum.md` -> `https://www.instagram.com/explore/tags/inova%C3%A7ao/` (markdown)
