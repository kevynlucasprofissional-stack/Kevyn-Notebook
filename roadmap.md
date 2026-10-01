---
id: roadmap-kevyn-notebook
titulo: Roadmap do Kevyn Notebook
tipo: roadmap
status: ativo
profundidade: avancada
versao_schema: "1.0"
versao_conteudo: "1.2"
idioma: pt-BR
data_criacao: 2026-09-28
ultima_revisao: 2026-09-29
tags:
  - planejamento/roadmap
  - sistema/curadoria
  - memoria/longitudinal
---

# Roadmap do Kevyn Notebook

## Visão

O Kevyn Notebook deve evoluir de um repositório que **preserva dados sobre Kevyn** para um sistema que **constrói compreensão rastreável sobre sua trajetória ao longo do tempo**.

A meta não é produzir uma descrição definitiva de Kevyn.

A meta é construir um **modelo versionado da trajetória de Kevyn**, capaz de registrar:

- o que aconteceu;
- como foi registrado na época;
- como foi reinterpretado depois;
- quais padrões aparecem ou desaparecem;
- quais narrativas mudam;
- quais decisões, projetos, ideias e relações se transformam;
- quais afirmações são sustentadas pelas fontes;
- quais continuam sendo interpretações ou hipóteses.

O princípio central é:

> **Os arquivos originais preservam os registros. A camada canônica preserva a compreensão acumulada desses registros.**

---

## Arquitetura epistemológica

O fluxo estrutural do Vault é:

```text
FONTES ORIGINAIS
      ↓
CLASSIFICAÇÃO E CURADORIA
      ↓
EVIDÊNCIAS / CLAIMS
      ↓
CONHECIMENTO CANÔNICO
      ↓
PERGUNTAS
      ↓
NOVAS SÍNTESES / HIPÓTESES / DECISÕES
      ↓
NOVOS REGISTROS E NOVA CURADORIA
```

Este processo é cumulativo e iterativo.

A camada canônica não deve se tornar um depósito de resumos. Ela deve representar **o que a leitura conjunta das fontes permite compreender**.

---

# Estado atual

## Infraestrutura já estabelecida

- [x] camada de originais consolidada em `000-Originais/`;
- [x] camada canônica separada da camada original;
- [x] documentação central em `README.md`;
- [x] manual operacional para agentes em `AGENTS.md`;
- [x] ontologia, schema YAML e convenções em `97-Infraestrutura/`;
- [x] sistema de evidências e claims;
- [x] controle de integração legado preservado;
- [x] controle progressivo de curadoria criado;
- [x] painel de curadoria criado;
- [x] política explícita de imutabilidade dos originais;
- [x] política explícita de que relevância 0 não implica exclusão;
- [x] política de memória cumulativa formalizada.

## Baseline atual da camada original

Na criação deste roadmap, `000-Originais/` continha **12.475 arquivos**. Em 29/09/2026 a contagem real é de **12.433 arquivos** (o CSV de controle preserva a fotografia inicial de 12.475 linhas).

O registro central é:

`98-Pendencias-e-controles/Controle-Curadoria-Originais/Controle-Curadoria-Originais.csv`

O painel é:

[[98-Pendencias-e-controles/Controle-Curadoria-Originais/Painel de curadoria dos originais]]

A quantidade de arquivos pode mudar. O controle deve acompanhar o estado real do repositório.

---

# FASE 1 — Classificar e curar toda a camada original

**Objetivo:** nenhuma fonte original deve permanecer indefinidamente como um arquivo sem estado conhecido.

## 1.1. Classificação de todos os arquivos

Para cada arquivo de `000-Originais/`:

- [ ] confirmar caminho e identidade;
- [ ] ler conteúdo suficiente para compreender sua natureza;
- [ ] marcar `analisado`;
- [ ] atribuir `relevancia` de 0 a 10;
- [ ] registrar observações de curadoria;
- [ ] marcar necessidade de revisita;
- [ ] registrar SHA-256 quando disponível;
- [ ] separar material sobre Kevyn de material apenas consumido por Kevyn.

### Escala

- **0** — irrelevante para o propósito do Kevyn Notebook;
- **1–3** — baixa relevância;
- **4–6** — relevância moderada;
- **7–9** — alta relevância;
- **10** — altíssima relevância e valor autobiográfico direto.

### Regra principal

> **O arquivo contém informação sobre Kevyn ou apenas informação que Kevyn consumiu?**

Não atribuir nota alta automaticamente a:

- livros;
- PDFs de estudo;
- materiais de aula;
- referências externas;
- documentação técnica;
- artigos de terceiros.

Tendem a merecer prioridade:

- diários;
- reflexões autorais;
- autobiografia;
- conversas em que Kevyn fala de si;
- registros contemporâneos de acontecimentos;
- decisões documentadas;
- projetos descritos pelo próprio Kevyn;
- textos sobre identidade, valores, relações, trabalho e sentido;
- documentos que permitam reconstruir mudanças ao longo do tempo.

## 1.2. Estado de utilização canônica

Para toda fonte analisada:

- [ ] registrar se foi utilizada na camada canônica;
- [ ] distinguir uso total, parcial ou nenhum;
- [ ] explicar brevemente o uso;
- [ ] registrar as notas canônicas relacionadas;
- [ ] registrar claims/evidências quando necessário;
- [ ] marcar `revisitar = sim` quando a fonte ainda tiver conteúdo não explorado.

## 1.3. Fila prioritária

A ordem de curadoria deve favorecer valor informacional, não facilidade de leitura:

1. relevância 10 ainda não utilizada;
2. relevância 7–9 não utilizada ou parcialmente utilizada;
3. relevância 4–6 ainda não utilizada;
4. fontes marcadas para revisitar;
5. fontes ainda sem análise;
6. relevância 1–3;
7. relevância 0 fora da fila de enriquecimento.

- [ ] manter o painel de fila prioritária funcional;
- [ ] evitar processar apenas formatos fáceis;
- [ ] impedir que fontes autobiográficas densas sejam adiadas indefinidamente;
- [ ] acompanhar cobertura por tipo de fonte e período temporal.

## Critério de conclusão da Fase 1

A fase só pode ser considerada amplamente concluída quando:

- todos os arquivos originais tiverem estado de análise conhecido;
- toda fonte tiver relevância 0–10 atribuída ou justificativa explícita para ausência;
- fontes 7–10 estiverem integralmente analisadas ou marcadas para revisita;
- o uso canônico de fontes relevantes estiver rastreado.

---

# FASE 2 — Curadoria profunda das fontes autobiográficas de maior valor

**Objetivo:** construir primeiro uma base canônica forte a partir das fontes mais representativas.

Não analisar os 12 mil arquivos de maneira puramente sequencial.

Selecionar inicialmente os **50–100 documentos de maior valor autobiográfico**, priorizando:

> [!success] Pré-seleção e curadoria Tier A concluídas — 28/09/2026
> **Filtro 1 (triagem por nome/caminho):** 218 candidatos identificados.
> **Filtro 2 (leitura real):** 150 arquivos lidos e classificados (27 Tier A + 56 Tier B + 67 Tier C).
> **Seleção final (Tier A + B):** 83 fontes (27 Tier A / 56 Tier B) com relevância 7–10.
> **Curadoria Tier A:** 27/27 com notas-fonte em `09-Fontes-e-Evidencias/` e integração em `Kevyn Lucas`, `Linha do tempo mestre`, `Claims principais`, `Matriz-Claims` e `Matriz-Evidencias`.
> **Camada canônica nova:** `Aline e o ciclo de reciprocidade e ritmo` + snapshot `Estado atual - setembro de 2026`.
> **Reserva (Tier C restante):** 68 candidatos pendentes de validação no Filtro 2.
> Ver [[98-Pendencias-e-controles/Controle-Curadoria-Originais/Preselecao-Fontes-Autobiograficas-Prioritarias|Pré-seleção de fontes autobiográficas prioritárias]].

- [x] definir a primeira fila de 50–100 fontes prioritárias (Tier A + B = 83);
- [x] diários pessoais (Diário Negro, Diário em Áudio, Diário provisório, Diário Parte 01);
- [x] reflexões escritas pelo próprio Kevyn (Cartas, Tratados, Contratos, Missão);
- [x] transcrições de áudio autobiográfico (Partes 01–03, áudios Jun/2026);
- [x] sessões de terapia (3 sessões com psicóloga Suzana);
- [x] conversas longas com conteúdo pessoal (CNV com Aline, GOOGLE_AI_STUDIO);
- [x] documentos autobiográficos (arquetipos, "Por qual motivo", etc.);
- [x] registros contemporâneos de crises e transições (290726, 260726, Banco de fúria, 270926);
- [x] textos sobre trabalho, relações, identidade e projetos;
- [x] sínteses pessoais cuja proveniência possa ser reconstruída (marcadas como derivadas);
- [x] registros de decisões importantes;
- [x] materiais que cubram períodos pouco representados (Set/2023–Abr/2024 via Diário Parte 01).

- [x] realizar leitura integral e curadoria oficial das 27 fontes do Tier A (notas-fonte + integração canônica em 28/09/2026);
- [ ] realizar leitura integral e curadoria oficial das fontes do Tier C ainda não lidas (ver contagem viva em [[Preselecao-Fontes-Autobiograficas-Prioritarias]]); Tier B concluído (56/56);
- [ ] consolidar notas 0–10 definitivas para todas as fontes Tier A+B após leitura completa;

## Para cada fonte prioritária

- [ ] extrair fatos documentáveis;
- [ ] extrair eventos e datas;
- [ ] extrair pessoas, organizações e lugares;
- [ ] extrair decisões e alternativas;
- [ ] extrair projetos;
- [ ] extrair ideias e conceitos;
- [ ] extrair autodescrições;
- [ ] extrair mudanças explícitas de posição;
- [ ] separar fato, interpretação, hipótese e simbolismo;
- [ ] registrar evidências;
- [ ] registrar claims;
- [ ] integrar somente o que acrescenta ou corrige o conhecimento canônico.

---

# FASE 3 — Enriquecer os núcleos canônicos

**Objetivo:** transformar as fontes prioritárias em uma representação integrada da trajetória.

Áreas centrais a aprofundar:

- [ ] **Kevyn Lucas** — nota de síntese principal;
- [ ] **Linha do tempo mestre**;
- [ ] **Estado atual**;
- [ ] **Trajetória profissional**;
- [ ] **Projetos**;
- [ ] **Relações e rede**;
- [ ] **Estudos e formação**;
- [ ] **Organização do conhecimento**;
- [ ] **Filosofia pessoal**;
- [ ] **Espiritualidade como linguagem de sentido**;
- [ ] **Mudanças de identidade e autoimagem**;
- [ ] **Crises e transições**;
- [ ] **Decisões importantes**;
- [ ] **Práticas, hábitos e sistemas pessoais**.

## Regra de integração

Antes de criar uma nota nova, perguntar:

> **Isso acrescenta, corrige, contradiz ou contextualiza algo que o Vault já sabe?**

Se sim, atualizar a estrutura existente.

Criar nota nova somente quando houver unidade semântica própria.

---

# FASE 4 — Reconstrução autobiográfica verificável

**Objetivo:** produzir uma autobiografia rastreável às fontes, sem depender exclusivamente da memória atual.

- [ ] mapear eventos significativos;
- [ ] associar cada evento a registros contemporâneos e retrospectivos;
- [ ] registrar mudanças de cidade, trabalho, estudo e projetos;
- [ ] registrar crises, reorganizações e viradas de fase;
- [ ] distinguir data do evento de data do relato;
- [ ] identificar eventos conhecidos apenas por reconstrução posterior;
- [ ] registrar divergências entre versões;
- [ ] manter localizadores e fontes.

Resultado esperado:

> uma cronologia na qual seja possível responder não apenas **o que aconteceu**, mas **como sabemos que aconteceu**.

---

# FASE 5 — Análise longitudinal

**Objetivo:** compreender mudanças ao longo do tempo, não apenas acumular descrições.

Perguntas orientadoras:

- [ ] Como a visão de trabalho mudou entre períodos?
- [ ] Quais preocupações desaparecem e quais persistem?
- [ ] Quando projetos ou ideias começaram a aparecer?
- [ ] Como conceitos foram reformulados?
- [ ] Quais valores ganharam ou perderam importância?
- [ ] Quais relações mudaram de função?
- [ ] Quais práticas permaneceram e quais foram abandonadas?
- [ ] Em quais períodos certos padrões se intensificam ou enfraquecem?

A camada canônica deve preferir formulações temporais:

> "Esse padrão aparece fortemente entre março e agosto de 2025 e enfraquece nas fontes de 2026."

em vez de:

> "Kevyn é assim."

---

# FASE 6 — Mapear recorrências sem congelar identidade

**Objetivo:** encontrar padrões documentados sem transformar frequência em essência.

Mapear recorrências de:

- [ ] conceitos;
- [ ] pessoas;
- [ ] projetos;
- [ ] símbolos;
- [ ] preocupações;
- [ ] ambições;
- [ ] conflitos;
- [ ] medos;
- [ ] práticas;
- [ ] formas de organização;
- [ ] temas de estudo;
- [ ] linguagens de sentido.

Para cada padrão relevante:

- [ ] período em que aparece;
- [ ] quantidade e diversidade de fontes;
- [ ] contextos em que aparece;
- [ ] mudanças de intensidade;
- [ ] exceções;
- [ ] interpretações alternativas;
- [ ] grau de confiança.

**Antiobjetivo:** usar contagem de ocorrências como diagnóstico ou definição fixa de personalidade.

---

# FASE 7 — História das próprias ideias

**Objetivo:** reconstruir a genealogia das ideias de Kevyn.

Para ideias centrais:

- [ ] localizar primeira ocorrência conhecida;
- [ ] identificar experiências que antecederam sua formulação;
- [ ] identificar autores, obras ou pessoas associados;
- [ ] registrar versões sucessivas;
- [ ] identificar abandono, retorno e reformulação;
- [ ] distinguir influência documentada de semelhança;
- [ ] relacionar ideias com eventos biográficos quando houver evidência.

Possíveis objetos de genealogia:

- filosofia pessoal;
- vontade;
- disciplina;
- cuidado de si;
- trabalho;
- identidade;
- espiritualidade;
- organização do conhecimento;
- IA;
- criatividade;
- heroísmo;
- simulacro;
- vocação.

---

# FASE 8 — Memória de decisões

**Objetivo:** transformar o Vault em um diário histórico de decisões.

Para decisões relevantes:

- [ ] qual era o problema;
- [ ] quais alternativas existiam;
- [ ] quais critérios foram usados;
- [ ] quais expectativas havia;
- [ ] qual decisão foi tomada;
- [ ] o que aconteceu depois;
- [ ] avaliação retrospectiva;
- [ ] fontes contemporâneas da decisão.

Isso deve permitir perguntas como:

> "Por que tomei essa decisão e o que eu sabia naquele momento?"

---

# FASE 9 — Mapa de projetos e vocação

**Objetivo:** diferenciar intenção, discurso, execução e persistência.

- [ ] mapear projetos mencionados ao longo do tempo;
- [ ] identificar primeira e última ocorrência;
- [ ] registrar estágio real de execução;
- [ ] identificar projetos abandonados, pausados, concluídos e recorrentes;
- [ ] relacionar projetos a habilidades adquiridas;
- [ ] relacionar projetos a contextos profissionais;
- [ ] comparar projetos muito narrados com projetos realmente executados;
- [ ] identificar famílias de projetos e continuidades.

Pergunta central:

> **Quais formas de trabalho e criação persistem na trajetória, independentemente do nome do projeto?**

---

# FASE 10 — Arquivo criativo

**Objetivo:** tornar o acervo reutilizável para produção intelectual e artística sem perder proveniência.

- [ ] indexar ideias originais;
- [ ] localizar fragmentos ensaísticos;
- [ ] mapear conceitos recorrentes;
- [ ] mapear imagens e símbolos;
- [ ] identificar histórias e episódios narráveis;
- [ ] conectar ideias a fontes;
- [ ] criar trilhas para ensaios, vídeos, discursos, livros e projetos artísticos;
- [ ] preservar distinção entre citação original e síntese posterior.

O arquivo criativo deve funcionar como **matéria-prima rastreável**, não como gerador de atribuições falsas.

---

# FASE 11 — Assistente pessoal fundamentado

**Objetivo:** permitir que uma IA responda sobre o passado e a trajetória com base no Vault, apontando fontes.

Perguntas-alvo:

- "O que eu já pensei sobre isso?"
- "Quando comecei a falar dessa ideia?"
- "Como minha posição mudou?"
- "Quais evidências contradizem a narrativa que estou contando agora?"
- "Quais projetos antigos se parecem com esta ideia?"
- "O que eu dizia querer naquela época?"
- "O que realmente aconteceu depois?"
- "Quais fontes sustentam essa conclusão?"

Requisitos:

- [ ] respostas com proveniência;
- [ ] distinção entre registro e síntese;
- [ ] possibilidade de mostrar evidências contrárias;
- [ ] recuperação temporal;
- [ ] capacidade de declarar incerteza;
- [ ] nenhuma resposta autobiográfica importante baseada apenas em uma síntese sem fonte.

---

# FASE 12 — Comparar discurso e trajetória

**Objetivo:** distinguir três dimensões diferentes:

```text
o que Kevyn dizia querer
≠
o que Kevyn dizia ser
≠
o que aparece documentado em decisões e acontecimentos
```

- [ ] mapear metas declaradas;
- [ ] mapear autodescrições;
- [ ] mapear comportamentos/eventos documentados;
- [ ] identificar convergências;
- [ ] identificar tensões;
- [ ] contextualizar temporalmente;
- [ ] evitar transformar divergência em julgamento moral ou diagnóstico;
- [ ] registrar quando não há dados suficientes para comparar.

---

# FASE 13 — Historiografia pessoal

**Objetivo:** preservar a história das interpretações sobre a própria história.

Modelo:

```text
EVENTO
  ↓
REGISTRO CONTEMPORÂNEO
  ↓
INTERPRETAÇÃO POSTERIOR
  ↓
REINTERPRETAÇÃO POSTERIOR
  ↓
ESTADO ATUAL DA NARRATIVA
```

Exemplo conceitual:

```text
O que Kevyn pensava em 2024
≠
como Kevyn de 2026 lembra de 2024
```

Ambos são dados relevantes, mas possuem naturezas diferentes.

Para eventos importantes:

- [ ] preservar versões contemporâneas;
- [ ] preservar memórias retrospectivas;
- [ ] identificar alterações na narrativa;
- [ ] registrar lacunas e contradições;
- [ ] não escolher automaticamente uma versão como "a verdadeira";
- [ ] distinguir evidência sobre o evento de evidência sobre como o evento passou a ser interpretado.

---

# FASE 14 — Sínteses temporais e estados versionados

**Objetivo:** acompanhar a evolução do sistema inteiro.

Produzir periodicamente notas do tipo:

- `Estado de Kevyn — 2026-09`;
- `Estado de Kevyn — 2026-12`;
- etc.

Cada snapshot pode registrar:

- projetos ativos;
- trabalho;
- estudos;
- relações;
- preocupações;
- decisões;
- ideias centrais;
- práticas;
- hipóteses atuais;
- questões abertas;
- mudanças desde o snapshot anterior.

Esses documentos devem ser **retratos datados**, não definições permanentes.

---

# FASE 15 — Diffs autobiográficos

**Objetivo:** tornar mudança explícita e comparável.

Modelo:

```text
KEVYN — JUNHO → SETEMBRO DE 2026

Novos projetos:
+ ...

Projetos abandonados ou pausados:
- ...

Mudanças de visão:
~ trabalho
~ relacionamento
~ tecnologia

Novos padrões recorrentes:
+ ...

Hipóteses enfraquecidas:
- ...

Eventos relevantes:
+ ...

Contradições ainda abertas:
? ...
```

- [ ] definir schema dos snapshots;
- [ ] criar mecanismo de comparação;
- [ ] preservar links para evidências;
- [ ] distinguir mudança real de ausência de dados;
- [ ] registrar quando uma diferença decorre apenas de maior cobertura documental.

---

# FASE 16 — Sistema de perguntas

**Objetivo:** usar o conhecimento acumulado para formular perguntas melhores.

Exemplos prioritários:

> Quais tipos de trabalho Kevyn repetidamente descreve como significativos?

> Há diferença entre os projetos sobre os quais ele mais fala e os projetos nos quais realmente persiste?

> Que acontecimentos antecedem grandes mudanças de direção?

> Quais ideias que hoje parecem fundamentais surgiram recentemente e quais aparecem há anos?

> Quais narrativas sobre si mesmo foram abandonadas?

> Quais pessoas aparecem como pontos de inflexão?

> Onde fontes contemporâneas contradizem reconstruções posteriores?

- [ ] criar banco de perguntas investigativas;
- [ ] vincular perguntas a áreas canônicas;
- [ ] registrar perguntas respondidas, parcialmente respondidas e abertas;
- [ ] transformar contradições em perguntas, não em conclusões precipitadas;
- [ ] usar perguntas para orientar a próxima curadoria.

---

# FASE 17 — Curadoria incremental dos milhares de arquivos restantes

Depois que o núcleo canônico estiver forte, os arquivos restantes devem deixar de ser tratados como "uma montanha de arquivos".

Para cada fonte restante, a pergunta passa a ser:

> **Isso acrescenta, corrige, contradiz ou contextualiza algo que o Vault já sabe?**

Possíveis resultados:

- **acrescenta** → integrar conhecimento novo;
- **corrige** → atualizar claim/nota e preservar histórico;
- **contradiz** → registrar conflito;
- **contextualiza** → fortalecer compreensão existente;
- **reforça** → aumentar confiança/proveniência sem duplicar prosa;
- **não acrescenta** → registrar análise e seguir;
- **irrelevante** → relevância 0, sem exclusão automática.

---

# FASE 18 — Governança, auditoria e saúde do Vault

**Objetivo:** impedir que o crescimento destrua a qualidade.

Acompanhar:

- [ ] porcentagem de originais analisados;
- [ ] distribuição de relevância 0–10;
- [ ] fontes 7–10 não utilizadas;
- [ ] fontes parcialmente utilizadas;
- [ ] fontes marcadas para revisitar;
- [ ] claims sem evidência suficiente;
- [ ] notas canônicas sem proveniência;
- [ ] links quebrados;
- [ ] duplicação semântica;
- [ ] MOCs desatualizados;
- [ ] mudanças de schema;
- [ ] notas isoladas;
- [ ] conflitos não resolvidos;
- [ ] cobertura temporal;
- [ ] cobertura por domínio;
- [ ] concentração excessiva em tipos de fonte fáceis de processar.

## Métricas de progresso

Não medir sucesso apenas por quantidade de arquivos processados.

Acompanhar pelo menos:

1. **Cobertura de análise**  
   arquivos analisados / arquivos originais.

2. **Cobertura de alta relevância**  
   fontes 7–10 integralmente analisadas / fontes 7–10 identificadas.

3. **Cobertura canônica**  
   fontes relevantes que já contribuíram para a camada canônica.

4. **Rastreabilidade**  
   claims importantes com evidência/localizador.

5. **Cobertura temporal**  
   períodos da trajetória representados por fontes suficientes.

6. **Integração**  
   proporção de novos conhecimentos incorporados a estruturas existentes em vez de notas órfãs.

7. **Qualidade longitudinal**  
   quantidade de mudanças temporalmente modeladas em vez de afirmações fixas.

---

# Princípios permanentes

## 1. Não congelar identidade

O Vault não deve transformar padrões em essências.

Evitar:

> "Kevyn é X."

Preferir, quando sustentado:

> "X aparece recorrentemente nesse período e contexto, com estas exceções e mudanças posteriores."

## 2. Frequência não é verdade

Quarenta registros semelhantes podem refletir uma fase, viés de documentação ou repetição de uma mesma fonte.

## 3. A narrativa atual também é uma fonte datada

Uma reconstrução posterior não deve apagar o registro contemporâneo.

## 4. Contradição é dado

Quando duas fontes discordam, registrar a discordância pode ser mais valioso do que escolher uma versão.

## 5. Curadoria é integração

O objetivo não é resumir cada arquivo. É melhorar o modelo canônico.

## 6. Proveniência é obrigatória

Afirmações fortes devem permitir retornar à fonte.

## 7. Hipótese continua hipótese

Repetição por IAs ou notas derivadas não transforma interpretação em fato.

## 8. A pessoa continua mudando

Toda síntese autobiográfica importante deve ser temporalmente contextualizada.

---

# Resultado de longo prazo

O Kevyn Notebook deve se tornar um sistema capaz de:

- reconstruir autobiografia com evidência;
- acompanhar mudança ao longo do tempo;
- preservar a história das próprias interpretações;
- recuperar decisões e seus contextos;
- mapear projetos, vocação e persistência;
- reconstruir genealogias de ideias;
- detectar padrões com contexto temporal;
- alimentar produção criativa;
- sustentar um assistente pessoal fundamentado;
- comparar discurso, desejo, autoimagem e trajetória;
- produzir snapshots e diffs autobiográficos;
- formular perguntas novas a partir do próprio acervo;
- continuar crescendo sem perder proveniência.

O objetivo final não é responder de uma vez:

> **Quem é Kevyn?**

É construir um sistema capaz de acompanhar, com memória, evidência e contexto:

> **Como Kevyn se torna Kevyn ao longo do tempo?**
