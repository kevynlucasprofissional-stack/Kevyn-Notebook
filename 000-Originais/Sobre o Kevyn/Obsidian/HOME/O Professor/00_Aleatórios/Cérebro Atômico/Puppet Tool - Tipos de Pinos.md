---
Resumo: Distinções entre ferramentas de marionete no After Effects.
Contexto: Curso de Motion Graphics (M06A05).
tags:
  - "#after_effects"
  - "#animacao"
  - "#tecnico"
ID único: 20251123022848-2r64il
created: 2025-11-23
---
# Puppet Tool - Tipos de Pinos

## Conceito
No After Effects, a Puppet Tool oferece diferentes tipos de pinos para controle de malha (mesh): 1) Puppet Position Pin: O padrão, controla apenas a posição (x,y). 2) Puppet Starch Pin: Endurece a área ao redor, prevenindo distorções indesejadas em áreas rígidas. 3) Puppet Bend Pin: Permite rotacionar e escalar a malha a partir do pino, ideal para articulações. 4) Puppet Advanced Pin: Combina posição, rotação e escala em um único controlador. 5) Puppet Overlap Pin: Define a ordem de empilhamento (Z-depth simulado) para controlar qual parte da malha fica sobre a outra.

## Importância
O uso correto de cada pino é crucial para evitar o aspecto de 'gelatina' em animações de personagens e garantir deformações orgânicas.

## Insight
Isso se conecta com [[Forward Kinematics (FK)]] porque os pinos Bend e Advanced são essenciais para simular articulações em cadeias FK sem rig complexo.

### Conexões:
- [[Forward Kinematics (FK)]]
- [[Loop Expressions no After Effects]]

## Ação
- [ ] Usar Starch Pins em torsos e cabeças para manter a forma.
- [ ] Substituir Position Pins por Advanced Pins em extremidades.

## Flashcards

Qual pino do Puppet Tool serve para endurecer uma área?::Puppet Starch Pin.
<!--SR:!2025-11-26,3,250-->

O Puppet Overlap Pin controla a ==profundidade (quem fica na frente)== da malha.

Qual pino combina rotação, escala e posição?::Puppet Advanced Pin.
<!--SR:!2025-11-26,3,250-->
