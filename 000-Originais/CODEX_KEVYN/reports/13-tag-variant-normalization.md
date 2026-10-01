# Tag Variant Normalization 13

- Gerado em: 2026-04-04T17:36:11.437667-03:00
- Objetivo: Normalizar variantes mecanicas de tags detectadas no audit 11, com comparacao sobre o frontmatter bruto e sem alterar o corpo das notas.

## Método

- Varredura de Markdown fora de sub-vaults aninhados.
- Leitura do frontmatter bruto para distinguir variante real de valor ja canonico.
- Normalizacao mecanica por caixa, acentos, hifen/underscore e separadores hierarquicos.
- Remocao de singleton tags apenas em areas de baixo valor.

## Critérios

- Corpo das notas preservado.
- Nenhum link novo criado.
- Nenhum arquivo movido.
- Somente variantes mecanicas e singleton tags em areas de baixo valor foram escritas.

## Arquivos afetados

- `reports\13-tag-variant-normalization.json`
- `reports\13-tag-variant-normalization.md`
- `logs\13-tag-variant-normalization.md`
- `_staging\manifests\13-tag-variant-normalization.json`

## Riscos

- Tags com diferenca apenas acentual podem colidir na forma canonica.
- Frontmatter muito incomum pode permanecer sem alteracao se nao expuser tags/aliases de forma legivel.

## Próximos passos

- Revisar o manifesto reversivel antes de considerar propagacao de tags ou sugestoes de link.
- Se aprovado, uma rodada futura pode tratar alias e link suggestions em separacao.

## Resumo

- Notas consideradas: 1012
- Arquivos alterados: 998
- Singleton tags removidas: 0
- Tags antes: 3676
- Tags depois: 3676
- Aliases antes: 79
- Aliases depois: 79

## Arquivos Alterados

- `ACIRV\Diário\Diário.md`
- `ACIRV\MOC - ACIRV.md`
- `ACIRV\Notas\(1º Conecta de 2026) Planejamento.md`
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
- `ACIRV\Notas\300326 - Notas reunião com VCOM.md`
- `ACIRV\Notas\A fazer.md`
- `ACIRV\Notas\A Única Coisa que você tem que fazer agora é.md`
- `ACIRV\Notas\Acessos site.md`
- `ACIRV\Notas\Ajustes site.md`
- `ACIRV\Notas\Blocos de foco\170326 - Bloco de foco tipo operacional.md`
- `ACIRV\Notas\Blocos de foco\180326 - Bloco de foco tipo operacional.md`
- `ACIRV\Notas\BRIEFING COMPLETO – PASTA ENVELOPE INSTITUCIONAL ACIRV.md`
- `ACIRV\Notas\CERIMONIAL - Café entre amigos 27.11.md`
- `ACIRV\Notas\Como criar o novo backdrop.md`
- `ACIRV\Notas\Como melhorar o manual de cerimonial.md`
- `ACIRV\Notas\Como melhorar o novo tom de voz da ACIRV.md`
- `ACIRV\Notas\Como melhorar o relatório mensal.md`
- `ACIRV\Notas\como organizar o meu tempo.md`
- `ACIRV\Notas\Como é realizado a reunião de apresentação de Métricas de todo dia 30 - Modelo da Vivi.md`
- `ACIRV\Notas\CONECTA SAÚDE - Campanha de Guerra.md`
- `ACIRV\Notas\Contas e Senhas.md`
- `ACIRV\Notas\Conteúdos que precisam se repetir em 2026.md`
- `ACIRV\Notas\cronograma otimizado para o dia 110326.md`
- `ACIRV\Notas\Dados Corrida Corre MOPORV.md`
- `ACIRV\Notas\Dados SEMINÁRIO MULTICADORES DE SUCESSO - PARCEIROS DA PCGO (Edição ACIRV).md`
- `ACIRV\Notas\Dados sobre a CAM ACIRV.md`
- `ACIRV\Notas\DADOS sobre a inauguração da reestruturação e reforma da quarta companhia do batalhão de Polícia Militar Rural.md`
- `ACIRV\Notas\Dados sobre a vinda do Vanderlan ao Rio Verde no IF Goiano.md`
- `ACIRV\Notas\DADOS SOBRE LOCAÇÃO DE AUDITÓRIO.md`
- `ACIRV\Notas\Dados sobre o Conecta Saúde.md`
- `ACIRV\Notas\Dados sobre o Fórum.md`
- `ACIRV\Notas\Dados sobre o Happy Hour do dia da mulher da ACIRV.md`
- `ACIRV\Notas\Dados sobre o novo tom de voz e planejamento de 2026.md`
- `ACIRV\Notas\Dados sobre o workshop NR-01 na prática - 120226.md`
- `ACIRV\Notas\Dados solicitados pela Vivi.md`
- `ACIRV\Notas\Dados Sorriso Verdadeiro.md`
- `ACIRV\Notas\Dica sobre como construir criativos do Raphael Valongo.md`
- `ACIRV\Notas\Dicas do José Carlos.md`
- `ACIRV\Notas\ESPELHO OFICIAL - CONECTA 5º EDIÇÃO.md`
- `ACIRV\Notas\Fazendo o Lovable pensar estratégicamente.md`
- `ACIRV\Notas\Fórum de indústria da ACIRV.md`
- `ACIRV\Notas\GALPÃO DE TAREFAS.md`
- `ACIRV\Notas\GESTÃO DA ATENÇÃO - Café entre amigos 01.md`
- `ACIRV\Notas\Gestão de tempo.md`
- `ACIRV\Notas\Guia Estratégico para Gestão da Comunidade ACIRV.md`
- `ACIRV\Notas\Ideia de criativos.md`
- `ACIRV\Notas\Idéias de conteúdo.md`
- `ACIRV\Notas\Inicio do prompt para fazer o planejamento de janeiro.md`
- `ACIRV\Notas\JOBS - Picanha dos depoimentos do Fórum de IA.md`
- `ACIRV\Notas\José Carlos Cintra.md`
- `ACIRV\Notas\Kevyn vs. Renata - Uma Mudança.md`
- `ACIRV\Notas\Lista de associados em JSON.md`
- `ACIRV\Notas\Lista Presença 5º Edição CNPJ - Conecta Acirv - Mesa Networking.md`
- `ACIRV\Notas\Lovable\(Ideias) Lovable para a ACIRV.md`
- `ACIRV\Notas\Lovable\21st.dev com Lovable.md`
- `ACIRV\Notas\Lovable\API no Lovable.md`
- `ACIRV\Notas\Lovable\Como copiar qualquer site.md`
- `ACIRV\Notas\Lovable\Dashboard.md`
- `ACIRV\Notas\Lovable\Figma + Lovable.md`
- `ACIRV\Notas\Melhorando a IA redatora.md`

## Singletons Removidos

- Nenhum singleton removido.
