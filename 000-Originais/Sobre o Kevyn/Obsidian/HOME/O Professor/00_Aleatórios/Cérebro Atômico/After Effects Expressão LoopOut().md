---
Resumo: Repetição de animação pós-keyframes.
Contexto: Expressões AE.md
tags:
  - "#aftereffects"
  - "#motion"
ID único: 20251123022731-5d7fft
created: 2025-11-23
---
# After Effects: Expressão LoopOut()

## Conceito
A expressão `loopOut()` no After Effects instrui a propriedade a repetir os keyframes existentes após o último keyframe na linha do tempo. Pode assumir modos como 'Cycle' (reinicia do primeiro frame), 'Pingpong' (vai e volta) ou 'Continue' (segue a inércia). Por padrão, sem argumentos, age como 'Cycle'.

## Importância
Automatiza movimentos repetitivos sem a necessidade de copiar e colar keyframes infinitamente.

## Insight
Isso se conecta com [[After Effects: Expressão LoopIn()]] que realiza a função inversa (antes dos keyframes).

### Conexões:
- [[After Effects: Expressão LoopIn()]]
- [[After Effects: Expressão Wiggle]]

## Ação
- [ ] Aplicar loopOut('pingpong') em animações de oscilação.

## Flashcards

O que a expressão loopOut() faz?::Repete a animação após o último keyframe.

Qual modo do loopOut faz a animação ir e voltar?::Pingpong.
