## Prompt para verificar se os cursos
Verifica se todos as aulas do curso foram baixadas. No html tem a lista completa do curso e no txt tem todas as aulas que foram baixadas.


















Quero que você analise o problema/projeto descrito abaixo, descubra quais melhorias realmente devem ser realizadas e, somente depois, crie um **fluxo final de prompts de implementação**.

O trabalho deve acontecer obrigatoriamente em **duas grandes etapas sequenciais**:

1. **Descoberta e validação das hipóteses**
    
2. **Construção do fluxo de prompts para implementação**
    

Não comece a implementar durante a etapa de descoberta.

---

# CONTEXTO / OBJETIVO

[COLE AQUI O CONTEXTO DO PROJETO, PROBLEMA, FEEDBACK DO CLIENTE, ESTADO ATUAL, RESULTADO DESEJADO ETC.]

---

# HIPÓTESES QUE EU JÁ QUERO TESTAR

Além das hipóteses que você próprio levantar durante a análise, quero que obrigatoriamente investigue também as hipóteses abaixo.

Elas são **hipóteses, não instruções de implementação**. Portanto, não presuma que estejam corretas. Teste-as com o mesmo rigor das hipóteses que você levantar e descarte, corrija, divida ou combine aquelas que não sobreviverem à análise.

### Minhas hipóteses

1. [HIPÓTESE 1]
    
2. [HIPÓTESE 2]
    
3. [HIPÓTESE 3]
    
4. [...]
    

Se este campo estiver vazio, simplesmente levante todas as hipóteses necessárias por conta própria.

---

# ETAPA 1 — DESCOBERTA E VALIDAÇÃO DAS HIPÓTESES

Trabalhe obrigatoriamente de forma **incremental, investigativa e verificável**, utilizando este framework:

**Hipótese → Investigação/Teste → Análise do resultado → Ajuste ou refutação → Novo teste, se necessário → Validação → Registro da conclusão → Próxima hipótese**

## Regra fundamental

**Não investigue várias hipóteses simultaneamente.**

Escolha **uma hipótese por vez** e trabalhe nela até chegar a uma conclusão suficientemente sustentada antes de avançar.

Para cada hipótese:

### 1. Formule a hipótese

Explique claramente:

- qual é a hipótese;
    
- qual problema ela pretende explicar ou resolver;
    
- por que ela é plausível;
    
- quais evidências seriam esperadas caso ela esteja correta;
    
- quais evidências poderiam refutá-la.
    

### 2. Investigue

Utilize tudo que estiver disponível e for relevante, como:

- código;
    
- arquitetura;
    
- banco de dados;
    
- logs;
    
- interfaces;
    
- comportamento atual;
    
- documentação;
    
- testes;
    
- dependências;
    
- fluxos existentes;
    
- requisitos;
    
- feedbacks;
    
- resultados observáveis.
    

Não valide uma hipótese apenas porque ela parece razoável.

### 3. Tente refutar a própria hipótese

Procure deliberadamente:

- contraexemplos;
    
- efeitos colaterais;
    
- pressupostos incorretos;
    
- conflitos com outras partes do sistema;
    
- soluções mais simples;
    
- causas alternativas;
    
- casos em que a hipótese não resolveria o problema.
    

### 4. Ajuste a hipótese quando necessário

Se a hipótese estiver parcialmente correta, reformule-a.

Uma hipótese pode ser:

- validada;
    
- validada parcialmente;
    
- reformulada;
    
- dividida em hipóteses menores;
    
- combinada posteriormente com outra;
    
- descartada.
    

Não force uma conclusão binária quando a evidência apontar para algo mais preciso.

### 5. Teste novamente

Sempre que houver uma reformulação relevante, execute um novo ciclo de verificação sobre a hipótese corrigida.

Continue o loop até que haja evidência suficiente para classificá-la.

### 6. Registre a conclusão

Ao encerrar cada hipótese, registre:

**Hipótese:**  
[...]

**Resultado:**  
Validada / Parcialmente validada / Reformulada / Refutada

**Evidências:**  
[...]

**Conclusão:**  
[...]

**Implicação prática:**  
[...]

**Deve entrar no fluxo final de implementação?**  
Sim / Não / Apenas na forma reformulada

Somente depois avance para a próxima hipótese.

---

# LEVANTAMENTO DE NOVAS HIPÓTESES

Não se limite às hipóteses fornecidas por mim.

Durante a investigação, identifique novas hipóteses sempre que surgirem indícios de:

- causa raiz não considerada;
    
- problema arquitetural;
    
- inconsistência de UX ou fluxo;
    
- dívida técnica;
    
- bug;
    
- oportunidade de simplificação;
    
- risco de regressão;
    
- melhoria de confiabilidade;
    
- melhoria de performance;
    
- necessidade de testes;
    
- necessidade de observabilidade;
    
- problema de dados;
    
- problema de segurança;
    
- comportamento incompatível com o objetivo do projeto.
    

Entretanto:

**não transforme todas as ideias em implementação automaticamente.**

Cada nova hipótese relevante deve passar pelo mesmo processo de teste e validação antes de poder entrar no fluxo final.

---

# CRITÉRIO DE ENCERRAMENTO DA INVESTIGAÇÃO

Continue levantando e testando hipóteses até que novas hipóteses plausíveis deixem de produzir melhorias materiais para o objetivo.

Não encerre simplesmente porque as hipóteses inicialmente fornecidas foram analisadas.

Antes de concluir esta etapa, faça uma última pergunta interna:

> "Existe alguma explicação, melhoria, risco ou solução relevante que ainda não investiguei e que poderia alterar materialmente o resultado?"

Se sim, transforme-a em uma nova hipótese e teste-a.

Se não, encerre a investigação.

---

# ETAPA 2 — CONSOLIDAÇÃO

Após terminar **todas** as hipóteses, faça uma consolidação das conclusões.

Organize somente as hipóteses validadas ou reformuladas que realmente merecem implementação.

Para cada uma, determine:

- problema resolvido;
    
- solução recomendada;
    
- prioridade;
    
- dependências;
    
- risco;
    
- esforço estimado;
    
- partes do sistema afetadas;
    
- testes necessários;
    
- critério objetivo de conclusão.
    

Também identifique relações entre elas.

Se duas ou mais melhorias pequenas:

- alterarem a mesma região do sistema;
    
- tiverem forte dependência entre si;
    
- puderem ser implementadas juntas sem aumentar significativamente a complexidade;
    
- puderem ser verificadas conjuntamente com clareza;
    

elas podem ser agrupadas.

Por outro lado, melhorias:

- grandes;
    
- arquiteturalmente complexas;
    
- arriscadas;
    
- que exijam bastante raciocínio;
    
- que afetem muitas partes do sistema;
    
- ou que precisem de validação própria;
    

devem ficar **isoladas em prompts individuais**.

O objetivo é encontrar o melhor equilíbrio entre:

**economia de prompts × capacidade de raciocínio × qualidade da implementação × facilidade de validação.**

Não crie dezenas de prompts desnecessariamente, mas também não crie prompts gigantes que misturem trabalhos complexos demais.

---

# ETAPA 3 — CRIAÇÃO DO FLUXO FINAL DE PROMPTS

Somente agora crie o fluxo de prompts que será enviado para a IA responsável pela implementação.

O fluxo deve representar a **ordem ideal de execução**, respeitando:

- dependências técnicas;
    
- risco;
    
- fundações necessárias;
    
- facilidade de teste;
    
- possibilidade de regressão;
    
- menor retrabalho possível.
    

Cada prompt deve ser **autossuficiente** e pronto para copiar e colar.

---

# REGRA OBRIGATÓRIA PARA TODOS OS PROMPTS DE IMPLEMENTAÇÃO

Todo prompt de implementação deverá começar com esta instrução:

> Trabalhe obrigatoriamente de forma incremental e verificável, utilizando o seguinte framework:
> 
> **Implementação → Loop de verificação e ajuste → Validação da implementação → Próxima implementação**
> 
> Não implemente vários itens independentes simultaneamente. Cada melhoria deve ser implementada, testada, corrigida e considerada estável antes de avançar para a próxima.

---

# LOOP INTERNO DE IMPLEMENTAÇÃO

Dentro de cada prompt, a IA deverá executar cada item seguindo:

### 1. Inspecionar antes de alterar

Entender:

- estado atual;
    
- arquivos envolvidos;
    
- comportamento atual;
    
- dependências;
    
- possíveis impactos.
    

Não presumir que a solução planejada ainda corresponde exatamente ao estado atual do projeto.

### 2. Implementar

Realizar apenas a alteração atual.

### 3. Verificar

Executar os testes adequados, que podem incluir:

- testes unitários;
    
- testes de integração;
    
- testes E2E;
    
- testes manuais;
    
- inspeção de banco;
    
- análise de logs;
    
- compilação;
    
- lint;
    
- typecheck;
    
- build;
    
- execução real;
    
- cenários adversariais.
    

### 4. Procurar regressões

Verificar explicitamente se a implementação:

- quebrou comportamentos existentes;
    
- criou inconsistências;
    
- introduziu código duplicado;
    
- deixou código morto;
    
- alterou fluxos não relacionados;
    
- criou falhas silenciosas.
    

### 5. Ajustar

Se houver qualquer problema, corrigir e executar novamente os testes.

Repetir:

**Implementar → Testar → Analisar → Ajustar → Testar novamente**

até que a implementação esteja estável.

### 6. Validar

Somente considerar o item concluído quando os critérios objetivos de aceitação forem satisfeitos.

### 7. Avançar

Apenas depois iniciar o próximo item daquele prompt.

---

# PROIBIÇÕES

Durante a implementação:

- não mascarar erros apenas para fazer testes passarem;
    
- não remover testes válidos para evitar falhas;
    
- não substituir comportamento real por mocks permanentes;
    
- não declarar sucesso apenas porque o código compila;
    
- não considerar uma implementação concluída sem verificar o comportamento;
    
- não ignorar regressões descobertas;
    
- não expandir desnecessariamente o escopo;
    
- não implementar hipóteses que foram refutadas durante a investigação.
    

Se durante a implementação surgir uma descoberta que invalide uma decisão anterior, pare aquela implementação, investigue a nova evidência e ajuste a solução antes de continuar.

---

# FORMATO DA RESPOSTA FINAL

Quero sua resposta dividida exatamente nestas seções:

## 1. Diagnóstico geral

Resumo do que você concluiu sobre o problema.

## 2. Hipóteses investigadas

Para cada hipótese:

- hipótese;
    
- origem: **minha** ou **levantada por você**;
    
- testes/investigações realizados;
    
- evidências;
    
- resultado;
    
- implicação.
    

## 3. Hipóteses descartadas

Explique resumidamente o que foi descartado e por quê.

## 4. Hipóteses validadas

Liste apenas aquilo que realmente deverá orientar a implementação.

## 5. Arquitetura da solução

Explique como as hipóteses validadas se transformam em uma solução coerente.

## 6. Estratégia de agrupamento

Explique:

- o que foi agrupado;
    
- o que ficou isolado;
    
- por quê.
    

## 7. Ordem ideal de implementação

Apresente a sequência e suas dependências.

## 8. Fluxo final de prompts

Entregue:

### Prompt 1 — [Título]

```text
[PROMPT COMPLETO E AUTOSSUFICIENTE]
```

### Prompt 2 — [Título]

```text
[PROMPT COMPLETO E AUTOSSUFICIENTE]
```

E assim sucessivamente.

## 9. Critério final de conclusão

Crie um último prompt de validação geral que revise o resultado completo após todas as implementações, procurando:

- implementações incompletas;
    
- bugs;
    
- regressões;
    
- inconsistências;
    
- código morto;
    
- problemas de arquitetura;
    
- falhas de UX;
    
- falhas de segurança;
    
- testes insuficientes;
    
- divergências entre o objetivo original e o resultado final.
    

Esse último prompt também deverá operar em loop:

**Auditoria → Identificação de problema → Correção → Reteste → Nova auditoria**

até que não sejam encontrados problemas materiais.

---

# PRINCÍPIO CENTRAL

Não quero que você simplesmente transforme minhas ideias em tarefas.

Quero que você primeiro descubra **o que realmente deveria ser feito**.

Depois quero que transforme apenas as conclusões que sobreviveram à investigação em **um fluxo de implementação eficiente, ordenado, verificável e resistente a erros**.

Em resumo:

**Hipóteses → Testes → Refutação/Ajuste → Validação → Consolidação → Priorização → Fluxo de prompts → Implementação em loop → Validação final.**














































































## Prompts de loop
Trabalhe obrigatoriamente de forma **incremental e verificável**, utilizando o seguinte framework: **Implementação → Loop de verificação e ajuste → Validação da implementação → Próxima implementação** Não implemente vários itens simultaneamente. Cada melhoria deve ser concluída, testada e considerada estável antes de avançar para a próxima.

## Prompts de levantamento de hipótese
Cria um prompt para eu te reencaminhar e você reavaliar tudo para ver se realmente está funcionando. Para criar este prompt trabalhe com levantamento de hipóteses, validação, e escrita do prompt final sob as hipóteses validadas. O objetivo é fazer esse fluxo funcionar.

Trabalhe obrigatoriamente de forma **incremental e verificável**, utilizando o seguinte framework: **Hipótese → Loop de verificação e ajuste da hipótese → Validação da hipótese e incrementação no prompt final → Próxima hipótese** Não levante várias hipóteses simultaneamente. Cada hipótese deve ser concluída, testada e considerada válida antes de avançar para a próxima.

Por fim me retorne o prompt para eu te reencaminhar e fazer você implementar no projeto todas as hipóteses válidas. O primeiro parágrafo desse prompt que me retornar deve ser esse:

Trabalhe obrigatoriamente de forma **incremental e verificável**, utilizando o seguinte framework: **Implementação → Loop de verificação e ajuste → Validação da implementação → Próxima implementação** Não implemente vários itens simultaneamente. Cada melhoria deve ser concluída, testada e considerada estável antes de avançar para a próxima.

## Prompt para implementar camada de diagnóstico
Preciso que você revise todo o código do projeto e implemente mecanismos de diagnóstico que nos permitam identificar o que aconteceu sempre que o software não funcionar como esperado.
O sistema deve conseguir registrar situações como logs do powershell, erros, falhas inesperadas, travamentos, baixa precisão do modelo, resultados inconsistentes ou qualquer comportamento anormal durante a execução.
Além disso, quero que o projeto gere automaticamente um relatório detalhado ao final de cada execução, contendo informações sobre tudo o que ocorreu internamente, incluindo os lotes processados, etapas executadas, erros encontrados, decisões tomadas pelo sistema, resultados obtidos e possíveis pontos de falha.
Esse relatório deve ser salvo em um formato fácil de compartilhar e analisar, para que eu possa encaminhá-lo posteriormente a você. A ideia é permitir que, a partir desse diagnóstico, seja possível reconstruir o que aconteceu durante a execução, identificar bugs, entender suas possíveis causas, levantar hipóteses melhores e formular perguntas mais precisas para corrigir e aprimorar o software.

## Comparar aulas baixadas com total de aulas

Do HTML você vai conseguir extrair a lista de aulas completas do curso, e no txt tem todas as aulas que baixei, consegue verificar se está faltando alguma aula para baixar? Faça isso ao comparar a lista de aulas baixadas com a lista de aulas completas que você vai extrair do HTML.

## Fluxo de prompts Lovable

Cria para mim um fluxo de prompts para eu mandar para o Lovalble e ele fazer todos estes ajustes passo a passo. Quero que pense em qual o equílibrio perfeito entre economia de prompts e maximização de resultados, não quero ter que enviar prompts de mais, só que ao mesmo tempo o Lovable tem um mecanismo interno de economia de tokens que faz ele não trabalhar bem com prompts gigantes, então devemos agrupar tarefas que são parecidas que vão requerir pouco esforço e manter tarefas grandes sozinhas para o Lovable conseguir focar todas as forças dele apenas nessa tarefa difícil.

## Limpeza total de usuários e cadastros do ACIRV Connect

Objetivo: zerar toda a memória de usuários da plataforma, mantendo o evento SudoExpo 2026, os segmentos e a taxonomia. A conta de equipe (admin) atual é preservada.

## O que será apagado

- Perfis de participantes e tudo ligado a eles: ofertas, necessidades, segmentos do perfil
    
- Matches, motivos de match, histórico e decisões de match, revisões de admin de match
    
- Conexões e todo o histórico: eventos, notas, histórico de status (hoje zeradas, mas incluídas por segurança)
    
- Consentimentos
    
- Registros de IA, eventos de analytics e logs de auditoria
    
- Todas as contas de login de visitantes (usuários anônimos e telefones verificados via WhatsApp), incluindo sessões, tokens de atualização e códigos OTP pendentes — qualquer novo acesso começa do zero
    

## O que será mantido

- Evento SudoExpo 2026
    
- Segmentos, taxonomia e relações de taxonomia
    
- A conta de equipe/admin atual e seu vínculo em `event_staff`
    

## Detalhes técnicos

1. Uma migração fará a limpeza em ordem de dependência: tabelas filhas primeiro (`match_reasons`, `match_status_history`, `match_decisions`, `match_admin_reviews`, `connection_*`, `connections`, `matches`, `profile_offers`, `profile_needs`, `profile_segments`, `consents`, `ai_runs`, `analytics_events`, `audit_logs`) e depois `profiles`.
    
2. Em seguida, remoção das contas em `auth.users` que não pertencem à equipe: exclui todo `auth.users` cujo `id` não esteja em `event_staff.user_id` nem em `staff_roles.user_id`. Isso remove em cascata identidades, sessões, refresh tokens e one-time tokens de OTP.
    
3. Verificação pós-execução: contagem zerada nas tabelas acima, `event_staff` com 1 registro, evento e taxonomia intactos, e o painel público (`/publico`) exibindo zeros a partir da RPC real.
    

Após a limpeza, um novo cadastro pelo mesmo WhatsApp será tratado como primeiro acesso.



---

## Fluxo de prompts geral

Quero que você analise o problema/projeto descrito abaixo, descubra quais melhorias realmente devem ser realizadas e, somente depois, crie um **fluxo final de prompts de implementação**.

O trabalho deve acontecer obrigatoriamente em **duas grandes etapas sequenciais**:

1. **Descoberta e validação das hipóteses**
    
2. **Construção do fluxo de prompts para implementação**
    

Não comece a implementar durante a etapa de descoberta.

---

# CONTEXTO / OBJETIVO

O **ECO V5** é um sistema para construir **modelos computacionais rastreáveis de pessoas a partir de corpora documentais** e, posteriormente, utilizar esses modelos para gerar clones conversacionais capazes de responder de maneira compatível com o conhecimento, os padrões de decisão, os valores, o estilo e outras características inferíveis da pessoa analisada.

O objetivo central **não é simplesmente criar a imitação mais convincente possível**. O projeto foi concebido para produzir o modelo de pessoa mais **rastreável, auditável, falseável e empiricamente verificável possível**, distinguindo explicitamente aquilo que é fato documentado, autorrelato, inferência, hipótese, extrapolação ou informação contraditória.

---

# HIPÓTESES QUE EU JÁ QUERO TESTAR

Além das hipóteses que você próprio levantar durante a análise, quero que obrigatoriamente investigue também as hipóteses abaixo.

Elas são **hipóteses, não instruções de implementação**. Portanto, não presuma que estejam corretas. Teste-as com o mesmo rigor das hipóteses que você levantar e descarte, corrija, divida ou combine aquelas que não sobreviverem à análise.

### Minhas hipóteses

1. Quero uma CLI com seleção via clique em atalho número, seleção com mouse, ou setinhas com enter para confirmar.
2. No próximo arquivo podia vir junto um .bat que já vem com o script que cria o ambiente virtual, ativa, faz a instalação e por fim testa com o doctor e version me retornando o resultado.
3. Tornar configurável a opção de utilizar chaves API de modelos pagos, ou chaves API do Google Ai Studio, ou do Nvidia NIM, ou qualquer outra que eu preferir.

Se este campo estiver vazio, simplesmente levante todas as hipóteses necessárias por conta própria.

---

# ETAPA 1 — DESCOBERTA E VALIDAÇÃO DAS HIPÓTESES

Trabalhe obrigatoriamente de forma **incremental, investigativa e verificável**, utilizando este framework:

**Hipótese → Investigação/Teste → Análise do resultado → Ajuste ou refutação → Novo teste, se necessário → Validação → Registro da conclusão → Próxima hipótese**

## Regra fundamental

**Não investigue várias hipóteses simultaneamente.**

Escolha **uma hipótese por vez** e trabalhe nela até chegar a uma conclusão suficientemente sustentada antes de avançar.

Para cada hipótese:

### 1. Formule a hipótese

Explique claramente:

- qual é a hipótese;
    
- qual problema ela pretende explicar ou resolver;
    
- por que ela é plausível;
    
- quais evidências seriam esperadas caso ela esteja correta;
    
- quais evidências poderiam refutá-la.
    

### 2. Investigue

Utilize tudo que estiver disponível e for relevante, como:

- código;
    
- arquitetura;
    
- banco de dados;
    
- logs;
    
- interfaces;
    
- comportamento atual;
    
- documentação;
    
- testes;
    
- dependências;
    
- fluxos existentes;
    
- requisitos;
    
- feedbacks;
    
- resultados observáveis.
    

Não valide uma hipótese apenas porque ela parece razoável.

### 3. Tente refutar a própria hipótese

Procure deliberadamente:

- contraexemplos;
    
- efeitos colaterais;
    
- pressupostos incorretos;
    
- conflitos com outras partes do sistema;
    
- soluções mais simples;
    
- causas alternativas;
    
- casos em que a hipótese não resolveria o problema.
    

### 4. Ajuste a hipótese quando necessário

Se a hipótese estiver parcialmente correta, reformule-a.

Uma hipótese pode ser:

- validada;
    
- validada parcialmente;
    
- reformulada;
    
- dividida em hipóteses menores;
    
- combinada posteriormente com outra;
    
- descartada.
    

Não force uma conclusão binária quando a evidência apontar para algo mais preciso.

### 5. Teste novamente

Sempre que houver uma reformulação relevante, execute um novo ciclo de verificação sobre a hipótese corrigida.

Continue o loop até que haja evidência suficiente para classificá-la.

### 6. Registre a conclusão

Ao encerrar cada hipótese, registre:

**Hipótese:**  
[...]

**Resultado:**  
Validada / Parcialmente validada / Reformulada / Refutada

**Evidências:**  
[...]

**Conclusão:**  
[...]

**Implicação prática:**  
[...]

**Deve entrar no fluxo final de implementação?**  
Sim / Não / Apenas na forma reformulada

Somente depois avance para a próxima hipótese.

---

# LEVANTAMENTO DE NOVAS HIPÓTESES

Não se limite às hipóteses fornecidas por mim.

Durante a investigação, identifique novas hipóteses sempre que surgirem indícios de:

- causa raiz não considerada;
    
- problema arquitetural;
    
- inconsistência de UX ou fluxo;
    
- dívida técnica;
    
- bug;
    
- oportunidade de simplificação;
    
- risco de regressão;
    
- melhoria de confiabilidade;
    
- melhoria de performance;
    
- necessidade de testes;
    
- necessidade de observabilidade;
    
- problema de dados;
    
- problema de segurança;
    
- comportamento incompatível com o objetivo do projeto.
    

Entretanto:

**não transforme todas as ideias em implementação automaticamente.**

Cada nova hipótese relevante deve passar pelo mesmo processo de teste e validação antes de poder entrar no fluxo final.

---

# CRITÉRIO DE ENCERRAMENTO DA INVESTIGAÇÃO

Continue levantando e testando hipóteses até que novas hipóteses plausíveis deixem de produzir melhorias materiais para o objetivo.

Não encerre simplesmente porque as hipóteses inicialmente fornecidas foram analisadas.

Antes de concluir esta etapa, faça uma última pergunta interna:

> "Existe alguma explicação, melhoria, risco ou solução relevante que ainda não investiguei e que poderia alterar materialmente o resultado?"

Se sim, transforme-a em uma nova hipótese e teste-a.

Se não, encerre a investigação.

---

# ETAPA 2 — CONSOLIDAÇÃO

Após terminar **todas** as hipóteses, faça uma consolidação das conclusões.

Organize somente as hipóteses validadas ou reformuladas que realmente merecem implementação.

Para cada uma, determine:

- problema resolvido;
    
- solução recomendada;
    
- prioridade;
    
- dependências;
    
- risco;
    
- esforço estimado;
    
- partes do sistema afetadas;
    
- testes necessários;
    
- critério objetivo de conclusão.
    

Também identifique relações entre elas.

Se duas ou mais melhorias pequenas:

- alterarem a mesma região do sistema;
    
- tiverem forte dependência entre si;
    
- puderem ser implementadas juntas sem aumentar significativamente a complexidade;
    
- puderem ser verificadas conjuntamente com clareza;
    

elas podem ser agrupadas.

Por outro lado, melhorias:

- grandes;
    
- arquiteturalmente complexas;
    
- arriscadas;
    
- que exijam bastante raciocínio;
    
- que afetem muitas partes do sistema;
    
- ou que precisem de validação própria;
    

devem ficar **isoladas em prompts individuais**.

O objetivo é encontrar o melhor equilíbrio entre:

**economia de prompts × capacidade de raciocínio × qualidade da implementação × facilidade de validação.**

Não crie dezenas de prompts desnecessariamente, mas também não crie prompts gigantes que misturem trabalhos complexos demais.

---

# ETAPA 3 — CRIAÇÃO DO FLUXO FINAL DE PROMPTS

Somente agora crie o fluxo de prompts que será enviado para a IA responsável pela implementação.

O fluxo deve representar a **ordem ideal de execução**, respeitando:

- dependências técnicas;
    
- risco;
    
- fundações necessárias;
    
- facilidade de teste;
    
- possibilidade de regressão;
    
- menor retrabalho possível.
    

Cada prompt deve ser **autossuficiente** e pronto para copiar e colar.

---

# REGRA OBRIGATÓRIA PARA TODOS OS PROMPTS DE IMPLEMENTAÇÃO

Todo prompt de implementação deverá começar com esta instrução:

> Trabalhe obrigatoriamente de forma incremental e verificável, utilizando o seguinte framework:
> 
> **Implementação → Loop de verificação e ajuste → Validação da implementação → Próxima implementação**
> 
> Não implemente vários itens independentes simultaneamente. Cada melhoria deve ser implementada, testada, corrigida e considerada estável antes de avançar para a próxima.

---

# LOOP INTERNO DE IMPLEMENTAÇÃO

Dentro de cada prompt, a IA deverá executar cada item seguindo:

### 1. Inspecionar antes de alterar

Entender:

- estado atual;
    
- arquivos envolvidos;
    
- comportamento atual;
    
- dependências;
    
- possíveis impactos.
    

Não presumir que a solução planejada ainda corresponde exatamente ao estado atual do projeto.

### 2. Implementar

Realizar apenas a alteração atual.

### 3. Verificar

Executar os testes adequados, que podem incluir:

- testes unitários;
    
- testes de integração;
    
- testes E2E;
    
- testes manuais;
    
- inspeção de banco;
    
- análise de logs;
    
- compilação;
    
- lint;
    
- typecheck;
    
- build;
    
- execução real;
    
- cenários adversariais.
    

### 4. Procurar regressões

Verificar explicitamente se a implementação:

- quebrou comportamentos existentes;
    
- criou inconsistências;
    
- introduziu código duplicado;
    
- deixou código morto;
    
- alterou fluxos não relacionados;
    
- criou falhas silenciosas.
    

### 5. Ajustar

Se houver qualquer problema, corrigir e executar novamente os testes.

Repetir:

**Implementar → Testar → Analisar → Ajustar → Testar novamente**

até que a implementação esteja estável.

### 6. Validar

Somente considerar o item concluído quando os critérios objetivos de aceitação forem satisfeitos.

### 7. Avançar

Apenas depois iniciar o próximo item daquele prompt.

---

# PROIBIÇÕES

Durante a implementação:

- não mascarar erros apenas para fazer testes passarem;
    
- não remover testes válidos para evitar falhas;
    
- não substituir comportamento real por mocks permanentes;
    
- não declarar sucesso apenas porque o código compila;
    
- não considerar uma implementação concluída sem verificar o comportamento;
    
- não ignorar regressões descobertas;
    
- não expandir desnecessariamente o escopo;
    
- não implementar hipóteses que foram refutadas durante a investigação.
    

Se durante a implementação surgir uma descoberta que invalide uma decisão anterior, pare aquela implementação, investigue a nova evidência e ajuste a solução antes de continuar.

---

# FORMATO DA RESPOSTA FINAL

Quero sua resposta dividida exatamente nestas seções:

## 1. Diagnóstico geral

Resumo do que você concluiu sobre o problema.

## 2. Hipóteses investigadas

Para cada hipótese:

- hipótese;
    
- origem: **minha** ou **levantada por você**;
    
- testes/investigações realizados;
    
- evidências;
    
- resultado;
    
- implicação.
    

## 3. Hipóteses descartadas

Explique resumidamente o que foi descartado e por quê.

## 4. Hipóteses validadas

Liste apenas aquilo que realmente deverá orientar a implementação.

## 5. Arquitetura da solução

Explique como as hipóteses validadas se transformam em uma solução coerente.

## 6. Estratégia de agrupamento

Explique:

- o que foi agrupado;
    
- o que ficou isolado;
    
- por quê.
    

## 7. Ordem ideal de implementação

Apresente a sequência e suas dependências.

## 8. Fluxo final de prompts

Entregue:

### Prompt 1 — [Título]

```text
[PROMPT COMPLETO E AUTOSSUFICIENTE]
```

### Prompt 2 — [Título]

```text
[PROMPT COMPLETO E AUTOSSUFICIENTE]
```

E assim sucessivamente.

## 9. Critério final de conclusão

Crie um último prompt de validação geral que revise o resultado completo após todas as implementações, procurando:

- implementações incompletas;
    
- bugs;
    
- regressões;
    
- inconsistências;
    
- código morto;
    
- problemas de arquitetura;
    
- falhas de UX;
    
- falhas de segurança;
    
- testes insuficientes;
    
- divergências entre o objetivo original e o resultado final.
    

Esse último prompt também deverá operar em loop:

**Auditoria → Identificação de problema → Correção → Reteste → Nova auditoria**

até que não sejam encontrados problemas materiais.

---

# PRINCÍPIO CENTRAL

Não quero que você simplesmente transforme minhas ideias em tarefas.

Quero que você primeiro descubra **o que realmente deveria ser feito**.

Depois quero que transforme apenas as conclusões que sobreviveram à investigação em **um fluxo de implementação eficiente, ordenado, verificável e resistente a erros**.

Em resumo:

**Hipóteses → Testes → Refutação/Ajuste → Validação → Consolidação → Priorização → Fluxo de prompts → Implementação em loop → Validação final.**