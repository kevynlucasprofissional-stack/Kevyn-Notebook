---
Resumo: Técnica de renderização que simula sombreamento em fendas e cantos.
Contexto: Nota 'Ambient Oclusion (AO)' - Computação Gráfica/C4D.
tags:
  - "#3d"
  - "#render"
  - "#design"
ID único: 20251123021135-2ovwty
created: 2025-11-23
---
# Ambient Occlusion (AO)

## Conceito
Ambient Occlusion (AO) é um método de sombreamento usado em computação gráfica 3D que calcula o quão exposto cada ponto da cena está à iluminação ambiente. Na prática, ele escurece áreas onde a luz tem dificuldade de chegar, como cantos, fendas e áreas de contato entre objetos, criando profundidade visual. No contexto de produção (C4D), o 'pass' de AO é frequentemente renderizado sem texturas (tudo branco/cinza) para servir como mapa de sombras ou para comparações de 'Clay Render' (antes e depois).

## Importância
Adiciona realismo e peso aos objetos 3D, impedindo que pareçam estar flutuando e destacando detalhes geométricos.

## Insight
Isso se conecta com [[Alpha Channel e HDRI]] pois ambos são componentes de uma pipeline de composição (compositing) profissional.

### Conexões:
- [[Alpha Channel e HDRI]]
- [[Advanced Spill Suppressor]]

## Ação
- [ ] Ativar o AO nas configurações de render para aumentar o realismo de contato dos objetos.
- [ ] Usar o render de AO como máscara de multiplicação na pós-produção.

## Flashcards

O que o Ambient Occlusion (AO) simula?::O sombreamento em fendas, cantos e áreas de contato onde a luz ambiente é ocluída.

O render de AO é frequentemente usado para mostrar a cena ==sem texturas== (Clay Render).
