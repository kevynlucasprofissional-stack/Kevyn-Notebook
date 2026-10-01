## 1. Princípio central

Todo comportamento desejado precisa passar por esta conversão:

> **Intenção subjetiva → comportamento observável → meta SMART → ação mínima → evidência diária → revisão → ajuste.**

Exemplo:

> “Quero ser mais disciplinado”  
> vira  
> “Durante os próximos 14 dias, vou iniciar meu primeiro bloco de trabalho profundo até 8h30 em pelo menos 10 dos 14 dias, registrando horário de início, duração e principal distração.”

Esse é o ponto mais importante: **o sistema não acompanha personalidade, acompanha evidência comportamental**.

---

# 2. Regras do framework

## Regra 1 — Nada entra no sistema como abstração

Evite metas como:

> “Ser mais focado.”  
> “Ser menos impulsivo.”  
> “Ser mais organizado.”  
> “Ter mais autocontrole.”

Toda meta precisa responder:

- Qual comportamento será observado?
    
- Em qual contexto?
    
- Com qual frequência?
    
- Como será medido?
    
- Até quando?
    
- Qual evidência comprova que aconteceu?
    

---

## Regra 2 — Consequência não é punição

A consequência deve ser **leve, proporcional e corretiva**.

Ela não serve para gerar culpa. Serve para gerar atrito consciente, ajuste e retorno ao plano.

Boas consequências:

- registrar o desvio em 3 linhas;
    
- reduzir a meta para uma ação mínima no dia seguinte;
    
- fazer 10 minutos de reorganização do ambiente;
    
- remover uma distração específica por um bloco de trabalho;
    
- revisar o cartão no Trello antes de continuar;
    
- executar uma reparação pequena e objetiva.
    

Consequências ruins:

- privação de sono;
    
- privação de comida;
    
- humilhação;
    
- punição financeira pesada;
    
- excesso de tarefas compensatórias;
    
- qualquer coisa que gere desregulação emocional.
    

---

## Regra 3 — O sistema mede comportamento, não valor pessoal

Um desvio não significa:

> “Eu falhei.”

Significa:

> “O desenho da meta, do ambiente, do gatilho ou da ação mínima precisa ser ajustado.”

---

## Regra 4 — O ciclo é diário, mas a avaliação real é semanal

O acompanhamento diário serve para gerar dados.

A revisão semanal serve para interpretar padrões.

Evite mudar a estratégia todo dia por ansiedade. Mude quando houver evidência repetida.

---

# 3. Ciclo contínuo do sistema

O ciclo fixo será:

> **Observar → Registrar → Analisar → Ajustar → Executar → Revisar**

Na prática:

1. Você grava um áudio.
    
2. A IA transforma o áudio em dados comportamentais.
    
3. A IA organiza metas SMART.
    
4. As metas viram cartões no Trello.
    
5. Diariamente, você grava novo áudio de acompanhamento.
    
6. A IA compara relato + plano anterior + JSON do Trello.
    
7. O sistema atualiza prioridades, desvios, consequências e próximos passos.
    

---

# 4. Estrutura recomendada no Trello

O Trello permite exportar o quadro em JSON, formato que é mais útil para leitura por máquina do que para leitura humana comum; por isso faz sentido você enviar esse JSON para a IA nas revisões. A Atlassian também informa que o JSON é exportável por membros do quadro, mas não serve para recriar automaticamente um board por importação direta. ([Atlassian Support](https://support.atlassian.com/trello/docs/exporting-data-from-trello/ "Export data from Trello | Trello | Atlassian Support"))

## Listas do quadro

Crie um quadro chamado:

> **Autorregulação Comportamental — SMART**

Com estas listas:

1. **00 — Manual do Sistema**
    
2. **01 — Backlog de Comportamentos**
    
3. **02 — Metas SMART Ativas**
    
4. **03 — Hoje**
    
5. **04 — Em Observação**
    
6. **05 — Ajustar Estratégia**
    
7. **06 — Consolidado / Virou Rotina**
    
8. **07 — Arquivo de Padrões**
    

---

# 5. Modelo de cartão comportamental

Cada comportamento deve virar um cartão.

## Título do cartão

Use este formato:

> **[COMPORTAMENTO] — [FREQUÊNCIA] — [PRAZO]**

Exemplos:

> **Trabalho profundo matinal — 5x por semana — até 30/06**  
> **Responder impulsos com pausa — diário — por 21 dias**  
> **Dormir antes de 23h30 — 5x por semana — por 14 dias**

---

## Descrição do cartão

Copie este modelo:

```markdown
## 1. Comportamento-alvo

Descrever o comportamento que será desenvolvido, corrigido ou acompanhado.

## 2. Formulação SMART

**Específico:**  
O que exatamente será feito?

**Mensurável:**  
Como vou medir?

**Alcançável:**  
Qual é a versão realista dessa meta?

**Relevante:**  
Por que isso importa agora?

**Temporal:**  
Até quando será acompanhado?

## 3. Meta comportamental final

Durante [período], vou [comportamento observável] em [frequência], medindo [indicador], com revisão em [data].

## 4. Indicadores de acompanhamento

- Frequência:
- Duração:
- Horário:
- Taxa de conclusão:
- Nível de dificuldade:
- Principal obstáculo:
- Evidência registrada:

## 5. Ação mínima

Se eu não conseguir fazer a versão ideal, farei pelo menos:

- [ação mínima de 2 a 10 minutos]

## 6. Plano se–então

Se [gatilho/obstáculo], então eu vou [resposta comportamental específica].

## 7. Consequência branda para desvio

Se eu não cumprir sem justificativa forte, vou:

- [consequência leve, proporcional e corretiva]

## 8. Critério de sucesso

A meta será considerada bem-sucedida se:

- [critério objetivo]

## 9. Critério de ajuste

A meta será ajustada se:

- [condição objetiva de repetição de desvio]

## 10. Revisão

- Revisão diária:
- Revisão semanal:
- Data-limite:
```

---

# 6. Checklists dentro de cada cartão

## Checklist 1 — Execução diária

```markdown
- [ ] Executei o comportamento-alvo
- [ ] Registrei evidência
- [ ] Registrei horário ou contexto
- [ ] Registrei dificuldade principal
- [ ] Marquei se houve desvio
```

## Checklist 2 — Em caso de desvio

```markdown
- [ ] O desvio foi registrado sem autoataque
- [ ] Identifiquei o gatilho
- [ ] Identifiquei o obstáculo real
- [ ] Apliquei consequência branda
- [ ] Defini ajuste para a próxima tentativa
```

## Checklist 3 — Revisão semanal

```markdown
- [ ] Calculei taxa de cumprimento
- [ ] Identifiquei padrões repetidos
- [ ] Ajustei meta se necessário
- [ ] Removi metas irrelevantes
- [ ] Mantive metas que ainda fazem sentido
- [ ] Promovi hábitos consolidados para “Virou Rotina”
```

---

# 7. Indicadores simples de acompanhamento

Use poucos indicadores. O sistema precisa ser sustentável.

## Indicadores principais

|Indicador|Como medir|
|---|---|
|Cumprimento|Sim / Não|
|Frequência|Quantas vezes na semana|
|Intensidade|0 a 3|
|Dificuldade|0 a 3|
|Desvio|Sim / Não|
|Motivo do desvio|Texto curto|
|Ação mínima feita|Sim / Não|
|Consequência aplicada|Sim / Não|
|Próximo ajuste|Texto curto|

## Escala de dificuldade

```markdown
0 = sem dificuldade
1 = dificuldade leve
2 = dificuldade moderada
3 = dificuldade alta
```

## Escala de aderência semanal

```markdown
0% a 39% = meta mal calibrada ou ambiente inadequado
40% a 69% = meta possível, mas precisa de ajuste
70% a 89% = boa aderência
90% a 100% = comportamento em consolidação
```

---

# 8. Biblioteca de consequências brandas

Use consequências pequenas, repetíveis e não dramáticas.

## Consequências de consciência

```markdown
- Escrever 3 linhas: “O que aconteceu, qual foi o gatilho, qual será o ajuste?”
- Gravar áudio de 2 minutos explicando o desvio.
- Comentar no cartão do Trello: “Desvio registrado — causa provável: ____.”
```

## Consequências de organização

```markdown
- Organizar o ambiente por 10 minutos.
- Preparar a próxima execução com antecedência.
- Remover uma distração do ambiente por um bloco.
```

## Consequências de redução

```markdown
- Reduzir a meta do dia seguinte para a ação mínima.
- Trocar intensidade por consistência.
- Diminuir a meta pela metade por 48h para recuperar aderência.
```

## Consequências de reparação

```markdown
- Fazer uma versão curta da tarefa ainda hoje.
- Repor apenas 10 minutos, sem tentar “compensar tudo”.
- Enviar uma mensagem, organizar um arquivo ou fechar uma pendência pequena relacionada ao comportamento.
```

---

# 9. Prompt 1 — Configuração inicial do sistema

Use [[Prompt 1 — Configuração inicial do sistema|este prompt]] quando você enviar o primeiro áudio com suas metas comportamentais.

---

# 10. Prompt 2 — Acompanhamento diário

Use [[Prompt 2 — Acompanhamento diário|este prompt]] todos os dias, depois que o sistema já estiver criado.

Ele aceita três entradas:

1. resumo anterior;
2. transcrição do áudio diário;
3. JSON exportado do Trello, se houver.


---

# 11. Modelo de áudio diário

Para facilitar, use sempre o mesmo roteiro no áudio.

```markdown
Hoje eu consegui cumprir:

Hoje eu não consegui cumprir:

O principal obstáculo foi:

O principal padrão que percebi em mim foi:

O momento em que mais desviei foi:

A meta que ainda faz sentido é:

A meta que talvez precise ser ajustada é:

A menor ação possível para amanhã é:

A consequência branda que aceito aplicar, se fizer sentido, é:
````

---

# 12. Modelo de resumo para transportar entre chats

Sempre que terminar uma grande revisão, peça para a IA gerar algo assim:

```markdown
Resumo do Sistema de Autorregulação Comportamental

Estou usando um sistema de autorregulação baseado em metas SMART, observação diária, revisão contínua e organização no Trello.

O ciclo é: observar → registrar → analisar → ajustar → executar → revisar.

Minhas metas ativas são:

1. [meta 1]
2. [meta 2]
3. [meta 3]

Os principais indicadores acompanhados são:

- cumprimento diário;
- frequência semanal;
- dificuldade de execução;
- obstáculos recorrentes;
- desvios;
- ação mínima;
- consequência branda aplicada;
- ajustes necessários.

Os principais padrões observados até agora são:

- [padrão 1]
- [padrão 2]
- [padrão 3]

As regras do sistema são:

- comportamento precisa ser observável;
- meta precisa ser SMART;
- desvio não é culpa, é dado;
- consequência precisa ser leve e proporcional;
- ajustes pequenos vêm antes de mudanças grandes;
- consistência vale mais que intensidade.

Na próxima análise, você deve usar este resumo, a nova transcrição do meu áudio diário e, se houver, o JSON exportado do Trello para atualizar o plano.
```

---

# 13. Versão enxuta do protocolo

Use esta versão quando quiser lembrar rapidamente do sistema:

```markdown
1. Grave um áudio livre.
2. Transcreva.
3. Envie para a IA com o Prompt 1, se for configuração inicial.
4. Transforme cada comportamento em meta SMART.
5. Crie cartões no Trello.
6. Execute diariamente.
7. Grave áudio de acompanhamento.
8. Envie resumo anterior + áudio novo + JSON do Trello com o Prompt 2.
9. Atualize metas, cartões, consequências e prioridades.
10. Repita o ciclo.
```

O nome mais preciso para esse método seria:

> **Protocolo SMART de Autorregulação Comportamental Observável**

Ele é forte porque tira o comportamento do campo da intenção vaga e coloca em um sistema de evidência, revisão e ajuste.