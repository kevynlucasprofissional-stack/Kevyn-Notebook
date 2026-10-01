# Plano de Mudancas - Ciclo 0003

## Escopo

Lote `SRC-000010` a `SRC-000020`, composto por diarios transcritos, diarios escritos e uma analise de IA sobre o Diario Negro 01.

## Decisoes do lote

- `SRC-000010`, `SRC-000011`, `SRC-000012`, `SRC-000013`, `SRC-000014`, `SRC-000016`, `SRC-000017`, `SRC-000018`, `SRC-000019` e `SRC-000020` serao classificados como `ja_integrado`, pois ha notas de fonte existentes com SHA-256 e tamanho correspondentes, alem de registros brutos selecionados no vault.
- `SRC-000015` sera tratado como `interpretacao_ia`, nao como relato direto nem como avaliacao clinica.
- O conteudo integral de `SRC-000015` nao sera copiado para o vault. Apenas serao incorporadas conclusoes editoriais curtas sobre padroes de Kevyn, explicitamente rotuladas como leitura derivada.

## Mudancas previstas

### UNI-000012

- Fonte: `SRC-000010` a `SRC-000014` e `SRC-000016` a `SRC-000020`.
- Destino: controle de integracao, manifesto e matriz.
- Operacao: classificar como `ja_integrado`.
- Justificativa: notas de fonte e registros selecionados ja existem; hashes e tamanhos coincidem com o manifesto atual.
- Impacto: melhora rastreabilidade sem duplicar bruto nem reescrever notas ja cobertas.
- Risco de duplicacao: baixo, desde que nenhuma nova nota de fonte seja criada.
- Risco interpretativo: baixo, pois nao ha nova sintese biografica.
- Validacao prevista: auditoria de links e conferência de SHA-256.

### UNI-000013

- Fonte: `SRC-000015`.
- Destinos:
  - `04-Trabalho-Vocacao-e-Projetos/Execucao versus complexidade.md`
  - `01-Perfil-e-Autoconhecimento/Narrativa de grandeza e vida comum.md`
  - `01-Perfil-e-Autoconhecimento/Organizacao do conhecimento.md`
- Operacao: ampliar notas existentes.
- Justificativa: a analise de IA reforca uma leitura ja presente no vault: excesso de simbolizacao, autoanalise e sistemas pode competir com acao concreta, enquanto trabalho, corpo, rotina e entrega funcionam como aterramento.
- Frontmatter afetado: incluir `[[Fonte - Analises Diario Negro 01]]` em `fontes_derivadas` quando ausente.
- Links afetados: criar relacoes `exemplifica`, `contextualiza` e `desenvolve` entre as notas de destino e a fonte.
- Risco de duplicacao: medio, mitigado por textos curtos e foco no que a fonte permite concluir sobre Kevyn.
- Risco interpretativo: alto se tratado como fato psicologico; mitigacao: rotular como `interpretacao_ia` e `hipotese_de_trabalho`, sem diagnostico.
- Validacao prevista: auditoria complementar de Markdown, YAML, links, JSON/Canvas/Base e checagem manual das relacoes.

## Mudancas fora do escopo

- Nao corrigir mojibake legado em massa neste ciclo.
- Nao importar referencias externas citadas dentro de `SRC-000015`.
- Nao criar nota nova sobre escrita expressiva, terapia do esquema, Jung, WOOP, MCII ou ativacao comportamental.
- Nao alterar `Dados Kevyn`.
