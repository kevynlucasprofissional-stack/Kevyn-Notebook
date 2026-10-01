---
Resumo: Preservação da qualidade vetorial em composições.
Contexto: Curso de Motion Graphics (M06 Character Animation).
tags:
  - "#after_effects"
  - "#vetor"
  - "#tecnico"
ID único: 20251123022848-tsqw0p
created: 2025-11-23
---
# Collapse Transformations (Rasterização Contínua)

## Conceito
O botão 'Collapse Transformations' (ícone de sol) no After Effects tem dupla função. Para camadas vetoriais (AI, EPS), ele ativa a Rasterização Contínua, forçando o AE a recalcular o vetor a cada frame, mantendo a nitidez perfeita em qualquer escala (evita pixelização). Para pré-composições, ele 'colapsa' a estrutura, fazendo com que as camadas internas da pré-comp interajam diretamente com a comp principal (ignorando a resolução/cortes da pré-comp) e permitindo transformações 3D complexas.

## Importância
Essencial para trabalhar com logos e ilustrações vetoriais sem perda de qualidade e para rigs de personagens complexos.

## Insight
Isso se conecta com [[Puppet Tool - Tipos de Pinos]] porque o Collapse deve estar DESLIGADO ao usar Puppet Tool em vetores, pois a malha precisa de limites definidos de rasterização.

### Conexões:
- [[Puppet Tool - Tipos de Pinos]]
- [[Rigg ou Rigging no After Effects]]

## Ação
- [ ] Sempre ativar o 'Solzinho' em logos vetoriais escalonados.
- [ ] Desativar ao aplicar efeitos de deformação que exigem limites de layer.

## Flashcards

O que o botão Collapse Transformations faz em vetores?::Ativa a rasterização contínua (nitidez infinita).

Deve-se usar Collapse Transformations com Puppet Tool em vetores?::Não, deve estar desligado.

O ícone do Collapse Transformations se assemelha a um ==sol==.
