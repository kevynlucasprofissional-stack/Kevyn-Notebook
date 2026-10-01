# Audit Metadata Network 11

- Gerado em: 2026-04-04T17:26:50.213145-03:00
- Objetivo: Executar uma auditoria unificada e leve de metadados e rede de links para preparar normalizacao com o menor numero possivel de prompts.

## Método

- Uma unica varredura leu cada nota Markdown apenas uma vez e reutilizou indexes em memoria para links e metadados.
- Frontmatter foi parseado de forma conservadora para identificar tags, aliases e propriedades fora do padrao sem reescrever notas.
- Links foram resolvidos com a mesma heuristica ja usada nas auditorias anteriores, mas sem acionar novas leituras do vault.
- Sugestoes de tags e links foram limitadas a sinais de alta confianca e a areas nao bloqueadas.

## Critérios

- Nenhum arquivo foi movido, renomeado, apagado ou reescrito.
- Boundary, HOME/Kevyn Lucas, diarios, dossies longos e zonas espelho/protegidas foram tratadas como bloqueadas para sugestoes.
- As saidas revisaveis foram registradas em reports/, logs/ e _staging/manifests/.

## Arquivos afetados

- `reports/11-audit-metadata-network.json`
- `reports/11-audit-metadata-network.md`
- `logs/11-audit-metadata-network.md`
- `_staging/manifests/11-tag-normalization-candidates.json`
- `_staging/manifests/11-tag-propagation-candidates.json`
- `_staging/manifests/11-link-suggestion-candidates.json`

## Riscos

- Propriedades YAML complexas podem escapar do parser conservador e aparecer como avisos de frontmatter.
- Sugestoes de link e propagacao continuam heuristicas, ainda que filtradas por alta confianca.
- Areas protegidas e boundary foram excluidas das sugestoes, entao a cobertura semantica pode parecer inferior ao real nessas subarvores.

## Próximos passos

- Revisar os manifestos para decidir a rodada de normalizacao mecanica minima.
- Se desejar, converter apenas os casos deterministicos em um plano de edicao separado.
- Reusar os candidatos de alta confianca para calibrar alias, tags e backlinks antes de qualquer escrita.

## Resumo

- Arquivos auditados: 3419
- Notas Markdown: 3352
- Sub-vaults detectados: 7
- Notas em boundary: 364
- Notas protegidas: 215
- Notas bloqueadas para sugestoes: 684
- Tags distintas: 1197
- Tags singleton: 85
- Aliases totais: 74
- Aliases duplicados: 0
- Links quebrados: 684
- Alvos nao resolvidos distintos: 422
- Candidatos a propagacao de tags: 26
- Candidatos a link sugerido: 1190
- Hubs/MOCs detectados: 86

## Deterministico vs Heuristico

- Contagens diretas de arquivos, notas, tags, aliases, propriedades e links resolvidos sao deterministicas.
- Alias duplicado, tag singleton e chaves de frontmatter fora do conjunto canonico sao deteccoes deterministicas.
- Notas em boundary, HOME/Kevyn Lucas, diarios e dossies marcados como protegidos foram excluidas das sugestoes.
- Sugerir aliases a partir de alvos de wikilink nao resolvidos e correspondencia unica por artigo/pontuacao e heuristica de alta confianca.
- Propagacao de tags por maioria entre notas-irmaas usa heuristica de contexto local.
- Sugestoes de link usam sobreposicao de tags, vizinhanca de pasta e phrasings comuns como sinal de alta confianca.
- Cobertura de hub/MOC combina padrao lexical com densidade de links, portanto e heuristica.

## Areas Bloqueadas

- boundary: 364 notas | protegidas: 215 | bloqueadas: 684
- `HOME\Kevyn Lucas`
- `HOME\Neuron\Neuron Obsidian`
- `HOME\Ágora\Ágora Obsidian`
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico`
- `HOME\SaaS com Kelvyn\TPM\TPM Obsidian`
- `Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian`
- `HOME`: 178 notas protegidas/bloqueadas
- `ACIRV`: 37 notas protegidas/bloqueadas

## Tags

- Singleton tags: `033`, `036`, `129cdf`, `1b26ae`, `6`, `8bec01`, `absoluto`, `acaso`, `anti-intelectualismo`, `ascetismo`, `atencao_plena`, `autodestruicao`, `banalidade`, `capcut`, `causalidade`, `cidadela_interior`, `clarissa_pinkola_estes`, `cocriacao`, `comunidade`, `constancia`, `cooperacao`, `cosmopolitismo`, `definicoes`, `desconstrucao`, `direito_romano`
- `comunicacao`: 2 variantes -> `comunicacao`, `comunicação`
- `lideranca`: 2 variantes -> `lideranca`, `liderança`
- `marketing`: 2 variantes -> `Marketing`, `marketing`
- `acirv`: 2 variantes -> `ACIRV`, `acirv`
- `persuasao`: 2 variantes -> `persuasao`, `persuasão`
- `vendas`: 2 variantes -> `Vendas`, `vendas`
- `etica`: 2 variantes -> `etica`, `ética`
- `resiliencia`: 2 variantes -> `resiliencia`, `resiliência`
- `estrategia`: 2 variantes -> `estrategia`, `estratégia`
- `produtividade`: 2 variantes -> `Produtividade`, `produtividade`
- `metafora`: 2 variantes -> `metafora`, `metáfora`
- `negociacao`: 2 variantes -> `negociacao`, `negociação`
- `percepcao`: 2 variantes -> `percepcao`, `percepção`
- `ia`: 2 variantes -> `ia`, `IA`
- `sucesso`: 2 variantes -> `Sucesso`, `sucesso`
- `acirvmulher`: 3 variantes -> `ACIRVmulher`, `ACIRVMulher`, `acirvmulher`
- `gest`: 2 variantes -> `Gest`, `gest`
- `lideran`: 2 variantes -> `Lideran`, `lideran`
- `neg`: 2 variantes -> `neg`, `Neg`
- `negocios`: 2 variantes -> `negocios`, `negócios`

## Aliases

- Aliases com duplicidade: 0

## Propriedades

- `resumo`: 906 ocorrencia(s)
- `contexto`: 862 ocorrencia(s)
- `criado`: 533 ocorrencia(s)
- `modificado`: 533 ocorrencia(s)
- `excalidraw-plugin`: 135 ocorrencia(s)
- `excalidraw-open-md`: 134 ocorrencia(s)
- `origem`: 100 ocorrencia(s)
- `funil`: 17 ocorrencia(s)
- `tema`: 15 ocorrencia(s)
- `kanban-plugin`: 11 ocorrencia(s)
- `relacionado`: 8 ocorrencia(s)
- `solicitante`: 2 ocorrencia(s)
- `teste`: 2 ocorrencia(s)
- `ACIRV\Diário\2025\11 - novembro\11 - novembro.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\11 - novembro\11 - terça-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\11 - novembro\13 - quinta-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\11 - novembro\14 - sexta-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\11 - novembro\17 - segunda-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\11 - novembro\19 - quarta-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\11 - novembro\21 - sexta-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\11 - novembro\24 - segunda-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\11 - novembro\25 - terça-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\11 - novembro\27 - quinta-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\12 - dezembro\01 - segunda-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\12 - dezembro\02 - terça-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\12 - dezembro\03 - quarta-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\12 - dezembro\04 - quinta-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\12 - dezembro\05 - sexta-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\12 - dezembro\08 - segunda-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\12 - dezembro\09 - terça-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\12 - dezembro\10 - quarta-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\12 - dezembro\12 - dezembro.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\12 - dezembro\12 - sexta-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\12 - dezembro\29 - segunda-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2025\2025.md`: frontmatter-parse-warning
- `ACIRV\Diário\2026\01 - janeiro\01 - janeiro.md`: frontmatter-parse-warning
- `ACIRV\Diário\2026\01 - janeiro\07 - quarta-feira.md`: frontmatter-parse-warning
- `ACIRV\Diário\2026\01 - janeiro\08 - quinta-feira.md`: frontmatter-parse-warning

## Tags por Dominio

- `HOME`: `flashcards` 710, `estoicismo` 110, `resistencia` 89, `comunicacao` 63, `lideranca` 63, `psicologia` 55, `cnv` 51, `aprendizado` 50, `infomativo` 42, `marketing` 40
- `ACIRV`: `acirv` 20, `conectarparacrescer` 11, `rioverde` 6, `acirvmulher` 5, `hashtags` 4, `gest` 4, `neg` 4, `lideran` 4, `empreendedorismo` 3, `sebrae` 2
- `Google Drive (Not synced)`: `000000` 2

## Propagacao de Tags

- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Agir sem Hesitação.md` receberia `estoicismo` via `HOME\O Professor\01_SELF - O IMPERADOR\Meditações` (0.88)
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Amizade e Virtude.md` receberia `estoicismo` via `HOME\O Professor\01_SELF - O IMPERADOR\Meditações` (0.88)
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Beleza do Acidental.md` receberia `estoicismo` via `HOME\O Professor\01_SELF - O IMPERADOR\Meditações` (0.88)
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Bem Racional vs. Sensorial.md` receberia `estoicismo` via `HOME\O Professor\01_SELF - O IMPERADOR\Meditações` (0.88)
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Consistência do Sábio.md` receberia `estoicismo` via `HOME\O Professor\01_SELF - O IMPERADOR\Meditações` (0.88)
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Filosofia como Guia.md` receberia `estoicismo` via `HOME\O Professor\01_SELF - O IMPERADOR\Meditações` (0.88)
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Honra e Voluntariedade.md` receberia `estoicismo` via `HOME\O Professor\01_SELF - O IMPERADOR\Meditações` (0.88)
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Valor do Tempo Presente.md` receberia `estoicismo` via `HOME\O Professor\01_SELF - O IMPERADOR\Meditações` (0.88)
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Violência contra a Alma.md` receberia `estoicismo` via `HOME\O Professor\01_SELF - O IMPERADOR\Meditações` (0.88)
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Visão Física da Morte.md` receberia `estoicismo` via `HOME\O Professor\01_SELF - O IMPERADOR\Meditações` (0.88)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\A Causa Real da Raiva.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\A Fome de Apreciação.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\A Raiva como Alarme.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\A Superficialidade da Punição.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Amtssprache (Linguagem de Escritório).md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Auto-perdão na CNV.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Autocompaixão e o Luto na CNV.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Inteligência Humana e Observação.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\O Deveria como Violência Interior.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\O Foco no Positivo.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Quatro Passos para Expressar a Raiva.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Reanimar Conversas Mortas.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Resolução de Conflitos Interiores.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Tenho de para Escolho porque....md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Tradução de Autojulgamentos.md` receberia `cnv` via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta` (0.77)
- `HOME\O Professor\00_Cérebro Operacional\V1\00_modelo_nota_atomica.md` receberia `flashcards` via `HOME\O Professor\00_Cérebro Operacional\V1` (0.75)

## Links Sugeridos

- `ACIRV\Notas\Dados Sorriso Verdadeiro.md` <-> `ACIRV\Notas\Sorriso Verdadeiro.md`: tags `ACIRV`, `DoeSorrisos`, `EmpresariadoComProp`, `NatalSolid`, `RioVerde`, `SorrisoVerdadeiro`
- `ACIRV\Notas\GESTÃO DA ATENÇÃO - Café entre amigos 01.md` <-> `ACIRV\Notas\Responsabilidades do Social Media ACIRV - Com comentários.md`: tags `ACIRV`, `Caf`, `Gest`, `Lideran`, `Neg`, `Produtividade`
- `ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V1.md` <-> `ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V2.md`: tags `ACIRV`, `ACIRVMulher`, `ConectarParaCrescer`, `Empreendedorismo`, `Lideran`, `RioVerde`
- `HOME\ACIRV\Notas\Dados Sorriso Verdadeiro.md` <-> `HOME\ACIRV\Notas\Sorriso Verdadeiro.md`: tags `ACIRV`, `DoeSorrisos`, `EmpresariadoComProp`, `NatalSolid`, `RioVerde`, `SorrisoVerdadeiro`
- `HOME\ACIRV\Notas\GESTÃO DA ATENÇÃO - Café entre amigos 01.md` <-> `HOME\ACIRV\Notas\Responsabilidades do Social Media ACIRV - Com comentários.md`: tags `ACIRV`, `Caf`, `Gest`, `Lideran`, `Neg`, `Produtividade`
- `HOME\ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V1.md` <-> `HOME\ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V2.md`: tags `ACIRV`, `ACIRVMulher`, `ConectarParaCrescer`, `Empreendedorismo`, `Lideran`, `RioVerde`
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Alegria na Virtude.md` <-> `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Autossuficiência da Alma.md`: tags `estoicismo`, `felicidade`, `flashcards`, `virtude`
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Circularidade da História.md` <-> `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Morte Diária.md`: tags `estoicismo`, `flashcards`, `perspectiva`, `tempo`
- `HOME\O Professor\02_EGO - O MAGUS\A guerra da arte\A Mentalidade do Fuzileiro Naval.md` <-> `HOME\O Professor\02_EGO - O MAGUS\A guerra da arte\Imunidade à Crítica e Elogio.md`: tags `estoicismo`, `flashcards`, `resiliencia`, `resistencia`
- `HOME\O Professor\02_EGO - O MAGUS\A guerra da arte\A Recorrência Diária da Resistência.md` <-> `HOME\O Professor\02_EGO - O MAGUS\A guerra da arte\A Rotina de Somerset Maugham.md`: tags `disciplina`, `flashcards`, `resistencia`, `rotina`
- `HOME\O Professor\02_EGO - O MAGUS\A guerra da arte\Automedicação e Consumismo.md` <-> `HOME\O Professor\02_EGO - O MAGUS\A guerra da arte\Limitações da Orientação Hierárquica.md`: tags `alienacao`, `flashcards`, `resistencia`, `sociologia`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Apreciação Sincera na Gestão de Crises.md` <-> `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Sorriso como Ferramenta de Ensino e Venda.md`: tags `flashcards`, `lideranca`, `psicologia_aplicada`, `reforco_positivo`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Autoimagem do Inimigo Público como Benfeitor.md` <-> `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Racionalização da Própria Bondade.md`: tags `autoimagem`, `flashcards`, `psicologia_criminal`, `racionalizacao`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Habilidade de Despertar Entusiasmo (Charles Schwab).md` <-> `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Elogio como Ferramenta de Motivação.md`: tags `flashcards`, `gestao_de_pessoas`, `lideranca`, `reforco_positivo`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Habilidade de Despertar Entusiasmo (Charles Schwab).md` <-> `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Elogio Sincero como Ferramenta de Liderança.md`: tags `flashcards`, `lideranca`, `motivacao`, `reforco_positivo`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\Elogio Barato.md` <-> `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\Interesse Sincero é uma Qualidade Essencial do Vendedor.md`: tags `autenticidade`, `etica`, `flashcards`, `sinceridade`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\Elogio Público e Particular (Andrew Carnegie).md` <-> `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Elogio como Ferramenta de Motivação.md`: tags `flashcards`, `gestao_de_pessoas`, `lideranca`, `reforco_positivo`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Elogio como Ferramenta de Motivação.md` <-> `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Laço Vital da Equipe.md`: tags `feedback`, `flashcards`, `gestao_de_pessoas`, `lideranca`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PRINCÍPIO 1 (Parte 2) - Torne-se verdadeiramente interessado na outra pessoa..md` <-> `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PRINCÍPIO 1 - Não critique, não condene, não se queixe..md`: tags `flashcards`, `principio_fundamental`, `regra_de_ouro`, `relacionamentos`
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PRINCÍPIO 1 - Não critique, não condene, não se queixe..md` <-> `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PRINCÍPIO 2 - Aprecie honesta e sinceramente..md`: tags `comunicacao_nao_violenta`, `flashcards`, `principio_fundamental`, `relacionamentos`
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\A Raiva como Alarme.md` <-> `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Tradução de Autojulgamentos.md`: tags `autocompaixao`, `flashcards`, `inteligencia_emocional`, `sombra`
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\A Raiz dos Sentimentos.md` <-> `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Identificação de Sentimentos.md`: tags `cnv`, `flashcards`, `inteligencia_emocional`, `sentimentos`
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Compreensão Intelectual versus Empatia.md` <-> `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Substituindo Diagnósticos Psicológicos.md`: tags `cnv`, `empatia`, `flashcards`, `psicologia`
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Comunicação Alienante da Vida.md` <-> `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Julgamentos como Expressões Trágicas de Necessidades.md`: tags `cnv`, `comunicacao`, `flashcards`, `julgamento`
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Comunicação Alienante da Vida.md` <-> `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Observar sem Avaliar.md`: tags `cnv`, `comunicacao`, `flashcards`, `julgamento`
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Definição de Comunicação Não-Violenta (CNV).md` <-> `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Julgamentos como Expressões Trágicas de Necessidades.md`: tags `cnv`, `comunicacao`, `empatia`, `flashcards`
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Definição de Comunicação Não-Violenta (CNV).md` <-> `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Obstáculos à Empatia.md`: tags `cnv`, `comunicacao`, `empatia`, `flashcards`
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Definição de Comunicação Não-Violenta (CNV).md` <-> `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Parafrasear.md`: tags `cnv`, `comunicacao`, `empatia`, `flashcards`
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Definição de Comunicação Não-Violenta (CNV).md` <-> `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Quatro Opções ao Receber Mensagens Negativas.md`: tags `cnv`, `comunicacao`, `empatia`, `flashcards`
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Distinção entre Juízo de Valor e Julgamento Moralizador.md` <-> `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\O Conceito de Merecimento.md`: tags `cnv`, `etica`, `flashcards`, `julgamento`

## Cobertura de Hubs e MOCs

- `HOME`: 462/3123 notas cobertas, 82 hubs
- `ACIRV`: 14/205 notas cobertas, 2 hubs
- `Google Drive (Not synced)`: 0/14 notas cobertas, 0 hubs
- `templates`: 1/8 notas cobertas, 1 hubs
- `AGENTS.md`: 0/1 notas cobertas, 0 hubs
- `Índice do Vault.md`: 1/1 notas cobertas, 1 hubs
