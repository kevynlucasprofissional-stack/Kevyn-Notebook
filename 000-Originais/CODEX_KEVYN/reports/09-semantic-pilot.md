# Piloto 09 - Consolidacao Semantica Assistida

- Gerado em: 2026-04-04
- Objetivo: Executar um piloto restrito de consolidacao semantica em um dominio de risco moderado e alto potencial de ganho, sem consolidacao ampla do vault.

## Metodo

- Reuso do inventario de near-duplicates de `reports/04-near-duplicates.json` como ponto de partida.
- Exclusao de areas proibidas para este piloto: `HOME/Kevyn Lucas`, diarios, dossies longos e sub-vaults de fronteira.
- Leitura manual apenas de notas do dominio `ACIRV/Notas` ligadas a comunicacao operacional, tom de voz, releases e cerimonial.
- Selecao somente de clusters com sobreposicao textual ou estrutural suficiente para merge manual assistido.
- Criacao de notas sintese apenas onde a redundancia ficou clara e o ganho de navegacao superou o risco.

## Criterios

- Dominio unico e vivo: `ACIRV/Notas`.
- Nao mover, renomear, fundir ou apagar notas originais.
- Preservar links para origem em toda nota sintese criada.
- Limitar o piloto a clusters revisaveis, sem expandir para o vault inteiro.

## Dominio escolhido

`ACIRV/Notas` foi escolhido por combinar:

- material operacional relativamente curto ou medio
- varias versoes e prompts derivados sobre o mesmo processo editorial
- bom potencial de reduzir ruído de navegacao sem tocar em material pessoal denso

## Clusters revisaveis selecionados

### 1. Workflow de releases

- Notas: `ACIRV\Notas\Playbook de Releases.md`, `ACIRV\Notas\Releaser.md`, `ACIRV\Notas\PROMPT RELEASE.md`
- Sinal de redundancia: `Playbook de Releases` e `Releaser` compartilham o mesmo corpo-base; `PROMPT RELEASE` funciona como gatilho de uso do mesmo processo.
- Acao recomendada: manter `Playbook de Releases` como referencia detalhada, usar a sintese como entrada principal e tratar `PROMPT RELEASE` como atalho contextual.
- Status do piloto: criada `ACIRV\Notas\Sintese - Workflow de Releases.md`.

### 2. Tom de voz ACIRV 2026

- Notas: `ACIRV\Notas\Tom de voz 2026 da ACIRV - V3.md`, `ACIRV\Notas\Tom de voz ACIRV - V4.md`, `ACIRV\Notas\Novo tom de voz 2026.md`, `ACIRV\Notas\Dados sobre o novo tom de voz e planejamento de 2026.md`, `ACIRV\Notas\Como melhorar o novo tom de voz da ACIRV.md`, `ACIRV\Notas\(Desatualizado) Padrão de qualidade do novo tom de voz.md`
- Sinal de redundancia: V3 e V4 sao near-duplicates confirmados no relatorio 04; as demais notas orbitam o mesmo nucleo editorial com regras, ajustes e embasamento repetidos.
- Acao recomendada: usar a sintese como hub curto, preservar V4 como versao operacional mais recente e manter V3 e notas auxiliares como historico de decisao.
- Status do piloto: criada `ACIRV\Notas\Sintese - Tom de Voz ACIRV 2026.md`.

### 3. Cobertura social media ACIRV Mulher

- Notas: `ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V1.md`, `ACIRV\Notas\Roteiro do Social Media - Cerimônia de Posse ACIRV Mulher - V2.md`
- Sinal de redundancia: V2 amplia e refina a mesma estrutura narrativa da V1, preservando a maior parte do esqueleto de cobertura.
- Acao recomendada: merge manual assistido promovendo V2 a canonical draft e adicionando, em rodada futura, um apontamento explicito de supersessao para V1.
- Status do piloto: apenas recomendacao; nenhuma alteracao nas notas de origem.

### 4. Cerimonial Cafe Entre Amigos

- Notas: `ACIRV\Notas\PLAYBOOK Cerimonial Café entre Amigos.md`, `ACIRV\Notas\CERIMONIAL - Café entre amigos 27.11.md`, `ACIRV\Notas\250226 - ROTEIRO DE CERIMONIAL CAFÉ ENTRE AMIGOS - Reforma tributária.md`, `ACIRV\Notas\Roteiro de Cerimonial Café Entre Amigos – Especial Mês da Mulher - 260326.md`
- Sinal de redundancia: o playbook consolida uma estrutura que reaparece em roteiros de edicoes especificas com variacoes locais de abertura, patrocinio e encerramento.
- Acao recomendada: manter o playbook como matriz, revisar manualmente os roteiros especificos para remover boilerplate redundante so depois de validar que nao carregam informacao contextual exclusiva.
- Status do piloto: apenas recomendacao; nenhuma alteracao nas notas de origem.

## Notas sintese criadas

- `ACIRV\Notas\Sintese - Workflow de Releases.md`
- `ACIRV\Notas\Sintese - Tom de Voz ACIRV 2026.md`

## Arquivos afetados

- `ACIRV\Notas\Sintese - Workflow de Releases.md`
- `ACIRV\Notas\Sintese - Tom de Voz ACIRV 2026.md`
- `reports/09-semantic-pilot.md`
- `logs/09-semantic-pilot.md`

## Riscos

- Alguns agrupamentos misturam duplicacao e variacao legitima de contexto; por isso o piloto nao removeu nada.
- A familia de notas de tom de voz ainda contem embasamento util que pode ser perdido se houver merge agressivo.
- Roteiros de evento podem parecer redundantes, mas frequentemente guardam patrocinadores, datas e instrucoes operacionais unicas.

## Proximos passos

- Validar se as duas notas sintese realmente reduzem a busca no uso diario.
- Se aprovado, criar em rodada futura uma convencao leve de supersessao, por exemplo "substitui parcialmente" ou "ver sintese".
- Revisar manualmente V1/V2 e os roteiros de cerimonial antes de qualquer consolidacao adicional.

## Resultado do piloto

- 1 dominio selecionado
- 4 clusters revisaveis considerados seguros
- 2 notas sintese criadas
- 0 movimentos de arquivo
- 0 exclusoes
