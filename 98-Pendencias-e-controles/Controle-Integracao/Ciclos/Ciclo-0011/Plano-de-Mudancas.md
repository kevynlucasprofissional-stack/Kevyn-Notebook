# Plano de Mudancas - Ciclo 0011 - Triagem Ampla

## Escopo

Cobrir `SRC-000079` a `SRC-000500` como bloco de triagem e registrar a fronteira de cobertura no manifesto sem inflar o estado de analise completa.

## Mudancas previstas

- Atualizar `Manifesto-Fontes.csv` com `ultimo_ciclo = CICLO-0011` para o bloco inteiro.
- Reconciliar `Estado-Integracao.json`, `Relatorio-Acumulado.md` e `Registro-de-Decisoes.md` com a nova cobertura.
- Produzir artefatos de ciclo que distingam triagem, duplicatas, irrelevantes e fontes ainda nao avaliadas.
- Manter `Checksums-Antes.txt` e `Checksums-Depois.txt` iguais, porque nao ha edicao de notas no vault neste ciclo.

## Riscos

- Nao confundir cobertura de metadados com leitura profunda de todas as 422 fontes.
- Nao atribuir a este ciclo analise completa que nao foi realizada.
- Manter segredos fora dos artefatos publicos do controle.

## Validacao

- Manifesto e estado refletem a cobertura real.
- A cadeia de checksums do vault permanece estavel.
- O proximo item avanca para `SRC-000501`.
