---
id: controle-curadoria-originais
titulo: Controle de curadoria dos arquivos originais
tipo: infraestrutura
status: ativo
profundidade: avancada
versao_schema: "1.0"
versao_conteudo: "1.2"
idioma: pt-BR
data_criacao: 2026-09-28
ultima_revisao: 2026-10-08
tags:
  - curadoria/fontes
  - infraestrutura/controle
---

# Controle de curadoria dos arquivos originais

## Finalidade

Este diretório controla a leitura progressiva de `000-Originais/` e a incorporação rastreável de conhecimento à camada canônica do Kevyn Notebook.

A fonte de verdade operacional é:

- `Controle-Curadoria-Originais.csv`

O painel de leitura é:

- [[Painel de curadoria dos originais]]

## Princípio de relevância

A pergunta central não é **"Kevyn possuiu ou leu este arquivo?"**.

A pergunta central é:

> **Este arquivo contém informação sobre Kevyn — sua história, trajetória, pensamentos, experiências, relações, decisões, identidade ou contexto — ou contém principalmente informação que ele consumiu?**

Materiais externos, livros, PDFs de estudo, referências técnicas e conteúdos de terceiros não recebem relevância alta apenas por estarem no acervo.

Diários, reflexões autorais, registros autobiográficos, conversas em que Kevyn fala de si, transcrições, registros profissionais contextualizados, documentos produzidos pelo próprio Kevyn e outras fontes primárias tendem a merecer atenção maior — mas **a nota final só deve ser atribuída após leitura suficiente do conteúdo**.

Não pontue por nome de arquivo, pasta ou extensão isoladamente.

## Escala 0–10

| Nota | Classe | Critério |
|---:|---|---|
| 0 | irrelevante | não acrescenta informação relevante sobre Kevyn ao propósito do Notebook |
| 1–3 | baixa | relação indireta, contextual ou fraca |
| 4–6 | moderada | contém informação útil, mas não central |
| 7–9 | alta | contém informação importante sobre Kevyn e merece curadoria cuidadosa |
| 10 | altíssima | fonte excepcionalmente valiosa, direta e representativa da história, experiência, pensamento ou identidade de Kevyn |

### Regra de nota 0

`relevancia = 0` **não autoriza exclusão**.

A nota apenas registra irrelevância curatorial. A remoção física exige decisão posterior e explícita em `decisao_remocao`.

## Estados controlados

### `analisado`

- `nao`
- `parcial`
- `sim`

### `utilizado_na_canonica`

- `nao`
- `parcial`
- `sim`

### `status`

Use preferencialmente:

- `nao_analisado`
- `em_analise`
- `analisado_aguardando_curadoria`
- `integrado_parcialmente`
- `integrado`
- `revisitar`
- `irrelevante_confirmado`

Registros importados do controle anterior podem aparecer temporariamente como:

- `integrado_legado`
- `integrado_parcialmente_legado`

Esses estados preservam trabalho anterior sem fingir que a nova nota 0–10 já foi atribuída.

### `revisitar`

- `nao_avaliado`
- `nao`
- `sim`

### `decisao_remocao`

- `nao_avaliado`
- `manter`
- `candidato`
- `bloqueado`

Mesmo `candidato` não executa remoção. É somente decisão registrada.

## Campos

| Campo | Função |
|---|---|
| `id_curadoria` | identificador estável deste controle |
| `fonte_id_legado` | ID de controles anteriores, quando foi possível reconciliar |
| `arquivo` | basename do arquivo |
| `caminho` | caminho exato no repositório |
| `tipo` | extensão/tipo |
| `tamanho_bytes` | tamanho do blob atual |
| `git_blob_sha` | identificador Git do blob; **não é SHA-256** |
| `sha256` | SHA-256 conhecido; pode ficar vazio até ser calculado/recuperado |
| `relevancia` | nota curatorial 0–10, somente após análise |
| `relevancia_legada` | classificação anterior preservada sem conversão arbitrária |
| `status` | estado global da curadoria |
| `analisado` | não/parcial/sim |
| `utilizado_na_canonica` | não/parcial/sim |
| `uso` | descrição sintética de como a fonte foi usada |
| `notas_canonicas` | wikilinks separados por ponto e vírgula |
| `revisitar` | necessidade de nova leitura |
| `decisao_remocao` | decisão curatorial separada da nota de relevância |
| `data_ultima_curadoria` | data ISO |
| `curador` | pessoa/agente responsável |
| `observacoes` | contexto, limites e histórico |

## Fila prioritária

A prioridade é calculada a partir do controle, nesta ordem:

1. relevância **10** e `utilizado_na_canonica != sim`;
2. relevância **7–9** e ainda não utilizada ou utilizada parcialmente;
3. relevância **4–6** ainda não utilizada;
4. arquivos marcados `revisitar = sim`;
5. arquivos ainda sem análise/nota;
6. relevância **1–3**;
7. relevância **0** fica fora da fila de enriquecimento e entra apenas em revisão de retenção.

O [[Painel de curadoria dos originais]] apresenta essa fila dinamicamente quando DataviewJS está disponível.

Sem Dataview, abra o CSV e filtre por `relevancia`, `utilizado_na_canonica`, `analisado` e `revisitar`.

## Fluxo obrigatório

```text
arquivo original
  → leitura/análise
  → nota de relevância 0–10
  → extração de evidências/claims
  → comparação com a camada canônica existente
  → incorporação total, parcial ou nenhuma
  → registro das notas canônicas relacionadas
  → atualização deste controle
```

Ao incorporar conhecimento, mantenha a cadeia:

`arquivo original → evidência → claim/síntese → nota canônica`

Para granularidade de evidência e claims, continue usando:

- `98-Pendencias-e-controles/Controle-Integracao/Matriz-Evidencias.csv`
- `98-Pendencias-e-controles/Controle-Integracao/Matriz-Claims.csv`

Este controle não substitui essas matrizes; ele responde **qual fonte merece atenção, em que estado está e onde foi utilizada**.

## Migração inicial

O controle foi criado a partir da árvore atual de `000-Originais/`.

Quando um caminho pôde ser reconciliado de forma inequívoca por sufixo com `Controle-Integracao/Matriz-Cobertura.csv`, foram preservados:

- `fonte_id_legado`;
- SHA-256 já conhecido;
- status anterior de análise/integração;
- relevância categórica legada;
- observações anteriores;
- notas de destino encontradas em `Matriz-Claims.csv`.

**Nenhuma relevância numérica 0–10 foi inferida automaticamente da classificação antiga.** Isso evita transformar `nucleo_a`, `nucleo_b` etc. em notas arbitrárias.

## Pré-seleção inicial de alta prioridade

A primeira fila não deve ser escolhida aleatoriamente a partir dos 12 mil arquivos.

Foi concluído um pré-processamento em dois filtros — estrutura/nome e leitura direta de conteúdo no GitHub — que resultou em **70 fontes prioritárias**:

- [[Pré-seleção de 70 fontes prioritárias]]

A lista usa `P0/P1/P2` apenas para ordenar a curadoria. Essas classes **não substituem** a nota oficial `relevancia = 0–10`, que continua exigindo análise suficiente do arquivo e atualização de `Controle-Curadoria-Originais.csv`.

## Integração de outubro de 2026

**Ingestão 08/10/2026:** foram adicionados ao CSV central sete registros novos (cinco `.md` e dois `.m4a`) do commit `e569fa2`. As notas 0–10 para transcrições e documentos refletem leitura textual; os áudios pareados estão como `analisado=parcial` e `revisitar=sim` por ausência de escuta independente. As datas reais das gravações são incertas; o dia 08/10/2026 representa data de curadoria. Ver [[Perguntas investigativas - outubro de 2026]].
