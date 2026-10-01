# Plano de Mudancas - CICLO-0027

## Escopo do lote

- Fontes: `SRC-000103`, `SRC-000104`, `SRC-000105`, `SRC-000106`, `SRC-000107`
- Recorte editorial: planejamento e copy de lancamento semente do DS21/Svelte
- Regra epistemica: integrar apenas o que o lote permite concluir sobre a atuacao, o repertorio e o nivel de dominio de Kevyn; nao importar o conteudo tematico do produto nem transcrever credenciais

## Mudancas planejadas

### MUD-000093
- Unidade: lote operacional `SRC-000103`
- Nota de destino: `09-Fontes-e-Evidencias/Fonte - Roteiros e lancamento semente DS21 2025.md`
- Operacao: criar
- Justificativa: o lote possui identidade propria, combina planejamento editorial, roteiro de campanha e material sensivel, e sera citado de mais de um lugar
- Impacto: nova nota-fonte agregada com hashes, limites de uso e redacao de seguranca
- Frontmatter afetado: novo frontmatter completo
- Links e MOCs afetados: referenciavel por notas de Marketing e Salus
- Risco de duplicacao: medio; mitigar distinguindo este lote de analises posteriores de resultado
- Risco interpretativo: medio; nao confundir plano/roteiro com entrega ou desempenho real
- Validacao prevista: leitura cruzada com manifesto e conferência de sensibilidade

### MUD-000094
- Unidade: planejamento operacional e cadencia de lancamento do lote `SRC-000103`
- Nota de destino: `04-Trabalho-Vocacao-e-Projetos/Marketing comunicacao e processos.md`
- Operacao: ampliar
- Justificativa: a nota precisa registrar o nivel de organizacao de funil, cadencia editorial e posse operacional de acessos sem transcrever segredos
- Impacto: reforca evidencia de coordenacao de fluxo editorial, assets de lancamento e trato seguro de credenciais
- Frontmatter afetado: `fontes_primarias`, `versao_conteudo`, `ultima_revisao`
- Links e MOCs afetados: novo link para a nota-fonte agregada do lote
- Risco de duplicacao: baixo
- Risco interpretativo: medio; explicitar que planejamento nao equivale a execucao concluida
- Validacao prevista: comparacao com notas ja existentes sobre DS21 e acessos

### MUD-000095
- Unidade: CTAs, VSL e prova social dos lotes `SRC-000104` a `SRC-000107`
- Nota de destino: `04-Trabalho-Vocacao-e-Projetos/Marketing comunicacao e processos.md`
- Operacao: ampliar
- Justificativa: o bloco mostra repertorio de copy de resposta direta em fundo/meio de funil e aprofunda a evidencia de competencias de oferta e narrativa comercial
- Impacto: melhora a precisao sobre bonus, garantia, ancoragem de preco, urgencia e prova social
- Frontmatter afetado: nenhum adicional alem de `fontes_primarias`, `versao_conteudo`, `ultima_revisao`
- Links e MOCs afetados: novo link para a nota-fonte agregada do lote
- Risco de duplicacao: medio; mitigar diferenciando este lote dos criativos curtos do `CICLO-0026`
- Risco interpretativo: medio; nao atribuir eficacia ou autoria absoluta sem evidencias adicionais
- Validacao prevista: revisao semantica com a nota-fonte agregada

### MUD-000096
- Unidade: desenho do lancamento semente do DS21 nos lotes `SRC-000103` a `SRC-000107`
- Nota de destino: `02-Cronologia-e-Memorias/Salus e Desafio Svelte.md`
- Operacao: ampliar
- Justificativa: a cronologia do projeto fica mais precisa ao registrar que havia planejamento explicito de cadencia, VSL, landing page, bonus, lives e CTA em agosto de 2025
- Impacto: esclarece o estagio de estruturacao da oferta sem reescrever o produto
- Frontmatter afetado: `fontes_primarias`, `versao_conteudo`, `ultima_revisao`
- Links e MOCs afetados: novo link para a nota-fonte agregada do lote
- Risco de duplicacao: baixo
- Risco interpretativo: medio; tratar o lote como planejamento e linguagem de lancamento, nao como resultado
- Validacao prevista: checagem de coerencia com metricas e diagnosticos ja integrados

### MUD-000097
- Unidade: estado operacional do programa de integracao apos a reincorporacao manual do lote
- Nota de destino: `95-Auditorias/Estado da integracao.md`
- Operacao: ampliar
- Justificativa: manter o vault legivel sobre a reabertura metodologica e o proximo item pendente
- Impacto: atualiza contagem de fontes reavaliadas manualmente e o proximo `fonte_id`
- Frontmatter afetado: `ultima_revisao`
- Links e MOCs afetados: nenhum
- Risco de duplicacao: baixo
- Risco interpretativo: baixo
- Validacao prevista: comparacao com `Estado-Integracao.json`
