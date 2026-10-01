# Piloto 16 - Consolidacao Semantica Assistida 2

- Gerado em: 2026-04-04
- Objetivo: Executar uma segunda rodada piloto de consolidacao semantica em um dominio de risco moderado e alto ganho, sem consolidacao ampla do vault e sem tocar em `HOME/Kevyn Lucas`.

## Metodo

- Reuso do inventario de near-duplicates de `reports/05-near-duplicates.md` e dos manifestos em `_merge_candidates/05-near-duplicates/`.
- Leitura manual apenas de material de `ACIRV/Notas` ligado a comunicacao institucional, tom de voz e cobertura de evento.
- Exclusao de diários, dossiers longos, `HOME/Kevyn Lucas` e qualquer fronteira de sub-vault.
- Criacao de notas sintese somente onde a redundancia entre as fontes ficou clara e o ganho de navegacao compensou o risco.
- Nenhuma nota de origem foi apagada, renomeada ou substituida.

## Criterios

- Dominio unico: comunicacao operacional da ACIRV.
- Maximo de 5 clusters revisaveis nesta rodada.
- Apenas sinteses curtas e rastreaveis, com links para as fontes.
- Sinalizar claramente o que foi criado e o que ficou apenas como sugestao.

## Dominio escolhido

`ACIRV/Notas` no eixo de comunicacao institucional e cobertura de eventos.

Este dominio foi escolhido porque:

- concentra notas curtas e repetitivas, com estrutura muito proxima
- tem ganho alto para navegacao diaria
- nao depende de consolidacao de material pessoal denso ou de dossies longos

## Clusters revisaveis selecionados

### 1. Tom de voz e regras de redacao

- Clusters: `049` e `306`
- Fontes: `ACIRV\Notas\Novo tom de voz 2026.md`, `ACIRV\Notas\Como melhorar o novo tom de voz da ACIRV.md`
- Sinal de redundancia: ambos orbitam o mesmo nucleo editorial sobre identidade, tom, abertura e regras de redacao.
- Status do piloto: criada `ACIRV\Notas\Sintese - Tom de Voz e Regras de Redacao.md`.

### 2. Conecta Saude - plano e cobertura

- Clusters: `057`, `060` e `061`
- Fontes: `ACIRV\Notas\Planejamento Social Media - Primeiro Conecta Saúde.md`, `ACIRV\Notas\RELEASE - Conecta Saúde (pré-evento).md`, `ACIRV\Notas\RELEASE - Conecta Saúde (Pós Evento).md`
- Sinal de redundancia: o planejamento, o release de convocacao e o release pos-evento repetem o mesmo eixo narrativo de networking, prova social e reaproveitamento editorial.
- Status do piloto: criada `ACIRV\Notas\Sintese - Conecta Saude - Plano e Cobertura.md`.

### 3. Comunicacao geral de evento ACIRV

- Clusters: `062`, `063` e `064`
- Fontes: `ACIRV\Notas\Release Fórum de IA.md`, `ACIRV\Notas\Responsabilidades do Social Media da ACIRV.md`, `ACIRV\Notas\Resumo Executivo da Campanha de Indicação ACIRV.md`
- Sinal de redundancia: sao notas vizinhas e muito utiliarias, mas ainda misturam funcao, campanha e evento especifico; por isso ficaram apenas como sugestao nesta rodada.
- Status do piloto: apenas recomendacao; nenhuma alteracao nas notas de origem.

## Notas sintese criadas

- `ACIRV\Notas\Sintese - Tom de Voz e Regras de Redacao.md`
- `ACIRV\Notas\Sintese - Conecta Saude - Plano e Cobertura.md`

## Clusters apenas sugeridos

- `062` - `Release Fórum de IA.md`
- `063` - `Responsabilidades do Social Media da ACIRV.md`
- `064` - `Resumo Executivo da Campanha de Indicação ACIRV.md`

## Ganhos percebidos

- uma entrada curta para o tom de voz reduziu a necessidade de alternar entre nota mestre e nota de melhoria
- uma entrada unica para Conecta Saude separou planejamento, pre-evento e pos-evento sem apagar as fontes
- a navegacao ficou mais direta para quem precisa redigir ou revisar sem reconstruir o contexto a cada vez
- o piloto mostrou que a consolidacao semantica funciona bem quando a redundancia e estrutural e a area ja tem uma rede mais consistente

## Arquivos afetados

- `ACIRV\Notas\Sintese - Tom de Voz e Regras de Redacao.md`
- `ACIRV\Notas\Sintese - Conecta Saude - Plano e Cobertura.md`
- `reports/16-semantic-pilot-2.md`
- `logs/16-semantic-pilot-2.md`

## Riscos

- algumas notas de evento ainda misturam planejamento, briefing e resultado; por isso ficaram fora da consolidacao automatica
- o ganho desta rodada e local e operacional; nao deve ser extrapolado para o vault inteiro
- sem Obsidian CLI funcional, nao foi feito nenhum move/rename para preservar integridade de links

## Proximos passos

- validar se as duas sinteses realmente reduzem a busca no uso diario
- se aprovado, criar uma terceira camada curta para comunicacao geral de evento ACIRV
- reavaliar apenas os clusters sugeridos em rodada futura, sem ampliar o escopo para areas protegidas

## Resultado do piloto

- 1 dominio selecionado
- 5 clusters revisaveis considerados
- 2 notas sintese criadas
- 3 clusters apenas sugeridos
- 0 movimentos de arquivo
- 0 exclusoes
