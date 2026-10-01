---
Resumo: Código para gerar movimento aleatório em propriedades do After Effects.
Contexto: Arquivo 'Wiggle(Frequência,Amplitude).md'.
tags:
  - "#after_effects"
  - "#expressões"
  - "#motion"
ID único: 20251123023650-2iyetd
created: 2025-11-23
---
# Expressão Wiggle

## Conceito
A expressão `wiggle(freq, amp)` no After Effects gera valores aleatórios suaves para qualquer propriedade (posição, escala, opacidade). 
- **Frequência (freq):** Quantas vezes por segundo a oscilação ocorre. 
- **Amplitude (amp):** O quanto o valor varia (para mais ou para menos) em relação ao original. 
Para manter a escala uniforme (X e Y iguais) usa-se: `w=wiggle(freq,amp); [w[0], w[0]]`.

## Importância
Adiciona naturalidade e 'vida' a elementos estáticos ('handheld camera look') sem a necessidade de criar keyframes manuais tediosos.

## Insight
Isso se conecta com [[Variáveis]] porque você pode definir frequência e amplitude como variáveis ligadas a 'Sliders' para controlar a intensidade do wiggle durante a animação.

### Conexões:
- [[Time (Expressão)]]
- [[Variáveis]]

## Ação
- [ ] Aplicar um wiggle(2, 15) na posição de uma câmera para simular um operador humano segurando-a.

## Flashcards

O que significam os dois parâmetros do wiggle(freq, amp)?::Frequência (vezes por segundo) e Amplitude (intensidade do movimento).

Qual a sintaxe básica para movimento aleatório no After Effects?::wiggle(frequência, amplitude).
<!--SR:!2025-11-26,3,250-->

Como fazer o wiggle afetar a escala uniformemente (X e Y iguais)?::`w=wiggle(f,a); [w[0], w[0]]`
<!--SR:!2025-11-24,1,230-->
