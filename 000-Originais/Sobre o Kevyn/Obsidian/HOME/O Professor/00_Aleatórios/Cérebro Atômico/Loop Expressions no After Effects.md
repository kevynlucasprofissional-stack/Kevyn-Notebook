---
Resumo: Automação de repetição de keyframes via código.
Contexto: Curso de Motion Graphics (Notas de Aula).
tags:
  - "#expressões"
  - "#automação"
ID único: 20251123022848-2wbivg
created: 2025-11-23
---
# Loop Expressions no After Effects

## Conceito
As expressões de Loop no After Effects automatizam a repetição de animações sem a necessidade de copiar e colar keyframes. loopOut() repete a animação após o último keyframe. loopIn() repete antes do primeiro. O modo mais comum é o 'cycle' (reinicia do começo), mas existe o 'pingpong' (vai e volta) e 'continue' (continua a trajetória). Atenção: Não funciona diretamente em propriedades de 'Path' (caminhos de forma) a menos que a camada seja pré-composta e o Time Remap seja usado.

## Importância
Economiza tempo drástico em animações cíclicas (andar, piscar, fundos em movimento) e mantém a timeline limpa e editável.

## Insight
Isso se conecta com [[Micro-hábitos de 5 Minutos]] através da metáfora da automação: assim como o loop repete uma ação sem esforço adicional, o micro-hábito visa automatizar o comportamento.

### Conexões:
- [[Puppet Tool - Tipos de Pinos]]
- [[Math.round() - Expressão]]

## Ação
- [ ] Aplicar loopOut('pingpong') em animações de 'respiro' ou flutuação.
- [ ] Usar Time Remap para loopar Shape Layers complexos.

## Flashcards

Qual expressão repete a animação após o último keyframe?::loopOut().

Qual modo de loop faz a animação ir e voltar?::'pingpong'.
<!--SR:!2025-11-26,3,250-->

É possível aplicar loopOut diretamente em um Path?::Não, requer Time Remap ou pré-composição.
