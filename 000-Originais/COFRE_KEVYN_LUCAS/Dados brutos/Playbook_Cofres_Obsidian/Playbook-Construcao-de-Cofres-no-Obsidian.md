---
titulo: "Playbook completo para construção de cofres no Obsidian"
tipo: manual
versao: "1.0"
data: 2026-06-17
status: publicado
idioma: pt-BR
aplicacao: universal
---

# Playbook completo para construção de cofres no Obsidian

## 0. Finalidade

Este manual ensina uma inteligência artificial a transformar um tema em um cofre Obsidian completo, coerente, conectado, auditável e pronto para uso.

O método foi criado a partir de:

- auditoria estrutural de um cofre real sobre filosofia pós-Nietzsche;
- reconstrução do processo de criação, comparação e correção de versões;
- documentação atual do Obsidian, Dataview, JSON Canvas e Templater;
- práticas comunitárias de MOCs, notas atômicas e redes de conhecimento.

O playbook não pressupõe que todo cofre deva ser uma enciclopédia. Ele pode ser adaptado a pesquisa acadêmica, estudo pessoal, documentação técnica, gestão de projetos, história, arte, literatura, medicina, direito, biologia, negócios ou qualquer outro campo.

## 1. Definições operacionais

### 1.1. Cofre

Uma pasta reconhecida pelo Obsidian como vault, contendo arquivos Markdown, anexos, configurações e, opcionalmente, arquivos Canvas, Bases e dependências de plugins.

### 1.2. Nota

Unidade legível e endereçável de conhecimento. Uma nota deve possuir um propósito principal identificável, mesmo quando contém seções internas.

### 1.3. Ontologia

Conjunto de tipos de entidade aceitos pelo cofre e das relações permitidas entre eles. Exemplos: pessoa, obra, conceito, evento, método, organização, lugar, controvérsia e fonte.

### 1.4. Relação semântica

Conexão cujo significado pode ser enunciado em uma frase. “A está relacionado com B” é insuficiente; “A critica B”, “A desenvolve o conceito B” ou “A ocorreu durante B” são relações semanticamente úteis.

### 1.5. MOC

Mapa de Conteúdo: nota curada que oferece caminhos de navegação e explica como um conjunto de notas se organiza. MOC é uma prática metodológica da comunidade, não um tipo de arquivo nativo especial do Obsidian.

### 1.6. Nota atômica

Nota centrada em uma entidade, afirmação, questão ou unidade de raciocínio principal. Atomicidade não significa obrigatoriamente brevidade; significa evitar misturar unidades que precisariam evoluir, ser citadas ou conectadas separadamente.

### 1.7. Auditoria

Verificação documentada que compara o estado real do cofre com critérios previamente definidos.

## 2. Princípios universais

### 2.1. O conteúdo antecede a interface

Graph View, Canvas, cores e dashboards devem representar uma modelagem já justificada. Não devem inventar a modelagem.

### 2.2. Link é afirmação

Todo link interno comunica ao leitor que existe uma conexão relevante. Inserir links apenas porque palavras coincidem produz ruído e distorce o grafo.

### 2.3. Metadado é contrato

Uma propriedade consultada por Dataview, Bases, Search ou scripts precisa ter nome, tipo e vocabulário estáveis. YAML válido é apenas o primeiro requisito.

### 2.4. Pastas organizam arquivos; MOCs organizam entendimento

Pastas fornecem localização exclusiva. MOCs permitem múltiplas perspectivas sem mover a nota. Tags filtram transversalmente. Links constroem relações contextuais. Nenhum mecanismo substitui todos os outros.

### 2.5. O grafo é derivado

O grafo mostra a consequência dos links. Ele não demonstra causalidade, importância, verdade, influência ou hierarquia.

### 2.6. Toda automação precisa de modo degradado

O cofre deve continuar legível sem Dataview, DataviewJS ou Templater. Plugins podem melhorar a experiência, mas o conhecimento principal deve permanecer em Markdown.

### 2.7. Auditoria deve testar o arquivo entregue

Um ZIP só está validado depois de ser extraído em ambiente limpo e reanalisado.

### 2.8. Não confundir uniformidade com qualidade

Templates devem padronizar estrutura e propriedades; o argumento e a densidade devem variar conforme a entidade e a evidência.

## 3. Classificação das práticas

| Categoria | Significado | Exemplos |
|---|---|---|
| Universal obrigatória | Necessária em quase qualquer cofre gerado por IA | escopo, schema, inventário, links válidos, README, auditoria pós-ZIP |
| Universal recomendada | Útil na maioria dos projetos | MOC inicial, propriedades controladas, changelog, pendências |
| Dependente do tema | Definida após pesquisa de domínio | tipos de entidade, relações, critérios de evidência, fontes prioritárias |
| Nativa do Obsidian | Funciona sem plugin comunitário | links, backlinks, propriedades, tags, Graph, Canvas, Templates, Bases |
| Dependente de plugin | Requer instalação e deve ser declarada | Dataview, DataviewJS, Templater |
| Opcional avançada | Acrescenta automação ou visualização | CLI, scripts externos, DataviewJS, painéis complexos |
| Falha bloqueante | Impede considerar o vault pronto | ZIP corrompido, links essenciais quebrados, YAML inválido, arquivos faltantes |
| Falha degradante | Não impede abertura, mas reduz qualidade | notas isoladas, boilerplate, MOC fraco, bibliografia inconsistente |

## 4. Mapa atual de recursos do Obsidian

### 4.1. Recursos nativos

- **Internal links:** wikilinks e links Markdown para arquivos, cabeçalhos e blocos.
- **Backlinks:** visualização de referências de entrada e menções não vinculadas.
- **Aliases:** nomes alternativos armazenados como lista na propriedade `aliases`.
- **Embeds/transclusões:** incorporação de notas, cabeçalhos, blocos e anexos com `![[...]]`.
- **Properties:** dados YAML com tipos globais por nome de propriedade.
- **Tags:** rótulos pesquisáveis, inclusive hierarquias com `/`.
- **Templates:** inserção de snippets e variáveis básicas de título, data e hora.
- **Graph View:** representação dos links internos como nós e linhas.
- **Canvas:** arquivos `.canvas` baseados em JSON Canvas, com nós, grupos e arestas rotuláveis.
- **Bases:** vistas nativas, editáveis, filtráveis e ordenáveis sobre propriedades.
- **Search:** consultas por texto, caminho, tag e propriedade.
- **Obsidian CLI:** automação e inspeção por terminal nas versões compatíveis.

### 4.2. Plugins relevantes

#### Dataview

Índice e mecanismo de consulta sobre metadados. É excelente para listas derivadas, auditorias dinâmicas, agrupamentos e cálculos. Dataview é predominantemente uma camada de exibição; não deve ser tratado como editor principal de dados.

#### DataviewJS

Executa JavaScript com acesso ao índice Dataview. Deve ser reservado para necessidades que DQL ou Bases não resolvam. Aumenta complexidade, risco de erro e dependência técnica.

#### Templater

Oferece variáveis, funções e JavaScript para criação dinâmica de notas. É útil para automação interativa, mas exige documentação de dependência e cautela com scripts.

### 4.3. Bases versus Dataview

Use **Bases** quando:

- deseja vistas nativas e editáveis;
- quer tabelas, listas, cartões ou mapas sobre propriedades;
- o filtro e a fórmula podem ser expressos no sistema nativo;
- portabilidade e baixa dependência são prioritárias.

Use **Dataview** quando:

- precisa de consultas derivadas complexas;
- quer listar relações, detectar lacunas ou agrupar dados de modo mais flexível;
- precisa combinar campos implícitos, links, tarefas e funções;
- o resultado será leitura, não edição dos dados.

Use **DataviewJS** apenas quando:

- a consulta não pode ser resolvida por Bases ou DQL;
- há justificativa clara de manutenção;
- o código possui comentários, tratamento de ausências e resultado alternativo.

## 5. Processo completo de construção

O processo possui 18 fases. Uma IA pode executar várias na mesma sessão, mas cada fase precisa produzir um artefato verificável antes da seguinte.

---

# FASE 1 — Interpretar a solicitação

## 5.1. Extrair a intenção real

A IA deve responder internamente:

1. Qual é o tema literal?
2. Qual problema o usuário quer resolver com o cofre?
3. O cofre será usado para estudar, pesquisar, publicar, operar ou decidir?
4. Quem é o leitor?
5. Qual profundidade é necessária?
6. O usuário espera neutralidade, argumentação, documentação, cronologia ou aplicação prática?
7. Quais formatos finais são obrigatórios?

## 5.2. Produzir uma ficha de escopo

```yaml
tema: ""
pergunta_central: ""
objetivo_primario: "estudo | pesquisa | operacao | documentacao | publicacao"
publico: ""
idioma: "pt-BR"
profundidade: "introdutoria | intermediaria | avancada | academica"
recorte_temporal: ""
recorte_geografico: ""
recorte_disciplinar: []
entregaveis: []
recursos_nativos_obrigatorios: []
plugins_permitidos: []
fontes_fornecidas: []
fontes_externas_permitidas: []
restricoes: []
```

## 5.3. Critério de conclusão

A fase termina quando qualquer pessoa consegue explicar, em duas frases, o que pertence e o que não pertence ao cofre.

---

# FASE 2 — Definir o escopo

## 5.4. Criar três fronteiras

### Fronteira temática

Quais assuntos pertencem ao núcleo, quais são contexto e quais são apenas adjacentes?

### Fronteira de profundidade

Cada entidade receberá verbete mínimo, nota padrão ou dossiê aprofundado?

### Fronteira de completude

O cofre pretende ser:

- panorâmico;
- representativo;
- exaustivo dentro de um recorte;
- modular e expansível;
- protótipo validado.

## 5.5. Matriz de prioridade

| Nível | Definição | Tratamento |
|---|---|---|
| Núcleo A | indispensável para responder à pergunta central | nota profunda, relações, fontes, MOC |
| Núcleo B | importante para explicar o núcleo A | nota padrão, links e fontes |
| Contexto C | melhora compreensão histórica ou conceitual | nota breve ou seção contextual |
| Adjacente D | potencial expansão futura | pendência qualificada, não verbete fictício |

## 5.6. Regra contra inflação

Uma entidade só entra se cumprir ao menos uma condição:

- responde diretamente à pergunta central;
- explica uma entidade do núcleo;
- representa uma posição indispensável;
- fornece contexto sem o qual uma relação seria enganosa;
- é necessária para uma trilha de leitura ou processo operacional.

---

# FASE 3 — Pesquisar e definir autoridade

## 5.7. Hierarquia de fontes

A hierarquia depende do tema, mas o manual recomenda:

1. **fontes primárias:** documentos, obras, dados ou especificações originais;
2. **fontes institucionais ou oficiais:** documentação técnica, leis, órgãos, universidades, organizações responsáveis;
3. **pesquisa acadêmica revisada ou bibliografia especializada;**
4. **fontes secundárias de alta qualidade;**
5. **fontes pedagógicas;**
6. **comunidades e relatos**, utilizados como indício, experiência ou FAQ, não como prova central.

## 5.8. Registro de evidência

Cada afirmação importante deve permitir responder:

- qual fonte sustenta a afirmação?
- a fonte prova o fato ou apenas interpreta?
- qual data, edição, página, seção ou trecho é relevante?
- existe posição divergente?
- o dado pode ter mudado?

## 5.9. Camadas de verdade adaptáveis

O modelo filosófico do estudo de caso pode ser generalizado:

| Camada | Definição universal | Exigência |
|---|---|---|
| fato documentado | ocorrência ou dado verificável | fonte primária/oficial |
| relação demonstrada | ligação sustentada por evidência específica | explicação da ligação |
| interpretação especializada | leitura defendida por especialistas | autores e divergências nomeadas |
| hipótese de trabalho | proposição plausível ainda não confirmada | rótulo explícito e teste futuro |
| aproximação pedagógica | comparação útil para ensinar | não apresentar como fato |
| especulação visual | associação sugerida pelo mapa | nunca usar como prova |

---

# FASE 4 — Projetar a ontologia

## 5.10. Separar entidades, relações e documentos

Uma ontologia mínima universal pode conter:

- `entidade` — pessoa, organização, lugar, tecnologia, organismo etc.;
- `conceito` — ideia, categoria, princípio, método;
- `obra` ou `artefato` — livro, artigo, produto, lei, software, documento;
- `evento` — acontecimento localizado no tempo;
- `corrente` ou `categoria` — agrupamento interpretativo;
- `relacao` — conexão tipada entre duas ou mais entidades;
- `controversia` — disputa entre posições;
- `fonte` — registro bibliográfico ou documental;
- `moc` — mapa curado;
- `trilha` — sequência de estudo ou execução;
- `auditoria` — verificação;
- `pendencia` — lacuna qualificada;
- `infraestrutura` — schema, README, template, configuração.

Nem todo cofre precisa de todos os tipos.

## 5.11. Tabela ontológica

Antes de criar arquivos, produzir:

| Tipo | Pergunta respondida | Propriedades próprias | Relações permitidas | Profundidade |
|---|---|---|---|---|
| pessoa | quem é e por que importa? | período, função | criou, influenciou, participou | padrão/profunda |
| conceito | o que significa e como varia? | origem, definição | pertence, contrasta, é aplicado | padrão |
| obra | o que contém e qual impacto? | autoria, data | desenvolve, cita, critica | padrão |
| relação | como A se conecta a B? | origem, destino, tipo | evidencia | profunda se forte |

## 5.12. Vocabulário de relações

Evitar a propriedade genérica `relacionado_a` como padrão único. Definir um vocabulário por domínio.

Vocabulário universal inicial:

- `cria`
- `desenvolve`
- `aplica`
- `influencia`
- `recebe_influencia_de`
- `critica`
- `contrasta_com`
- `revisa`
- `expande`
- `substitui`
- `depende_de`
- `ocorre_em`
- `participa_de`
- `exemplifica`
- `contextualiza`
- `e_parte_de`
- `tem_como_parte`
- `evidencia`
- `contesta`
- `sintetiza`
- `traduz`
- `adapta`
- `precede`
- `sucede`
- `paralelo_pedagogico`

Cada termo precisa de definição e condições de uso.

## 5.13. Regra de direção

Relações direcionais devem deixar claro o sentido. Exemplo:

- origem: `[[Autor A]]`
- destino: `[[Autor B]]`
- tipo_relacao: `critica`

Não usar setas em títulos sem declarar o significado da seta.

---

# FASE 5 — Projetar a arquitetura de pastas

## 5.14. Arquitetura universal recomendada

```text
Nome-do-Vault/
├── 00 - Inicio/
├── 01 - MOCs/
├── 02 - Entidades/
├── 03 - Conceitos/
├── 04 - Obras-e-Artefatos/
├── 05 - Eventos-e-Contextos/
├── 06 - Relacoes/
├── 07 - Controversias/
├── 08 - Fontes/
├── 09 - Trilhas/
├── 10 - Bases-e-Consultas/
├── 11 - Canvas/
├── 90 - Templates/
├── 95 - Sistema-e-Auditorias/
├── 99 - Pendencias/
└── _Anexos/
```

## 5.15. Regras de arquitetura

- pastas representam tipos estáveis ou funções de manutenção;
- não criar uma pasta para cada pequeno tópico;
- não misturar templates com conteúdo;
- não misturar arquivos de processo com o vault final;
- limitar a profundidade a dois ou três níveis, salvo necessidade real;
- usar numeração somente para ordem, não como identidade semântica;
- caminhos não devem ser codificados manualmente em dezenas de consultas sem uma estratégia de migração.

## 5.16. Quando usar pastas temáticas

Pastas temáticas são adequadas quando uma nota pertence naturalmente a um único domínio operacional. Se uma nota participa de múltiplos temas, usar links, MOCs, propriedades e tags.

## 5.17. Pastas que devem ser excluídas do grafo

Em geral:

- templates;
- sistema;
- auditorias;
- anexos brutos;
- arquivos importados;
- pendências administrativas;
- consultas e dashboards, quando poluem a leitura temática.

---

# FASE 6 — Definir nomenclatura

## 5.18. Regras para nomes de arquivo

- usar nomes humanos e estáveis;
- evitar caracteres problemáticos `# | ^ : %% [[ ]]`;
- evitar dois arquivos com o mesmo basename;
- evitar inserir versão em cada nota temática;
- não incluir tipo no nome quando o contexto já é claro, salvo para desambiguação;
- preferir `Desconstrucao (corrente)` e `Desconstrucao (conceito)` quando houver homônimos;
- testar nomes com acentos em ZIPs reais; se a cadeia de empacotamento não preservar Unicode, usar ASCII consistente e título legível no YAML;
- não renomear em massa sem atualização automática de links e validação posterior.

## 5.19. Títulos e aliases

O título de exibição pode preservar acentos e forma editorial:

```yaml
titulo: "Jürgen Habermas"
aliases:
  - "Jurgen Habermas"
  - "Habermas"
```

Aliases são apropriados para siglas, nomes alternativos, traduções, abreviações e variantes ortográficas reais. Não adicionar aliases artificiais apenas para aumentar descoberta.

## 5.20. Identificador estável

Em cofres que serão integrados ou migrados, usar um campo `id` independente do nome do arquivo:

```yaml
id: autor-jurgen-habermas
```

O `id` não substitui links internos, mas ajuda scripts e integração externa.

---

# FASE 7 — Congelar o schema YAML

## 5.21. Contrato universal

Toda nota temática deve possuir, no mínimo:

```yaml
---
titulo: ""
aliases: []
tipo: ""
status: "rascunho"
versao_schema: "1.0"
tags: []
criado_em: 2026-06-17
atualizado_em: 2026-06-17
---
```

## 5.22. Propriedades controladas

Campos usados em filtros devem ter vocabulário fechado:

```yaml
status: "rascunho | em_revisao | revisado | auditado | arquivado"
prioridade: "nucleo_a | nucleo_b | contexto_c | adjacente_d"
grau_confianca: "alto | medio_alto | medio | medio_baixo | baixo | nao_avaliado"
risco_interpretativo: "alto | medio | baixo | nao_aplicavel"
```

Justificativas longas devem ficar em campos separados ou no corpo:

```yaml
grau_confianca: medio
justificativa_confianca: "A relação é conceitualmente plausível, mas falta documentação histórica direta."
```

## 5.23. Tipos consistentes

A mesma propriedade deve manter o mesmo tipo em todo o vault. Exemplos:

- `aliases`: sempre lista;
- `tags`: sempre lista;
- `autores`: sempre lista de links;
- `ano`: sempre número ou sempre texto definido pelo schema;
- `data`: formato ISO;
- `revisado`: sempre checkbox/booleano;
- `grau_confianca`: sempre texto controlado.

## 5.24. Evitar nested properties como requisito central

Embora YAML aceite objetos aninhados e Dataview possa consultá-los, a interface nativa de propriedades do Obsidian não oferece suporte completo a propriedades aninhadas. Para máxima compatibilidade, preferir chaves planas.

## 5.25. Links no frontmatter

Quando usar wikilinks como valores YAML, colocá-los entre aspas:

```yaml
autores:
  - "[[Michel Foucault]]"
conceitos:
  - "[[Genealogia]]"
```

## 5.26. Dicionário de propriedades

Criar `95 - Sistema-e-Auditorias/Dicionario-de-Propriedades.md` com:

| Propriedade | Tipo | Permitido em | Valores | Obrigatória | Descrição |
|---|---|---|---|---|---|

Nenhuma produção em massa começa antes do dicionário ser aprovado.

---

# FASE 8 — Criar o inventário mestre

## 5.27. Inventário antes das notas

Criar uma tabela com todas as notas planejadas:

| arquivo | tipo | prioridade | MOC principal | fontes mínimas | relações previstas | status |
|---|---|---|---|---|---|---|

O inventário previne:

- duplicatas;
- grafias concorrentes;
- notas sem função;
- links para entidades não planejadas;
- expansão descontrolada;
- produção desigual.

## 5.28. Registro de entidades

Manter um arquivo de máquina, como `inventario.json` ou `inventario.csv`, fora do conteúdo de leitura, com caminhos e IDs previstos. A IA deve gerar links apenas contra esse registro ou contra stubs autorizados.

## 5.29. Política de stubs

Um stub só é permitido quando:

- a entidade é necessária para resolver links;
- sua ausência é declarada;
- contém propósito, fontes mínimas e próximo passo;
- está marcado como `status: rascunho` ou `tipo: pendencia`;
- não finge profundidade.

---

# FASE 9 — Criar templates

## 5.30. Função correta do template

O template deve padronizar:

- propriedades;
- perguntas obrigatórias;
- seções;
- critérios de evidência;
- checklist;
- saídas esperadas.

Não deve impor o mesmo argumento a todas as notas.

## 5.31. Template mínimo de entidade

```markdown
---
titulo: ""
aliases: []
tipo: entidade
status: rascunho
versao_schema: "1.0"
prioridade: contexto_c
tags: []
relacoes_chave: []
fontes_primarias: []
fontes_secundarias: []
grau_confianca: nao_avaliado
criado_em: {{date:YYYY-MM-DD}}
atualizado_em: {{date:YYYY-MM-DD}}
---

# {{title}}

## Síntese

## Relevância para o cofre

## Contexto

## Elementos centrais

## Relações justificadas

## Controvérsias e limites

## Fontes

## Próximos passos

- [ ] A nota responde por que existe?
- [ ] Todos os links são semanticamente justificáveis?
- [ ] As fontes sustentam as afirmações fortes?
- [ ] Há conteúdo específico, não apenas boilerplate?
```

## 5.32. Core Templates versus Templater

Use Templates nativo para:

- inserir estrutura estática;
- título, data e hora;
- máxima portabilidade.

Use Templater para:

- escolher tipo de nota por prompt;
- gerar ID e nome dinamicamente;
- mover arquivo para pasta correta;
- criar seções condicionais;
- executar scripts documentados.

Nunca tornar Templater obrigatório para abrir ou ler o cofre.

---

# FASE 10 — Produzir o conteúdo

## 5.33. Ordem de produção

1. notas de sistema e metodologia;
2. MOC inicial;
3. entidades núcleo A;
4. fontes e obras essenciais;
5. conceitos núcleo;
6. relações fortes;
7. controvérsias;
8. contexto B/C;
9. trilhas e dashboards;
10. pendências.

Essa ordem permite que notas posteriores apontem para alvos existentes.

## 5.34. Densidade por função

Faixas são indicadores, não substitutos de qualidade:

| Tipo | Faixa inicial sugerida | Exigência principal |
|---|---:|---|
| stub qualificado | 100–250 palavras | propósito e próximo passo |
| conceito padrão | 350–800 | definição, variações, exemplos, limites |
| entidade padrão | 500–1.000 | contexto, relevância, relações, fontes |
| núcleo profundo | 1.000–2.500 | argumento, controvérsias, evidências |
| relação forte | 500–1.200 | tese, evidência, objeções, veredito |
| MOC | 250–1.000 | curadoria e caminhos, não verbete |
| auditoria | conforme achados | método, métricas, falhas e veredito |

## 5.35. Critérios de conteúdo específico

Cada nota deve conter elementos que não poderiam ser copiados para outra entidade sem alteração substancial.

Teste:

> Se nomes próprios e links forem removidos, a nota ainda é reconhecível como pertencente a esse assunto?

Se a resposta for não, revisar.

## 5.36. Separar fato, interpretação e hipótese

Usar seções ou callouts:

```markdown
> [!info] Fato documentado
> ...

> [!note] Interpretação
> ...

> [!question] Hipótese a verificar
> ...
```

## 5.37. Citações e referências

Em projetos rigorosos, registrar edição, página, seção, data de acesso e tipo de fonte. Evitar bibliografia genérica no final de uma nota que faz afirmações específicas sem indicar qual fonte sustenta cada ponto.

## 5.38. Controle de repetição

A auditoria deve comparar:

- frases iniciais repetidas;
- parágrafos com estrutura idêntica;
- distribuição de palavras por tipo;
- notas cuja diferença é apenas nomes e links;
- conclusões genéricas reutilizadas.

---

# FASE 11 — Construir links semanticamente relevantes

## 5.39. Regra principal

Um link só deve ser criado quando o autor da nota consegue completar a frase:

> “Este link existe porque...”

## 5.40. Algoritmo de linkagem da IA

### Passo A — Consultar o inventário

Verificar se o destino existe, está planejado ou é stub autorizado.

### Passo B — Classificar a relação

Escolher um tipo do vocabulário controlado.

### Passo C — Avaliar o link

Pontuar:

| Critério | Pontos |
|---|---:|
| relevância direta para a tese da nota | 0–3 |
| evidência ou explicação disponível | 0–3 |
| utilidade de navegação | 0–2 |
| especificidade do destino | 0–2 |

Criar link contextual se total ≥ 6. Entre 4 e 5, mover para “Veja também” ou pendência. Abaixo de 4, não criar.

### Passo D — Inserir no ponto de significado

O link deve aparecer quando a relação é explicada, não em toda repetição da palavra.

### Passo E — Registrar relações fortes

Se a relação for central, controversa ou exigir prova, criar nota de relação própria.

### Passo F — Validar o destino

Checar basename, caminho, cabeçalho ou bloco.

## 5.41. Tipos de link

### Link de entidade

```markdown
[[Michel Foucault]] desenvolve uma genealogia...
```

### Link com texto de exibição

```markdown
[[Michel Foucault|Foucault]]
```

### Link para cabeçalho

```markdown
[[Michel Foucault#Genealogia]]
```

### Link para bloco

```markdown
[[Michel Foucault#^definicao-genealogia]]
```

Links para blocos são específicos do Obsidian e menos portáveis. Usar apenas quando a granularidade compensa a dependência.

### Embed/transclusão

```markdown
![[Politica-de-Evidencias#Escala de confiança]]
```

Transcluir quando o trecho deve permanecer sincronizado. Não usar transclusão para esconder fragmentação excessiva ou criar páginas que só montam pedaços sem contexto.

## 5.42. Backlinks não exigem reciprocidade artificial

Se A aponta para B, B já recebe backlink. Adicionar B→A somente quando a leitura de B também se beneficia explicitamente da conexão.

## 5.43. Política de links não resolvidos

Escolher uma das políticas:

- **estrita:** nenhum link não resolvido na entrega;
- **controlada:** links não resolvidos apenas com tag/propriedade de stub planejado;
- **exploratória:** permitidos, mas excluídos do critério de pronto.

Para cofres entregues como prontos, usar política estrita.

## 5.44. Orçamento de links

Não impor números rígidos universais. Usar mínimos funcionais por tipo:

- entidade núcleo: MOC, 2–5 conceitos, 1–3 obras/fontes e relações principais;
- conceito: origem, entidades usuárias, conceitos vizinhos e contraste;
- obra: autoria, conceitos desenvolvidos, contexto e recepção;
- controvérsia: posições, participantes, fontes e conceitos;
- relação: origem, destino, evidências e MOC temático.

## 5.45. Auditoria de isolamento

Medir separadamente:

- sem links de entrada;
- sem links de saída;
- completamente isoladas;
- isoladas por tipo;
- isoladas no núcleo A/B.

Uma nota administrativa isolada pode ser aceitável. Uma nota núcleo isolada é falha.

---

# FASE 12 — Produzir MOCs

## 5.46. MOC manual versus lista automática

Um MOC manual responde:

- por onde começar;
- quais caminhos são alternativos;
- quais notas são centrais;
- quais tensões organizam o tema;
- como as partes se relacionam.

Uma consulta automática responde:

- quais arquivos satisfazem um filtro.

O melhor sistema combina os dois.

## 5.47. Tipos de MOC

- **MOC inicial:** porta de entrada geral;
- **MOC ontológico:** autores, obras, conceitos, eventos etc.;
- **MOC temático:** problema ou área;
- **MOC argumentativo:** posições e controvérsias;
- **MOC cronológico:** períodos e eventos;
- **MOC operacional:** fluxo de trabalho;
- **MOC de aprendizado:** trilha por nível.

## 5.48. Estrutura de MOC

```markdown
# MOC — Tema

## Como usar este mapa

## Entrada rápida
- [[Nota introdutória]] — função do link.

## Núcleo
### Eixo A
- [[Nota]] — por que está aqui.

### Eixo B
- [[Nota]] — por que está aqui.

## Controvérsias

## Trilhas sugeridas

## Lacunas e expansão
```

## 5.49. Critério de criação

Criar MOC quando o conjunto exige uma decisão de percurso. Não criar um MOC vazio apenas para espelhar cada pasta.

## 5.50. Auditoria de MOCs

- links explicados, não apenas listados;
- nenhum destino inexistente;
- cobertura dos núcleos;
- ausência de redundância com outro MOC;
- atualização após inclusão de notas importantes;
- conteúdo manual preservado mesmo quando há consulta dinâmica.

---

# FASE 13 — Tags e propriedades temáticas

## 5.51. Função das tags

Tags devem representar estado, fluxo ou agrupamento transversal de baixa granularidade. Não duplicar toda a ontologia em tags.

Exemplos adequados:

```yaml
tags:
  - status/revisao
  - escopo/nucleo
  - uso/trilha-inicial
```

Exemplos problemáticos:

- uma tag para cada pessoa;
- uma tag para cada conceito já representado por nota;
- tags e propriedades concorrentes para a mesma função;
- dezenas de tags sem dicionário.

## 5.52. Tags aninhadas

Usar `/` quando a hierarquia é estável e útil para busca. Evitar profundidade excessiva.

## 5.53. Propriedade ou tag?

Use propriedade quando:

- o valor possui tipo;
- será exibido em coluna;
- precisa de comparação, ordenação ou validação;
- existe um único valor ou lista controlada.

Use tag quando:

- é um marcador rápido e transversal;
- busca hierárquica simples é suficiente;
- não precisa de valor associado.

---

# FASE 14 — Bases, Dataview e DataviewJS

## 5.54. Estratégia de camadas

1. **Markdown manual** contém conhecimento indispensável.
2. **MOCs manuais** oferecem curadoria.
3. **Bases** oferece vistas nativas editáveis.
4. **Dataview DQL** oferece vistas derivadas e auditorias.
5. **DataviewJS** resolve exceções complexas.

## 5.55. Regras para consultas

Toda consulta deve declarar:

- pergunta respondida;
- fonte ou pasta;
- filtros e exclusões;
- propriedades exigidas;
- resultado esperado;
- comportamento quando não há resultados;
- dependência técnica.

## 5.56. Exemplo Dataview seguro

```dataview
TABLE status AS "Status", grau_confianca AS "Confiança", file.mtime AS "Atualizada"
FROM "02 - Entidades"
WHERE tipo = "entidade"
  AND !contains(file.path, "90 - Templates")
SORT choice(
  grau_confianca = "alto", 5,
  grau_confianca = "medio_alto", 4,
  grau_confianca = "medio", 3,
  grau_confianca = "medio_baixo", 2,
  grau_confianca = "baixo", 1,
  0
) DESC
```

## 5.57. Excluir infraestrutura

Não usar consultas globais sem filtrar tipos administrativos. Exemplo:

```dataview
TABLE tipo, status
FROM ""
WHERE !contains(list("infraestrutura", "template", "auditoria", "consulta"), tipo)
  AND (length(fontes_primarias) = 0 OR length(fontes_secundarias) = 0)
SORT file.path ASC
```

## 5.58. Evitar ordenação semântica alfabética

Categorias como alto, médio e baixo precisam de conversão para números ou propriedade adicional `grau_confianca_ordem`.

## 5.59. Dataview não corrige schema ruim

Se uma consulta exige dezenas de exceções textuais, corrigir propriedades na origem.

## 5.60. Bases como alternativa nativa

Criar arquivos `.base` para vistas que o usuário precisa editar frequentemente, como:

- inventário editorial;
- biblioteca de fontes;
- notas por status;
- pendências;
- entidades por prioridade;
- galeria de obras ou produtos.

## 5.61. DataviewJS

Exigências mínimas:

- comentário inicial com finalidade;
- nenhuma dependência oculta;
- tratamento de campo ausente;
- limite de escopo;
- sem alteração destrutiva de arquivos;
- fallback em texto ou DQL;
- teste após atualização do plugin.

---

# FASE 15 — Planejar Graph View e Canvas

## 5.62. Graph View

O Graph View nativo mostra links, tamanho relativo dos nós e grupos por busca. Ele não possui semântica de aresta por padrão. Logo:

- tipo de relação deve estar na nota ou em nota de relação;
- grupos devem usar propriedades, tags ou caminhos estáveis;
- infraestrutura deve ser excluída;
- setas indicam direção do link, não causalidade;
- tamanho do nó indica referências, não importância objetiva.

## 5.63. Configuração recomendada

- ocultar anexos quando não forem objeto de estudo;
- mostrar apenas arquivos existentes em vistas de auditoria;
- alternar órfãos conforme objetivo;
- criar grupos por `tipo` ou pasta;
- manter filtros documentados em nota de sistema;
- oferecer vistas locais para navegação cotidiana;
- não depender de uma única configuração global.

## 5.64. Camadas de grafo

Criar filtros prontos para:

- conteúdo temático;
- relações fortes;
- bibliografia;
- controvérsias;
- trilhas pedagógicas;
- pendências;
- auditoria de órfãos.

## 5.65. Canvas

Canvas é adequado para narrativas visuais curadas, comparação, planejamento e mapa de controvérsia. O formato JSON Canvas permite nós de texto, arquivo, link e grupo, além de arestas com direção, cor e rótulo.

Usos recomendados:

- explicar um recorte específico;
- representar uma controvérsia;
- montar trilha de leitura;
- comparar modelos;
- mostrar processo;
- servir como painel de entrada.

Não usar Canvas como substituto de notas de relação ou fonte de verdade.

## 5.66. Regras técnicas de Canvas

- IDs únicos;
- caminhos reais;
- nós sem duplicação desnecessária;
- arestas com rótulos quando o significado não é óbvio;
- legenda visual;
- grupos nomeados;
- verificação de todos os campos `file` após renomeações;
- JSON válido;
- abertura manual no Obsidian.

## 5.67. Legenda epistemológica

Todo Canvas analítico deve declarar:

- o que as cores representam;
- o que as setas representam;
- quais conexões são documentadas;
- quais são hipóteses;
- onde a evidência textual está registrada.

---

# FASE 16 — Auditorias

## 5.68. Auditoria técnica

Verificar:

- arquivos esperados e extensões;
- UTF-8;
- nomes seguros;
- YAML parseável;
- propriedades com tipos consistentes;
- basenames duplicados;
- links resolvidos;
- links para cabeçalhos e blocos;
- embeds;
- Canvas JSON e referências;
- Bases sintaticamente válidas;
- configurações `.obsidian` legíveis;
- dependências declaradas.

## 5.69. Auditoria semântica

- cada link possui função identificável;
- relações usam vocabulário correto;
- nenhuma similaridade é apresentada automaticamente como influência;
- notas núcleo não estão isoladas;
- relações fortes têm evidência;
- direção de relações está correta;
- aliases não criam ambiguidade.

## 5.70. Auditoria de conteúdo

- cobertura do escopo;
- profundidade por prioridade;
- ausência de boilerplate;
- definições consistentes;
- fatos e interpretações separados;
- exemplos específicos;
- controvérsias representadas;
- lacunas declaradas;
- sem invenções para preencher campo.

## 5.71. Auditoria bibliográfica

- fonte primária quando necessária;
- fontes secundárias especializadas;
- dados bibliográficos suficientes;
- páginas/seções para afirmações fortes;
- links externos válidos, quando usados;
- distinção entre autoridade e experiência;
- atualização de fatos temporais;
- nenhuma referência decorativa.

## 5.72. Auditoria de MOCs

- cobertura do núcleo;
- links resolvidos;
- caminhos explicados;
- nenhum MOC vazio;
- coerência entre MOCs;
- atualização após mudanças.

## 5.73. Auditoria Dataview/Bases

- plugin instalado quando necessário;
- consultas renderizam;
- campos existem;
- tipos compatíveis;
- filtros não capturam infraestrutura;
- ordenações semânticas corretas;
- resultado vazio tratado;
- alternativa nativa ou manual documentada.

## 5.74. Auditoria de grafo

- distribuição por tipo;
- órfãos por prioridade;
- hubs artificiais;
- links administrativos poluindo a rede;
- MOCs excessivamente dominantes;
- clusters que refletem conteúdo, não apenas pastas;
- centralidade não apresentada como verdade.

## 5.75. Auditoria de repetição

- hashes de parágrafos;
- similaridade entre notas do mesmo tipo;
- frases padrão repetidas;
- variação anormalmente baixa de tamanho;
- notas que poderiam trocar de título sem perder sentido;
- conclusões genéricas.

## 5.76. Auditoria editorial

- versão consistente;
- changelog completo;
- status real;
- pendências assumidas;
- arquivos de processo removidos;
- README e guia de uso atualizados;
- nenhum placeholder involuntário.

## 5.77. Auditoria manual por amostragem

Selecionar ao menos:

- 10% das notas ou mínimo de 10;
- notas de todos os tipos;
- as cinco mais longas e cinco mais curtas;
- hubs com mais links;
- notas isoladas;
- relações de maior confiança;
- páginas com mais fontes;
- arquivos Canvas e consultas principais.

A auditoria automatizada não substitui leitura.

---

# FASE 17 — Empacotar e entregar

## 5.78. Conteúdo mínimo da entrega

- pasta raiz com nome final;
- notas e anexos;
- `.obsidian` somente com configurações justificadas;
- README;
- guia de uso;
- arquitetura e ontologia;
- dicionário de propriedades;
- dependências;
- changelog;
- relatório de auditoria;
- lista de pendências;
- instruções de expansão.

## 5.79. Protocolo de ZIP

1. congelar a versão;
2. remover caches, temporários e contexto de produção;
3. verificar nomes Unicode;
4. compactar a pasta raiz, não apenas seus conteúdos;
5. extrair o ZIP em diretório temporário;
6. comparar inventário antes/depois;
7. executar auditoria sobre a cópia extraída;
8. abrir a cópia no Obsidian;
9. testar MOCs, consultas, Bases, Graph e Canvas;
10. gerar checksum opcional;
11. entregar somente após aprovação.

## 5.80. Teste de fidelidade pós-ZIP

Comparar:

- quantidade de arquivos por extensão;
- caminhos;
- hashes de conteúdo;
- caracteres Unicode;
- links resolvidos;
- referências Canvas;
- configurações;
- tamanho do pacote.

## 5.81. README obrigatório

O README deve informar:

- objetivo;
- versão;
- como abrir;
- ponto de entrada;
- plugins nativos e comunitários;
- modo sem plugins;
- estrutura;
- convenções;
- limitações;
- última auditoria;
- como contribuir ou expandir.

## 5.82. Critérios de bloqueio

Não entregar como “pronto” se houver:

- arquivo faltante;
- links núcleo quebrados;
- YAML inválido;
- ZIP que altera nomes;
- Canvas essencial quebrado;
- placeholders não declarados;
- fonte inventada;
- dependência não informada;
- discrepância de versão;
- relatório que contradiz o estado real.

---

# FASE 18 — Atualizar e expandir

## 5.83. Fluxo de manutenção

```text
capturar → classificar → pesquisar → criar/editar → conectar → revisar → auditar → publicar
```

## 5.84. Entrada de nova nota

Antes de criar:

- buscar duplicata e aliases;
- identificar tipo;
- escolher MOC;
- definir fontes;
- registrar relações previstas;
- aplicar template;
- atualizar inventário.

## 5.85. Mudança de schema

Quando alterar propriedade:

1. incrementar `versao_schema`;
2. documentar migração;
3. atualizar templates;
4. migrar notas existentes;
5. atualizar consultas/Bases;
6. auditar tipos;
7. registrar no changelog.

## 5.86. Mudança de pastas

Tratar como migração:

- mapa antigo→novo;
- atualização automática de links;
- atualização de consultas por caminho;
- atualização de Canvas;
- atualização de filtros Graph;
- atualização de README;
- auditoria pós-migração.

## 5.87. Política de arquivamento

Não apagar silenciosamente notas que foram substituídas. Marcar:

```yaml
status: arquivado
substituido_por:
  - "[[Nova nota]]"
```

Mover para arquivo somente quando isso não quebrar o modelo de navegação.

## 5.88. Indicadores de saúde

Acompanhar:

- notas por status e prioridade;
- links quebrados;
- núcleo sem fontes;
- notas isoladas;
- relações sem evidência;
- MOCs desatualizados;
- pendências antigas;
- propriedades inválidas;
- consultas com erro;
- repetição estrutural;
- versão do schema.

## 6. Práticas universais versus dependentes do tema

### 6.1. Universais

- inventário;
- ontologia explícita;
- YAML controlado;
- links válidos;
- política de fontes;
- README;
- MOC inicial;
- auditoria;
- teste pós-ZIP;
- dependências declaradas;
- versionamento.

### 6.2. Dependentes do tema

- tipos específicos de entidade;
- vocabulário de relações;
- hierarquia de fontes;
- critérios de verdade;
- densidade;
- períodos e categorias;
- tipos de controvérsia;
- unidades de análise;
- forma de citação;
- necessidade de dados tabulares, mapas ou cronologias.

## 7. Matriz de obrigatoriedade

| Elemento | Pequeno | Médio | Grande/rigoroso |
|---|---:|---:|---:|
| README | obrigatório | obrigatório | obrigatório |
| MOC inicial | recomendado | obrigatório | obrigatório |
| Ontologia escrita | simples | obrigatória | obrigatória e versionada |
| YAML | mínimo | obrigatório | obrigatório e auditado |
| Dataview | opcional | opcional | conforme necessidade |
| Bases | opcional | recomendado para gestão | recomendado quando editável |
| Canvas | opcional | conforme tema | curado, não automático |
| Auditoria automatizada | recomendada | obrigatória | obrigatória |
| Auditoria manual | recomendada | obrigatória | obrigatória por amostra |
| Changelog | recomendado | obrigatório | obrigatório |
| Teste pós-ZIP | obrigatório | obrigatório | obrigatório |

## 8. Anti-padrões

### 8.1. Linkagem por coincidência lexical

Criar links em toda ocorrência de uma palavra gera um grafo denso e pouco informativo.

### 8.2. Uma nota para tudo

Notas muito longas tornam conceitos difíceis de reutilizar e auditar.

### 8.3. Atomização compulsiva

Quebrar cada parágrafo em nota gera fragmentação e dependência de transclusões.

### 8.4. YAML enciclopédico

Mover toda a análise para propriedades torna a nota ilegível e esbarra nas limitações de propriedades.

### 8.5. Tags como ontologia completa

Tags não carregam direção, evidência ou contexto de relação.

### 8.6. MOC como lista automática sem curadoria

Uma tabela Dataview não explica percurso ou importância.

### 8.7. Canvas como prova

Setas coloridas podem mascarar ausência de evidência.

### 8.8. Relatório autoelogioso

Auditorias devem registrar falhas reais, não repetir requisitos do prompt como se tivessem sido verificados.

### 8.9. Word count como profundidade

Aumentar palavras com parágrafos genéricos não melhora a nota.

### 8.10. Versão apenas no nome do ZIP

Versão precisa ser consistente em changelog, schema e documentação, sem contaminar cada nota com tags históricas desnecessárias.

### 8.11. Entregar plugin sem declarar dependência

Configuração habilitada não garante que o plugin esteja instalado.

### 8.12. Validar antes de compactar

A compactação pode alterar nomes, permissões ou estrutura.

## 9. Critérios de qualidade final

### 9.1. Técnico

- 100% dos arquivos obrigatórios presentes;
- 100% do YAML parseável;
- nenhuma duplicata de basename não intencional;
- nenhum link quebrado no núcleo;
- nenhum caminho Canvas inválido;
- ZIP extraído com nomes idênticos;
- consultas principais testadas;
- dependências documentadas.

### 9.2. Semântico

- relações tipadas;
- links justificáveis;
- notas núcleo integradas;
- nenhuma influência inferida só por similaridade;
- controvérsias visíveis;
- hipóteses marcadas.

### 9.3. Editorial

- conteúdo específico;
- densidade proporcional;
- baixa repetição mecânica;
- linguagem coerente;
- exemplos e fontes;
- nenhum placeholder escondido;
- escopo respeitado.

### 9.4. Navegação

- ponto de entrada claro;
- MOCs úteis;
- trilhas para públicos distintos;
- busca por propriedades/tags;
- Graph View não poluído;
- Canvas explicados.

### 9.5. Manutenção

- schema documentado;
- templates completos;
- changelog;
- inventário;
- pendências qualificadas;
- fluxo de atualização.

## 10. Definition of Done

Um cofre é considerado pronto quando:

1. abre no Obsidian sem correções manuais obrigatórias;
2. o usuário encontra o ponto de entrada em menos de um minuto;
3. cada tipo de nota possui schema e template;
4. as notas núcleo respondem à pergunta central;
5. links importantes têm significado explicável;
6. relações fortes têm evidência e limites;
7. não há falhas técnicas bloqueantes;
8. consultas e Canvas principais funcionam;
9. o ZIP extraído foi auditado;
10. README, changelog e pendências correspondem ao estado real.

## 11. Resumo operacional para uma IA

```text
1. Leia todos os materiais.
2. Escreva ficha de escopo.
3. Defina autoridade e camadas de evidência.
4. Modele tipos e relações.
5. Congele nomes, schema e vocabulários.
6. Crie inventário completo.
7. Crie arquitetura, templates e MOCs iniciais.
8. Produza núcleo e fontes antes da periferia.
9. Gere links contra o inventário e classifique relações.
10. Crie consultas e vistas somente após os dados existirem.
11. Audite técnica, semântica e editorialmente.
12. Corrija o conteúdo real.
13. Compacte.
14. Extraia em ambiente limpo.
15. Audite novamente.
16. Entregue ZIP, README, changelog, relatório e pendências.
```

## 12. Arquivos complementares

- [[Anexos/Estudo-de-Caso-Vault-Pos-Nietzsche]]
- [[Anexos/Modelos-YAML-e-Notas]]
- [[Anexos/Biblioteca-Dataview-Bases-e-Consultas]]
- [[Anexos/Checklists-de-Producao-Auditoria-e-Entrega]]
- [[Prompt-Mestre-IA-para-Criar-Cofres]]
- [[Referencias-e-Fontes]]
