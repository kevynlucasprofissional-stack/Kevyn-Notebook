---
Resumo: Plugin de pós-produção para aplicação de desfoque de movimento baseado em vetores de movimento.
Contexto: Arquivo RSMB.md - Ferramentas de pós-produção para Motion Design.
tags:
  - "#motion_design"
  - "#vfx"
  - "#after_effects"
ID único: 20251123023753-a2o82i
created: 2025-11-23
---
# RSMB (Real Smart Motion Blur)

## Conceito
O RSMB (Real Smart Motion Blur) é um plugin de terceiros utilizado em softwares de composição como After Effects para aplicar desfoque de movimento (motion blur) de alta qualidade em filmagens ou renderizações 3D que não possuem o efeito nativo. Diferente do desfoque de movimento padrão que apenas mistura frames (frame blending), o RSMB utiliza algoritmos de rastreamento de pixels para calcular vetores de movimento, gerando um desfoque mais natural e fluido, essencial para integrar elementos 3D em cenas reais ou suavizar animações com taxas de quadros baixas.

## Importância
Resolve o problema de renderizações 3D 'duras' e artificiais ou filmagens com shutter speed alto (sem rastro), conferindo realismo cinemático e fluidez visual profissional sem o custo computacional de renderizar o motion blur nativamente no 3D.

## Insight
Isso se conecta com [[Renderização e finalização]] porque o uso do RSMB permite renderizar o 3D sem motion blur (mais rápido) e aplicar o efeito na pós-produção, otimizando drasticamente o tempo de workflow.

### Conexões:
- [[Renderização e finalização]]
- [[Renderização com o After Effects do Projeto com pós-produção finalizada]]

## Ação
- [ ] Instalar o plugin RSMB no After Effects.
- [ ] Testar a aplicação em um render 3D sem motion blur nativo.

## Flashcards

O que significa a sigla RSMB no contexto de Motion Design?::Real Smart Motion Blur.
<!--SR:!2025-11-25,2,248-->

Qual a principal vantagem do RSMB sobre o motion blur nativo de renderizadores 3D?::Economia de tempo de renderização (aplicação em pós-produção).

O RSMB funciona rastreando o movimento dos ==pixels== para criar vetores de desfoque.
<!--SR:!2025-11-24,1,230-->
