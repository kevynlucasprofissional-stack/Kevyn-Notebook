# Plano de Mudancas - Ciclo 0005

## Escopo

Lote `SRC-000035` a `SRC-000042`, com arquivos de leads, pitch telefonico, planejamento de palestra/oficina de IA e propostas de marketing para Espaco Prema.

## Decisoes do lote

- Tratar `SRC-000035` como Base do Obsidian com configuracao simples de visualizacao de leads; nao ha leads pessoais dentro do arquivo.
- Tratar `SRC-000041` como arquivo vazio, analisado e irrelevante justificado.
- Tratar `SRC-000036`, `SRC-000040` e `SRC-000042` como planejamento de palestra/oficina de IA e vendas por telefone.
- Tratar `SRC-000037`, `SRC-000038` e `SRC-000039` como propostas/pitches de marketing para Espaco Prema, evidenciando capacidade de adaptar frameworks de lancamento/oferta a um nicho de yoga/espiritualidade.
- Nao criar nota sobre yoga, respiracao, ansiedade ou terapias; o conteudo e relevante para entender Kevyn como produtor de proposta, nao como referencia teorica ou de saude.

## Mudancas previstas

### UNI-000017

- Fontes: `SRC-000035`, `SRC-000036`, `SRC-000040`, `SRC-000042`.
- Destinos: `Fonte - Palestra IA e pitches Espaco Prema 2025`, `Inteligencia artificial e automacao`, `Marketing comunicacao e processos`, `Portfolio de projetos`.
- Operacao: criar fonte agregada e ampliar notas existentes.
- Justificativa: os arquivos mostram planejamento de palestra/oficina de IA, promessa, estrutura, demos, ROI, governanca, ligacao para leads e organizacao de Base.
- Risco de duplicacao: medio, pois o ciclo 0004 ja integrou IMRIA; mitigacao: registrar este lote como aprofundamento/planejamento da palestra de 25 de outubro.
- Risco interpretativo: medio; nao confirmar realizacao do evento sem evidencias posteriores.
- Validacao prevista: auditoria de links e confirmacao de que o arquivo `.base` nao foi tratado como JSON puro.

### UNI-000018

- Fontes: `SRC-000037`, `SRC-000038`, `SRC-000039`.
- Destinos: `Fonte - Palestra IA e pitches Espaco Prema 2025`, `Marketing comunicacao e processos`, `Negocios e marketing`, `Portfolio de projetos`.
- Operacao: criar fonte agregada e ampliar notas existentes.
- Justificativa: o conjunto evidencia pesquisa de oferta, FOFA, precificacao, funil, copy, provas, roadmap de 90 dias, automacao e adaptacao de frameworks tipo Erico/Hormozi/Kevyn.
- Risco de duplicacao: baixo se tratado como proposta, nao como projeto confirmado.
- Risco interpretativo: medio; nao tratar afirmacoes de saude/ansiedade como recomendacao do vault.
- Validacao prevista: revisar texto para manter foco em repertorio de Kevyn.

### UNI-000019

- Fonte: `SRC-000041`.
- Destino: manifesto e matriz.
- Operacao: classificar como `irrelevante_justificado`.
- Justificativa: arquivo vazio.
- Validacao prevista: registrar tamanho zero e ausencia de conteudo.

## Mudancas fora do escopo

- Nao criar material teorico sobre yoga, terapia, respiracao, ansiedade, ROI, governanca de IA ou vendas telefonicas.
- Nao copiar os scripts completos de ligacao, pitch ou palestra.
- Nao confirmar clientes, leads, vendas ou realizacao de eventos sem fonte posterior.
- Nao alterar `Dados Kevyn`.
