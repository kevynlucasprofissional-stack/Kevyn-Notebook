---
titulo: "Modelos YAML e modelos de notas"
tipo: anexo_operacional
versao: "1.0"
data: 2026-06-17
---

# Modelos YAML e modelos de notas

## 1. Como usar este anexo

Os modelos abaixo são **contratos de dados**, não formulários que devam ser preenchidos mecanicamente. Cada tipo de nota possui:

1. uma função no sistema;
2. propriedades obrigatórias;
3. propriedades condicionais;
4. seções mínimas;
5. critérios de conclusão;
6. exemplos de links semanticamente justificáveis.

Uma IA deve adaptar os nomes dos tipos e relações ao domínio, mas preservar três princípios:

- uma nota deve possuir um tipo ontológico principal;
- propriedades usadas em consultas devem ter valores controlados;
- justificativas extensas pertencem ao corpo da nota, não a campos usados como filtros.

## 2. Convenções universais de propriedades

### 2.1. Formato dos nomes

Use `snake_case`, sem espaços, acentos ou pontuação:

```yaml
tipo: conceito
grau_confianca: alto
data_criacao: 2026-06-17
```

Evite criar propriedades equivalentes com grafias diferentes:

```yaml
# Ruim
grau-de-confianca: alto
grau_confianca: alta
nivael_de_confianca: forte
```

### 2.2. Tipos estáveis

| Necessidade | Tipo recomendado | Exemplo |
|---|---|---|
| identificador legível | texto | `id: conceito-genealogia` |
| classificação única | texto controlado | `tipo: conceito` |
| múltiplas categorias | lista | `tags: [filosofia, epistemologia]` |
| relações com notas | lista de links | `autores: ["[[Friedrich Nietzsche]]"]` |
| verdadeiro/falso | checkbox/booleano | `revisado: true` |
| data | data ISO | `ultima_revisao: 2026-06-17` |
| número ordenável | número | `prioridade: 2` |
| explicação longa | corpo da nota | seção `## Justificativa` |

Evite objetos YAML profundamente aninhados quando o cofre será mantido pela interface de propriedades do Obsidian. Prefira campos planos, listas e notas de relação próprias.

### 2.3. Vocabulários controlados sugeridos

```yaml
status:
  - rascunho
  - em_pesquisa
  - em_revisao
  - revisado
  - auditado
  - arquivado

grau_confianca:
  - alto
  - medio_alto
  - medio
  - medio_baixo
  - baixo
  - nao_avaliado

risco_interpretativo:
  - alto
  - medio
  - baixo
  - nao_aplicavel

profundidade:
  - indice
  - introdutoria
  - intermediaria
  - avancada
  - dossie

camada_evidencia:
  - fato_documentado
  - relacao_conceitual
  - interpretacao_especializada
  - hipotese_de_trabalho
  - recurso_pedagogico
  - representacao_visual
```

O domínio pode substituir `camada_evidencia` por outro modelo, como:

- medicina: diretriz, ensaio clínico, estudo observacional, hipótese;
- direito: legislação, precedente, doutrina, interpretação;
- história: fonte primária, reconstrução historiográfica, controvérsia;
- produto: especificação oficial, teste independente, relato de usuário;
- engenharia: requisito, decisão arquitetural, experimento, incidente.

### 2.4. Campos de versão

Separe versão do schema, versão do conteúdo e status editorial:

```yaml
versao_schema: "1.0"
versao_conteudo: "1.3"
status: revisado
```

Não use valores como `revisado_v5`, pois isso impede filtros limpos e mistura dois eixos.

### 2.5. Datas

```yaml
data_criacao: 2026-06-17
ultima_revisao: 2026-06-17
proxima_revisao: 2026-09-17
```

Use datas reais. Quando uma data for desconhecida, omita o campo ou use `null` conforme a política declarada. Não invente precisão.

### 2.6. Aliases

```yaml
aliases:
  - Genealogia nietzschiana
  - Método genealógico
```

Use aliases quando houver:

- nome completo e abreviação;
- título original e título traduzido;
- nome histórico e nome atual;
- sigla amplamente empregada;
- grafia alternativa relevante.

Não use aliases para palavras apenas vagamente relacionadas; isso cria autocompletar enganoso.

### 2.7. Tags

```yaml
tags:
  - dominio/filosofia
  - tipo/conceito
  - status/revisado
```

Tags devem apoiar filtros transversais. Não duplique em tags tudo o que já está em propriedades. Um cofre pode usar apenas:

- `dominio/...` para áreas amplas;
- `workflow/...` para estados especiais;
- `alerta/...` para revisão, risco ou pendência.

### 2.8. Links em propriedades

```yaml
autores_relacionados:
  - "[[Friedrich Nietzsche]]"
  - "[[Michel Foucault]]"

conceitos_relacionados:
  - "[[Genealogia]]"
  - "[[Poder]]"
```

Aspas evitam ambiguidades de parsing. Todo destino deve existir no inventário ou ser registrado como pendência explícita.

## 3. Schema-base universal

Use este conjunto como ponto de partida, não como obrigação de colocar todos os campos em toda nota:

```yaml
---
id: ""
titulo: ""
aliases: []
tipo: ""
subtipo: ""
status: rascunho
profundidade: introdutoria
versao_schema: "1.0"
versao_conteudo: "1.0"
idioma: pt-BR
data_criacao: 2026-06-17
ultima_revisao: 2026-06-17
responsavel: ""
grau_confianca: nao_avaliado
risco_interpretativo: nao_aplicavel
camadas_evidencia: []
tags: []
notas_relacionadas: []
fontes_primarias: []
fontes_secundarias: []
pendencias: []
---
```

### Obrigatório em todas as notas de conteúdo

```yaml
id: ""
titulo: ""
tipo: ""
status: rascunho
versao_schema: "1.0"
data_criacao: 2026-06-17
ultima_revisao: 2026-06-17
```

### Condicional

- `grau_confianca`: obrigatório quando a nota faz afirmações contestáveis;
- `camadas_evidencia`: obrigatório quando há gradação epistemológica;
- `fontes_primarias` e `fontes_secundarias`: obrigatórios para notas de pesquisa;
- `responsavel`: útil em cofres colaborativos;
- `proxima_revisao`: útil em domínios voláteis;
- `validade_ate`: útil em normas, preços, leis ou políticas.

## 4. Modelo — Entidade ou pessoa

### Função

Representar uma entidade relativamente estável: pessoa, organização, local, produto, instituição, escola, personagem ou componente.

### YAML

```yaml
---
id: autor-friedrich-nietzsche
titulo: "Friedrich Nietzsche"
aliases:
  - Nietzsche
tipo: entidade
subtipo: autor
status: revisado
profundidade: avancada
versao_schema: "1.0"
versao_conteudo: "1.2"
data_criacao: 2026-06-01
ultima_revisao: 2026-06-17
grau_confianca: alto
camadas_evidencia:
  - fato_documentado
  - interpretacao_especializada
tags:
  - dominio/filosofia
  - tipo/autor
obras_principais:
  - "[[Além do Bem e do Mal]]"
  - "[[Genealogia da Moral]]"
conceitos_principais:
  - "[[Genealogia]]"
  - "[[Ressentimento]]"
contextos:
  - "[[Filosofia alemã do século XIX]]"
fontes_primarias:
  - "[[Genealogia da Moral — edição crítica]]"
fontes_secundarias:
  - "[[SEP — Friedrich Nietzsche]]"
pendencias: []
---
```

### Corpo

```markdown
# Friedrich Nietzsche

> [!summary] Síntese
> Uma frase específica que situe a entidade no escopo do cofre.

## Por que esta entidade existe no cofre

Explique sua função no recorte, sem transformar importância em elogio genérico.

## Contexto

## Ideias, funções ou características centrais

## Relações principais

- [[Relação — Nietzsche transforma a crítica da moral em genealogia]] — transformação conceitual documentada.
- [[Relação — Nietzsche e Freud como crítica da consciência]] — paralelo comparativo, não filiação demonstrada.

## Obras, eventos ou componentes associados

## Controvérsias e limites

## Fontes

## Pendências editoriais
```

### Critério de conclusão

- explica por que a entidade pertence ao escopo;
- não é apenas biografia ou ficha técnica;
- conecta-se a pelo menos um contexto, um elemento produzido/associado e uma relação significativa;
- distingue fatos de interpretações;
- possui fontes adequadas ao domínio.

## 5. Modelo — Conceito

### Função

Definir uma unidade conceitual, incluindo origem, variações, aplicação e controvérsias.

### YAML

```yaml
---
id: conceito-genealogia
titulo: "Genealogia"
aliases:
  - método genealógico
tipo: conceito
status: revisado
profundidade: avancada
versao_schema: "1.0"
versao_conteudo: "1.1"
data_criacao: 2026-06-01
ultima_revisao: 2026-06-17
grau_confianca: medio_alto
risco_interpretativo: medio
camadas_evidencia:
  - relacao_conceitual
  - interpretacao_especializada
autores_associados:
  - "[[Friedrich Nietzsche]]"
  - "[[Michel Foucault]]"
obras_associadas:
  - "[[Genealogia da Moral]]"
  - "[[Vigiar e Punir]]"
conceitos_relacionados:
  - "[[Origem]]"
  - "[[Emergência]]"
  - "[[História efetiva]]"
tags:
  - dominio/filosofia
  - tipo/conceito
fontes_primarias: []
fontes_secundarias: []
pendencias: []
---
```

### Corpo

```markdown
# Genealogia

## Definição operacional

Defina o conceito para o propósito deste cofre. Evite começar por uma fórmula universal falsa.

## Origem e contexto

## Variações por autor, período ou disciplina

### Em [[Friedrich Nietzsche]]

### Em [[Michel Foucault]]

## O que o conceito não significa

## Relações com outros conceitos

## Exemplos de aplicação

## Controvérsias, traduções e ambiguidades

## Fontes e evidências

## Síntese comparativa
```

### Critério de conclusão

- oferece definição operacional;
- mostra variação, não identidade automática entre usos;
- contém exemplos ou aplicações;
- explicita limites e confusões comuns;
- liga-se às entidades, obras ou eventos em que o conceito realmente opera.

## 6. Modelo — Obra, documento ou artefato

### YAML

```yaml
---
id: obra-genealogia-da-moral
titulo: "Genealogia da Moral"
aliases:
  - Para a genealogia da moral
tipo: obra
subtipo: livro
status: revisado
profundidade: avancada
versao_schema: "1.0"
versao_conteudo: "1.0"
data_criacao: 2026-06-01
ultima_revisao: 2026-06-17
autores:
  - "[[Friedrich Nietzsche]]"
ano_original: 1887
idioma_original: de
grau_confianca: alto
conceitos_desenvolvidos:
  - "[[Ressentimento]]"
  - "[[Má consciência]]"
  - "[[Genealogia]]"
contextos:
  - "[[Crítica da moral]]"
tags:
  - dominio/filosofia
  - tipo/obra
fontes_primarias: []
fontes_secundarias: []
pendencias: []
---
```

### Corpo

```markdown
# Genealogia da Moral

## Identificação

- Autor:
- Data e edição original:
- Edição consultada:
- Tipo de obra:

## Pergunta ou problema central

## Estrutura da obra

## Tese ou contribuição principal

## Conceitos desenvolvidos

## Relação com outras obras

## Recepção e controvérsias

## Passagens ou seções-chave

| Localização | Tema | Uso no cofre | Observação |
|---|---|---|---|
| Prefácio, §3 | origem dos valores | [[Genealogia]] | verificar edição |

## Fontes secundárias

## Pendências de leitura
```

### Critério de conclusão

- diferencia resumo de interpretação;
- registra edição e localização quando relevante;
- liga conceitos realmente desenvolvidos na obra;
- não atribui à obra teses que pertencem apenas a comentadores.

## 7. Modelo — Evento ou acontecimento

### YAML

```yaml
---
id: evento-conferencia-x-2026
titulo: "Conferência X de 2026"
tipo: evento
subtipo: conferencia
status: revisado
versao_schema: "1.0"
versao_conteudo: "1.0"
data_inicio: 2026-06-20
data_fim: 2026-06-22
local: "[[Rio Verde]]"
organizadores:
  - "[[Organização Exemplo]]"
participantes: []
causas_relacionadas: []
consequencias_relacionadas: []
fontes_primarias: []
fontes_secundarias: []
tags:
  - tipo/evento
pendencias: []
---
```

### Corpo

```markdown
# Conferência X de 2026

## O que ocorreu

## Contexto anterior

## Linha do tempo

## Participantes e papéis

## Causas e condições

## Consequências imediatas

## Consequências posteriores

## Interpretações divergentes

## Fontes
```

## 8. Modelo — Corrente, categoria ou tradição

### YAML

```yaml
---
id: corrente-pos-estruturalismo
titulo: "Pós-estruturalismo"
tipo: corrente
status: em_revisao
profundidade: avancada
versao_schema: "1.0"
versao_conteudo: "1.0"
grau_confianca: medio
risco_interpretativo: alto
camadas_evidencia:
  - interpretacao_especializada
autores_associados:
  - "[[Jacques Derrida]]"
  - "[[Gilles Deleuze]]"
  - "[[Michel Foucault]]"
conceitos_associados: []
contextos:
  - "[[Filosofia francesa do século XX]]"
tags:
  - dominio/filosofia
  - tipo/corrente
fontes_primarias: []
fontes_secundarias: []
pendencias:
  - "Evitar tratar o rótulo como doutrina unitária."
---
```

### Corpo

```markdown
# Pós-estruturalismo

## Definição mínima e uso editorial

## Origem do rótulo

## Critérios de inclusão

## Autores frequentemente associados

## Diferenças internas

## Correntes próximas e contrastantes

## Limites e críticas ao rótulo

## Como representar no grafo

## Fontes
```

## 9. Modelo — Relação semântica

### Função

Tornar auditável uma ligação que carrega uma afirmação relevante. Relações triviais não precisam virar notas próprias; relações causais, históricas, conceituais, críticas ou controversas geralmente precisam.

### Vocabulário universal inicial

```yaml
tipo_relacao:
  - parte_de
  - instancia_de
  - produzido_por
  - ocorre_em
  - anterior_a
  - posterior_a
  - causa
  - contribui_para
  - responde_a
  - critica
  - contradiz
  - amplia
  - transforma
  - aplica
  - exemplifica
  - compara_com
  - depende_de
  - evidencia
  - contextualiza
  - recebe_influencia_documentada_de
  - apropriacao_conceitual_de
  - paralelo_tematica_com
  - hipotese_de_relacao
```

Não use `relacionado_a` como categoria final. É um rótulo provisório que deve ser refinado.

### YAML

```yaml
---
id: relacao-nietzsche-foucault-genealogia
titulo: "Nietzsche → Foucault — transformação da genealogia"
tipo: relacao
subtipo: autor_autor
status: revisado
profundidade: dossie
versao_schema: "1.0"
versao_conteudo: "1.1"
sujeito:
  - "[[Friedrich Nietzsche]]"
objeto:
  - "[[Michel Foucault]]"
tipo_relacao: transforma
orientacao: direcionada
grau_confianca: alto
risco_interpretativo: medio
camadas_evidencia:
  - fato_documentado
  - relacao_conceitual
  - interpretacao_especializada
conceitos_mediadores:
  - "[[Genealogia]]"
obras_evidencia:
  - "[[Genealogia da Moral]]"
  - "[[Nietzsche, a genealogia, a história]]"
fontes_primarias: []
fontes_secundarias: []
pendencias: []
---
```

### Corpo

```markdown
# Nietzsche → Foucault — transformação da genealogia

## Tese da relação

Declare exatamente o que a ligação afirma.

## Tipo e direção

- Tipo: transformação conceitual
- Direção: Nietzsche → Foucault
- Simetria: não

## Evidência histórica

Há leitura, citação, declaração, correspondência, curso, documentação ou contato verificável?

## Evidência conceitual

Compare problema, método e vocabulário antes e depois.

## Evidência contrária e limites

## Fontes favoráveis

## Fontes críticas ou alternativas

## Grau de confiança e justificativa

## Como representar no grafo

- aresta dirigida;
- grupo semântico: recepção;
- não usar como prova independente;
- abrir esta nota para ver a justificativa.

## Veredito editorial
```

### Teste de criação de uma nota de relação

Crie a nota apenas quando pelo menos uma condição for verdadeira:

- a relação é central para a pergunta do cofre;
- a ligação pode ser contestada;
- há mais de um tipo de evidência;
- a direção ou causalidade importa;
- a relação precisa de fontes próprias;
- a ligação deve aparecer em Canvas ou trilha.

Uma ligação simples como “obra escrita por autor” pode permanecer como propriedade e wikilink.

## 10. Modelo — Controvérsia

### YAML

```yaml
---
id: controversia-foucault-normatividade
titulo: "Foucault e o problema da normatividade"
tipo: controversia
status: em_revisao
profundidade: dossie
versao_schema: "1.0"
versao_conteudo: "1.0"
grau_confianca: medio_alto
risco_interpretativo: alto
camadas_evidencia:
  - interpretacao_especializada
participantes:
  - "[[Michel Foucault]]"
  - "[[Jürgen Habermas]]"
conceitos_em_disputa:
  - "[[Normatividade]]"
  - "[[Crítica]]"
obras_relevantes: []
fontes_primarias: []
fontes_secundarias: []
pendencias: []
---
```

### Corpo

```markdown
# Foucault e o problema da normatividade

## Pergunta em disputa

## Por que a controvérsia importa

## Posição A

### Argumentos

### Evidências

### Limites

## Posição B

### Argumentos

### Evidências

### Limites

## Posições intermediárias ou reformulações

## Pontos de consenso

## Pontos ainda abertos

## Veredito editorial prudente

## Bibliografia por posição
```

## 11. Modelo — Fonte

### Tipos de fonte

```yaml
subtipo:
  - fonte_primaria
  - artigo_revisado_por_pares
  - livro_academico
  - capitulo
  - enciclopedia_especializada
  - documentacao_oficial
  - norma
  - dataset
  - relato
  - comunidade
```

### YAML

```yaml
---
id: fonte-sep-nietzsche
titulo: "SEP — Friedrich Nietzsche"
tipo: fonte
subtipo: enciclopedia_especializada
status: revisado
versao_schema: "1.0"
autores: []
ano: null
url: ""
data_acesso: 2026-06-17
nivel_autoridade: alto
uso_permitido:
  - enquadramento
  - bibliografia
  - controversias
notas_sustentadas:
  - "[[Friedrich Nietzsche]]"
  - "[[Genealogia]]"
tags:
  - tipo/fonte
pendencias: []
---
```

### Corpo

```markdown
# SEP — Friedrich Nietzsche

## Referência completa

## Autoridade e escopo

## Principais contribuições para o cofre

## Afirmações que esta fonte sustenta

## Limitações

## Citações ou passagens localizadas

## Bibliografia derivada
```

## 12. Modelo — MOC

### YAML

```yaml
---
id: moc-conceitos-centrais
titulo: "MOC — Conceitos centrais"
tipo: moc
status: revisado
versao_schema: "1.0"
escopo:
  - "[[MOC — Geral]]"
criterio_organizacao: problema_e_percurso
publico:
  - iniciante
  - intermediario
tags:
  - tipo/moc
---
```

### Corpo

```markdown
# MOC — Conceitos centrais

> [!purpose] Função deste mapa
> Explique que pergunta o MOC ajuda a responder e para quem foi criado.

## Entrada recomendada

1. [[Conceito A]] — por que começar aqui.
2. [[Conceito B]] — qual passagem ele permite.

## Núcleo

### Problema 1

- [[Conceito A]] — função.
- [[Conceito C]] — função.

### Problema 2

- [[Conceito D]] — função.

## Comparações e controvérsias

## Trilhas sugeridas

## Lacunas e próximos desenvolvimentos
```

Um MOC não deve ser uma lista alfabética automática. Para listagem dinâmica, use Bases ou Dataview.

## 13. Modelo — Trilha de leitura ou percurso

```yaml
---
id: trilha-introducao-geral
titulo: "Trilha — Introdução geral"
tipo: trilha
status: revisado
versao_schema: "1.0"
nivel: iniciante
tempo_estimado_minutos: 120
pre_requisitos: []
resultados_esperados:
  - "Distinguir os principais tipos de nota."
notas_da_trilha:
  - "[[MOC — Geral]]"
  - "[[Conceito A]]"
  - "[[Controvérsia B]]"
---
```

```markdown
# Trilha — Introdução geral

## Para quem é

## O que o leitor deverá compreender

## Sequência

1. [[MOC — Geral]] — orientação inicial.
2. [[Conceito A]] — vocabulário necessário.
3. [[Entidade B]] — aplicação.
4. [[Controvérsia C]] — limites.

## Perguntas de verificação

## Próximas trilhas
```

## 14. Modelo — Decisão arquitetural

Útil para cofres técnicos, projetos, produtos e sistemas.

```yaml
---
id: adr-001-escolha-bases-ou-dataview
titulo: "ADR-001 — Usar Bases para vistas editáveis"
tipo: decisao_arquitetural
status: aceito
versao_schema: "1.0"
data_decisao: 2026-06-17
contexto: "[[Arquitetura do cofre]]"
decisores: []
alternativas:
  - "[[Alternativa — Dataview]]"
consequencias: []
---
```

```markdown
# ADR-001 — Usar Bases para vistas editáveis

## Contexto

## Decisão

## Alternativas consideradas

## Consequências positivas

## Consequências negativas

## Condições para revisão
```

## 15. Modelo — Auditoria

```yaml
---
id: auditoria-links-release-1-0
titulo: "Auditoria de links — release 1.0"
tipo: auditoria
subtipo: links
status: concluida
versao_schema: "1.0"
data_execucao: 2026-06-17
escopo_auditado: cofre_completo
metodo: script_e_amostragem
resultado: aprovado_com_ressalvas
falhas_criticas: 0
falhas_altas: 1
falhas_medias: 3
falhas_baixas: 8
responsavel: "IA + revisão humana"
---
```

```markdown
# Auditoria de links — release 1.0

## Objetivo

## Escopo e exclusões

## Método executado

## Métricas

## Achados

| Severidade | Arquivo | Problema | Evidência | Correção |
|---|---|---|---|---|

## Correções confirmadas

## Pendências assumidas

## Veredito
```

## 16. Modelo — Pendência qualificada

```yaml
---
id: pendencia-validar-relacao-a-b
titulo: "Validar relação entre A e B"
tipo: pendencia
status: aberta
prioridade: 2
versao_schema: "1.0"
origem: "[[Relação — A → B]]"
criterio_encerramento: "Encontrar fonte primária ou rebaixar a relação."
responsavel: ""
prazo: null
bloqueia_release: false
---
```

```markdown
# Validar relação entre A e B

## Problema observado

## Por que importa

## Evidência já disponível

## Próxima ação concreta

## Critério de encerramento
```

## 17. Modelos por domínio

### 17.1. História

Tipos adicionais:

- período;
- processo histórico;
- documento primário;
- ator coletivo;
- local;
- evento;
- controvérsia historiográfica.

Relações:

- precede;
- desencadeia;
- participa_de;
- documenta;
- interpreta;
- disputa_a_interpretacao_de.

### 17.2. Ciências

Tipos adicionais:

- hipótese;
- experimento;
- método;
- variável;
- resultado;
- teoria;
- dataset;
- replicação.

Relações:

- testa;
- corrobora;
- contradiz;
- mede;
- controla;
- replica;
- limita.

### 17.3. Direito

Tipos adicionais:

- norma;
- artigo;
- precedente;
- tribunal;
- tese jurídica;
- doutrina;
- caso;
- jurisdição.

Campos temporais obrigatórios:

```yaml
vigente: true
vigencia_inicio: 2026-01-01
vigencia_fim: null
jurisdicao: BR
ultima_verificacao: 2026-06-17
```

### 17.4. Empresa e produto

Tipos adicionais:

- requisito;
- iniciativa;
- decisão;
- risco;
- métrica;
- experimento;
- persona;
- concorrente;
- processo;
- incidente.

Relações:

- atende_requisito;
- mede;
- bloqueia;
- depende_de;
- mitiga;
- afeta;
- substitui;
- valida.

### 17.5. Literatura e artes

Tipos adicionais:

- obra;
- personagem;
- tema;
- motivo;
- escola;
- técnica;
- adaptação;
- recepção crítica.

Relações:

- aparece_em;
- simboliza;
- adapta;
- dialoga_com;
- parodia;
- influencia_documentadamente;
- aproxima_pedagogicamente.

## 18. Critérios para uma IA preencher modelos

Antes de salvar uma nota, a IA deve responder internamente:

1. Qual pergunta esta nota resolve?
2. Por que ela merece nota própria?
3. Qual é seu tipo principal?
4. Que propriedades serão realmente consultadas?
5. Quais links expressam relações demonstráveis?
6. Que afirmações exigem fonte?
7. Qual limitação ou controvérsia deve aparecer?
8. O texto está específico ou poderia servir a qualquer entidade?
9. Existe outra nota que deveria ser mesclada?
10. O título e o basename serão estáveis?

## 19. Teste antiboilerplate

Uma nota falha quando, após substituir nomes próprios, o texto continua praticamente igual ao de dezenas de outras notas.

Para reduzir isso:

- escreva primeiro a tese específica da nota;
- adapte a estrutura ao problema real;
- exija exemplos próprios;
- varie extensão de acordo com centralidade e dificuldade;
- compare notas do mesmo tipo por similaridade;
- revise manualmente uma amostra estratificada.

## 20. Checklist de schema

- [ ] Uma propriedade tem um único significado em todo o cofre.
- [ ] Valores categóricos pertencem a vocabulários documentados.
- [ ] Explicações longas não estão em campos de filtro.
- [ ] Datas usam ISO 8601.
- [ ] Links de propriedades apontam para alvos existentes.
- [ ] Não há propriedades quase duplicadas.
- [ ] Status e versão estão separados.
- [ ] Aliases são nomes reais, não palavras relacionadas.
- [ ] Tipos de nota são mutuamente inteligíveis.
- [ ] Campos obrigatórios estão presentes em 100% das notas aplicáveis.
