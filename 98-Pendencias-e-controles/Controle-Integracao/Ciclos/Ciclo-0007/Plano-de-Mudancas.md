# Plano de Mudancas - Ciclo 0007 - Revisao Corretiva

## Escopo

Revisar `SRC-000051` a `SRC-000054`, corrigir tamanhos, reconciliar manifesto/matriz e adicionar proveniencia para as sinteses de copy, oferta e lancamento DS21.

## Mudancas previstas

- Criar `Fonte - Analises de copy e lancamento DS21 2025` com IDs, caminhos, hashes, localizadores e limites epistemologicos.
- Adicionar a fonte agregada a `Negocios e marketing`, `Marketing comunicacao e processos` e `Salus e Desafio Svelte`.
- Incluir a nota-fonte no indice geral.
- Corrigir `Arquivos-Analisados.csv` para tamanhos binarios reais.
- Atualizar manifesto e matriz para `analisado`/`integrado`, `CICLO-0007`.
- Produzir os artefatos obrigatorios ausentes e executar auditoria complementar.

## Riscos

- Os arquivos clone Erico/Hormozi sao interpretacoes de IA, nao consultoria humana.
- Metricas do DS21 devem ser apresentadas como registradas nas fontes, sem extrapolacao.
- A assinatura `Por Kevyn` sustenta autoria declarada de `SRC-000052`, nao autoria exclusiva de todo o lote.

## Validacao

- SHA-256 calculado sobre bytes reais.
- Auditoria de YAML, links, IDs, basenames, JSON/Canvas/Base e segredos.
- Comparacao entre manifesto, matriz e arquivos do ciclo.
