---
Modificado:
  - quarta-feira 196 15/07/2026
  - sexta-feira 191 10/07/2026
  - sábado 143 23/05/2026
Criado: sábado 143 23/05/2026
---
## 1. Entenda o que o bpmn.io espera

O site `demo.bpmn.io` usa **bpmn-js** para visualizar, criar e editar diagramas BPMN 2.0 no navegador. Ele importa arquivos BPMN 2.0 XML e mostra erros ou alertas quando o diagrama não pode ser renderizado corretamente. ([BPMN Editor](https://demo.bpmn.io/ "BPMN Editor | bpmn-js modeler Demo | demo.bpmn.io"))

A base técnica do bpmn-js é o **bpmn-moddle**, que lê e escreve documentos BPMN 2.0 XML com base no metamodelo BPMN. Na importação, o XML vira uma árvore de objetos; durante a modelagem, essa árvore é validada e depois exportada novamente como XML BPMN 2.0. ([bpmn.io](https://bpmn.io/toolkit/bpmn-js/walkthrough/ "bpmn-js walkthrough | Toolkits | bpmn.io"))

Em termos práticos: um `.bpmn` funcional não é apenas “um desenho em XML”. Ele precisa ser **BPMN 2.0 real**, com elementos semânticos válidos e uma camada BPMNDI para renderização visual.

---

## 2. Estrutura obrigatória de um `.bpmn`

Um arquivo BPMN bom para o demo.bpmn.io deve ter esta estrutura:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<definitions ...>
  <process id="Process_1" isExecutable="false">
    <!-- eventos, tarefas, gateways e fluxos -->
  </process>

  <bpmndi:BPMNDiagram id="BpmnDiagram_1">
    <bpmndi:BPMNPlane id="BpmnPlane_1" bpmnElement="Process_1">
      <!-- shapes e edges visuais -->
    </bpmndi:BPMNPlane>
  </bpmndi:BPMNDiagram>
</definitions>
```

A especificação oficial BPMN 2.0 da OMG fornece os documentos normativos e os schemas XML, incluindo `BPMN20.xsd`, `BPMNDI.xsd`, `DC.xsd` e `DI.xsd`. ([OMG](https://www.omg.org/spec/BPMN/2.0/ "About the Business Process Model And Notation Specification Version 2.0"))

A separação é essencial: o arquivo BPMN contém **semântica do processo** e **representação visual**. O BPMN Diagram Interchange, ou BPMNDI, armazena posições, dimensões e caminhos das setas, mas não todos os detalhes visuais possíveis, como cores, sombras, quebras de texto e estilos de linha.

---

## 3. Anatomia do XML BPMN

### 3.1. `definitions`

É o elemento raiz. Deve conter os namespaces corretos:

```xml
<definitions
  xmlns="http://www.omg.org/spec/BPMN/20100524/MODEL"
  xmlns:bpmndi="http://www.omg.org/spec/BPMN/20100524/DI"
  xmlns:omgdi="http://www.omg.org/spec/DD/20100524/DI"
  xmlns:omgdc="http://www.omg.org/spec/DD/20100524/DC"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  id="Definitions_1"
  targetNamespace="http://bpmn.io/schema/bpmn">
```

Boas práticas:

- Use sempre `UTF-8`.
    
- Use IDs únicos.
    
- Não use ID começando apenas com número.
    
- Evite espaços, acentos e caracteres especiais em IDs.
    
- Use nomes humanos apenas no atributo `name`.
    

---

### 3.2. `process`

Representa o processo principal.

```xml
<process id="Process_1" isExecutable="false">
```

Use `isExecutable="false"` quando o objetivo for documentação, fluxograma ou entendimento visual. Use `true` apenas quando o processo for preparado para execução em motor BPMN, como Camunda, Zeebe ou outro engine.

---

### 3.3. Eventos

Eventos representam estados ou acontecimentos.

```xml
<startEvent id="StartEvent_1" name="Solicitação recebida">
  <outgoing>Flow_1</outgoing>
</startEvent>
```

Boas práticas de nomeação: eventos devem representar um **estado alcançado** ou algo que aconteceu no negócio, enquanto tarefas devem dizer uma ação. A Camunda recomenda nomear eventos com objeto + verbo em estado, e atividades com verbo + objeto, sempre pela perspectiva de negócio. ([Camunda 8 Docs](https://docs.camunda.io/docs/components/best-practices/modeling/naming-bpmn-elements/ "Naming BPMN elements | Camunda 8 Docs"))

Bons nomes:

```text
Solicitação recebida
Pagamento aprovado
Pedido cancelado
Cadastro concluído
```

Evite:

```text
Início
Evento 1
Começar processo
```

---

### 3.4. Tarefas

Tarefas representam trabalho.

```xml
<task id="Task_AnalisarSolicitacao" name="Analisar solicitação">
  <incoming>Flow_1</incoming>
  <outgoing>Flow_2</outgoing>
</task>
```

Use verbo + objeto:

```text
Analisar solicitação
Enviar proposta
Validar documentos
Aprovar cadastro
Emitir nota fiscal
```

Evite nomes genéricos:

```text
Processar
Fazer análise
Resolver
Verificar
```

---

### 3.5. Gateways

Gateways representam decisões, paralelismos ou junções.

Exemplo de gateway exclusivo:

```xml
<exclusiveGateway id="Gateway_Aprovado" name="Solicitação aprovada?">
  <incoming>Flow_2</incoming>
  <outgoing>Flow_Sim</outgoing>
  <outgoing>Flow_Nao</outgoing>
</exclusiveGateway>
```

Boas práticas:

- Nomeie gateway como pergunta.
    
- Nomeie as saídas como respostas.
    
- Use `Sim` / `Não`, `Aprovado` / `Reprovado`, `Completo` / `Incompleto`.
    
- Em gateways exclusivos, saídas devem representar alternativas mutuamente excludentes.
    
- Em gateways paralelos, evite perguntas; ele representa “fazer tudo”, não “decidir”.
    

A convenção de nomear fluxos de saída de gateways exclusivos, inclusivos e complexos com os resultados/condições da decisão é uma prática recomendada de modelagem BPMN. ([Trisotech](https://www.trisotech.com/naming-conventions-for-bpmn-diagrams/?utm_source=chatgpt.com "Naming Conventions for BPMN Diagrams - Trisotech"))

---

### 3.6. Sequence flows

São as setas do processo.

```xml
<sequenceFlow id="Flow_Sim" name="Sim" sourceRef="Gateway_Aprovado" targetRef="Task_EmitirContrato" />
```

Regras essenciais:

- `sourceRef` deve apontar para um elemento existente.
    
- `targetRef` deve apontar para um elemento existente.
    
- O ID do fluxo deve aparecer como `<outgoing>` no elemento de origem.
    
- O ID do fluxo deve aparecer como `<incoming>` no elemento de destino.
    
- Fluxos que saem de decisões devem ter nome claro.
    

---

## 4. Camada visual: BPMNDI

Sem BPMNDI, o processo pode até ser semanticamente válido, mas o demo.bpmn.io pode não conseguir renderizar corretamente o layout.

### 4.1. Shape

Cada elemento visual precisa de um `BPMNShape`:

```xml
<bpmndi:BPMNShape id="Task_AnalisarSolicitacao_di" bpmnElement="Task_AnalisarSolicitacao">
  <omgdc:Bounds x="240" y="80" width="100" height="80" />
</bpmndi:BPMNShape>
```

Regras:

- `bpmnElement` deve apontar para o ID real do elemento.
    
- Tarefas geralmente usam `width="100"` e `height="80"`.
    
- Eventos geralmente usam `width="36"` e `height="36"`.
    
- Gateways geralmente usam `width="50"` e `height="50"`.
    
- Use alinhamento horizontal sempre que possível.
    

---

### 4.2. Edge

Cada `sequenceFlow` precisa de um `BPMNEdge`:

```xml
<bpmndi:BPMNEdge id="Flow_1_di" bpmnElement="Flow_1">
  <omgdi:waypoint x="188" y="120" />
  <omgdi:waypoint x="240" y="120" />
</bpmndi:BPMNEdge>
```

Regras:

- `bpmnElement` deve apontar para o ID do `sequenceFlow`.
    
- Cada edge deve ter pelo menos dois `waypoint`.
    
- Waypoints devem conectar visualmente origem e destino.
    
- Evite linhas cruzadas.
    
- Prefira fluxo da esquerda para a direita.
    

---

## 5. Modelo mínimo funcional

Este é um exemplo simples, completo e funcional para abrir no `demo.bpmn.io`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<definitions xmlns="http://www.omg.org/spec/BPMN/20100524/MODEL"
  xmlns:bpmndi="http://www.omg.org/spec/BPMN/20100524/DI"
  xmlns:omgdi="http://www.omg.org/spec/DD/20100524/DI"
  xmlns:omgdc="http://www.omg.org/spec/DD/20100524/DC"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  id="Definitions_1"
  targetNamespace="http://bpmn.io/schema/bpmn"
  exporter="bpmn-js"
  exporterVersion="18.13.2">

  <process id="Process_1" isExecutable="false">

    <startEvent id="StartEvent_1" name="Solicitação recebida">
      <outgoing>Flow_1</outgoing>
    </startEvent>

    <task id="Task_AnalisarSolicitacao" name="Analisar solicitação">
      <incoming>Flow_1</incoming>
      <outgoing>Flow_2</outgoing>
    </task>

    <exclusiveGateway id="Gateway_Aprovada" name="Solicitação aprovada?">
      <incoming>Flow_2</incoming>
      <outgoing>Flow_Sim</outgoing>
      <outgoing>Flow_Nao</outgoing>
    </exclusiveGateway>

    <task id="Task_EmitirContrato" name="Emitir contrato">
      <incoming>Flow_Sim</incoming>
      <outgoing>Flow_3</outgoing>
    </task>

    <task id="Task_ComunicarRecusa" name="Comunicar recusa">
      <incoming>Flow_Nao</incoming>
      <outgoing>Flow_4</outgoing>
    </task>

    <endEvent id="EndEvent_ContratoEmitido" name="Contrato emitido">
      <incoming>Flow_3</incoming>
    </endEvent>

    <endEvent id="EndEvent_RecusaComunicada" name="Recusa comunicada">
      <incoming>Flow_4</incoming>
    </endEvent>

    <sequenceFlow id="Flow_1" sourceRef="StartEvent_1" targetRef="Task_AnalisarSolicitacao" />
    <sequenceFlow id="Flow_2" sourceRef="Task_AnalisarSolicitacao" targetRef="Gateway_Aprovada" />
    <sequenceFlow id="Flow_Sim" name="Sim" sourceRef="Gateway_Aprovada" targetRef="Task_EmitirContrato" />
    <sequenceFlow id="Flow_Nao" name="Não" sourceRef="Gateway_Aprovada" targetRef="Task_ComunicarRecusa" />
    <sequenceFlow id="Flow_3" sourceRef="Task_EmitirContrato" targetRef="EndEvent_ContratoEmitido" />
    <sequenceFlow id="Flow_4" sourceRef="Task_ComunicarRecusa" targetRef="EndEvent_RecusaComunicada" />

  </process>

  <bpmndi:BPMNDiagram id="BpmnDiagram_1">
    <bpmndi:BPMNPlane id="BpmnPlane_1" bpmnElement="Process_1">

      <bpmndi:BPMNShape id="StartEvent_1_di" bpmnElement="StartEvent_1">
        <omgdc:Bounds x="150" y="120" width="36" height="36" />
      </bpmndi:BPMNShape>

      <bpmndi:BPMNShape id="Task_AnalisarSolicitacao_di" bpmnElement="Task_AnalisarSolicitacao">
        <omgdc:Bounds x="240" y="98" width="120" height="80" />
      </bpmndi:BPMNShape>

      <bpmndi:BPMNShape id="Gateway_Aprovada_di" bpmnElement="Gateway_Aprovada" isMarkerVisible="true">
        <omgdc:Bounds x="420" y="113" width="50" height="50" />
      </bpmndi:BPMNShape>

      <bpmndi:BPMNShape id="Task_EmitirContrato_di" bpmnElement="Task_EmitirContrato">
        <omgdc:Bounds x="540" y="60" width="120" height="80" />
      </bpmndi:BPMNShape>

      <bpmndi:BPMNShape id="Task_ComunicarRecusa_di" bpmnElement="Task_ComunicarRecusa">
        <omgdc:Bounds x="540" y="190" width="120" height="80" />
      </bpmndi:BPMNShape>

      <bpmndi:BPMNShape id="EndEvent_ContratoEmitido_di" bpmnElement="EndEvent_ContratoEmitido">
        <omgdc:Bounds x="730" y="82" width="36" height="36" />
      </bpmndi:BPMNShape>

      <bpmndi:BPMNShape id="EndEvent_RecusaComunicada_di" bpmnElement="EndEvent_RecusaComunicada">
        <omgdc:Bounds x="730" y="212" width="36" height="36" />
      </bpmndi:BPMNShape>

      <bpmndi:BPMNEdge id="Flow_1_di" bpmnElement="Flow_1">
        <omgdi:waypoint x="186" y="138" />
        <omgdi:waypoint x="240" y="138" />
      </bpmndi:BPMNEdge>

      <bpmndi:BPMNEdge id="Flow_2_di" bpmnElement="Flow_2">
        <omgdi:waypoint x="360" y="138" />
        <omgdi:waypoint x="420" y="138" />
      </bpmndi:BPMNEdge>

      <bpmndi:BPMNEdge id="Flow_Sim_di" bpmnElement="Flow_Sim">
        <omgdi:waypoint x="445" y="113" />
        <omgdi:waypoint x="445" y="100" />
        <omgdi:waypoint x="540" y="100" />
      </bpmndi:BPMNEdge>

      <bpmndi:BPMNEdge id="Flow_Nao_di" bpmnElement="Flow_Nao">
        <omgdi:waypoint x="445" y="163" />
        <omgdi:waypoint x="445" y="230" />
        <omgdi:waypoint x="540" y="230" />
      </bpmndi:BPMNEdge>

      <bpmndi:BPMNEdge id="Flow_3_di" bpmnElement="Flow_3">
        <omgdi:waypoint x="660" y="100" />
        <omgdi:waypoint x="730" y="100" />
      </bpmndi:BPMNEdge>

      <bpmndi:BPMNEdge id="Flow_4_di" bpmnElement="Flow_4">
        <omgdi:waypoint x="660" y="230" />
        <omgdi:waypoint x="730" y="230" />
      </bpmndi:BPMNEdge>

    </bpmndi:BPMNPlane>
  </bpmndi:BPMNDiagram>
</definitions>
```

---

## 6. Regras de ouro para criar um fluxograma BPMN legível

### 6.1. Comece pelo processo, não pelo desenho

Antes de escrever XML, defina:

```text
Nome do processo:
Objetivo:
Evento inicial:
Resultado final esperado:
Atores envolvidos:
Tarefas principais:
Decisões:
Exceções:
Fim positivo:
Fim negativo:
```

BPMN é uma notação padronizada para processos de negócio, com uma linguagem visual comum para stakeholders e precisão suficiente para tradução em componentes de processo. ([OMG](https://www.omg.org/spec/BPMN/2.0/ "About the Business Process Model And Notation Specification Version 2.0"))

---

### 6.2. Use poucos tipos de elementos no início

Para a maioria dos processos administrativos, comece com:

|Necessidade|Elemento BPMN|
|---|---|
|Início do processo|`startEvent`|
|Trabalho humano ou etapa genérica|`task`|
|Decisão|`exclusiveGateway`|
|Caminho simultâneo|`parallelGateway`|
|Fim do processo|`endEvent`|
|Ordem entre etapas|`sequenceFlow`|

Evite começar usando eventos avançados, subprocessos, mensagens, compensações ou erros se o processo ainda não está maduro. A referência de símbolos BPMN 2.0 mostra que a notação tem muitos elementos possíveis, mas nem todos são necessários para um processo simples e legível. ([Camunda](https://camunda.com/bpmn/reference/ "BPMN 2.0 Symbols - A complete guide with examples. | Camunda | Camunda"))

---

### 6.3. Nomeie pensando no leitor de negócio

Regra prática:

```text
Evento = estado
Tarefa = ação
Gateway = pergunta
Fluxo de saída = resposta
```

Exemplo:

```text
Evento: Pedido recebido
Tarefa: Conferir estoque
Gateway: Produto disponível?
Fluxos: Sim / Não
Fim: Pedido enviado
```

---

### 6.4. Mantenha o fluxo da esquerda para a direita

Layout recomendado:

```text
Início → Tarefa → Decisão → Caminhos → Fim
```

Evite:

- setas voltando sem necessidade;
    
- cruzamento de linhas;
    
- tarefas desalinhadas;
    
- excesso de elementos na vertical;
    
- nomes longos demais;
    
- gateways sem saída nomeada;
    
- processo sem evento final.
    

---

### 6.5. Não confunda fluxograma desenhado com BPMN real

Um erro comum é criar um desenho “parecido com BPMN” em ferramentas genéricas e tentar converter para `.bpmn`. O próprio fórum do bpmn.io alerta que arquivos de ferramentas de desenho, como draw.io, não são necessariamente BPMN 2.0 XML: podem conter apenas formas e conexões visuais, permitindo coisas impossíveis, confusas ou inválidas em BPMN real. ([bpmn.io Forum](https://forum.bpmn.io/t/converting-draw-io-flows-to-bpmn-io-flows-en-masse/14330 "Converting draw.io flows to bpmn.io flows en masse - Users - bpmn.io Forum"))

Para o `demo.bpmn.io`, o arquivo deve ser BPMN 2.0 XML, não apenas um XML de desenho.

---

## 7. Checklist técnico antes de importar no demo.bpmn.io

Use este checklist sempre:

### XML

- O arquivo começa com `<?xml version="1.0" encoding="UTF-8"?>`.
    
- O elemento raiz é `definitions`.
    
- Os namespaces BPMN, BPMNDI, DI e DC estão corretos.
    
- Não há caracteres especiais sem escape, como `&` solto.
    
- IDs são únicos.
    
- IDs não começam com número puro.
    
- Todas as tags abrem e fecham corretamente.
    

### Processo

- Existe pelo menos um `<process>`.
    
- Existe pelo menos um `startEvent`.
    
- Existe pelo menos um `endEvent`.
    
- Toda tarefa tem `incoming` e/ou `outgoing` coerentes.
    
- Todo gateway divergente tem mais de uma saída.
    
- Todo gateway de decisão tem saídas nomeadas.
    
- Todo `sequenceFlow` tem `sourceRef` e `targetRef`.
    
- Todo `sourceRef` e `targetRef` aponta para ID existente.
    

### BPMNDI

- Todo evento/tarefa/gateway visível tem `BPMNShape`.
    
- Todo `sequenceFlow` visível tem `BPMNEdge`.
    
- Todo `BPMNShape` tem `Bounds`.
    
- Todo `BPMNEdge` tem pelo menos dois `waypoint`.
    
- O `BPMNPlane` aponta para o processo ou colaboração correta.
    
- Os elementos não se sobrepõem visualmente.
    

### Validação

- Abrir no `demo.bpmn.io`.
    
- Verificar se não aparece “Import Error”.
    
- Verificar se não aparece “Import Warnings”.
    
- Validar contra o schema BPMN 2.0 quando possível. O fórum do bpmn.io recomenda que o primeiro quality gate seja a validação XSD contra o schema BPMN 2.0, porque XML estruturalmente válido não significa necessariamente BPMN válido. ([bpmn.io Forum](https://forum.bpmn.io/t/error-when-using-the-modeler/10938 "Error when using the modeler - General - bpmn.io Forum"))
    

---

## 8. Padrão de escrita recomendado

Use este padrão para IDs:

```text
Definitions_1
Process_1
StartEvent_SolicitacaoRecebida
Task_AnalisarSolicitacao
Gateway_SolicitacaoAprovada
Flow_AnalisarParaGateway
Flow_Sim
Flow_Nao
EndEvent_ProcessoConcluido
```

Use este padrão para nomes:

```text
Solicitação recebida
Analisar solicitação
Solicitação aprovada?
Emitir contrato
Comunicar recusa
Contrato emitido
Recusa comunicada
```

Evite:

```text
Task 1
Gateway 2
Processar coisa
Fazer etapa
Decisão
Fim
```

---

## 9. Diferença entre processo simples e processo com piscinas

Para processos internos simples, use apenas:

```xml
<process>
```

Para processos com empresas, departamentos ou atores externos trocando mensagens, use:

```xml
<collaboration>
  <participant id="Participant_Cliente" name="Cliente" processRef="Process_Cliente" />
  <participant id="Participant_Empresa" name="Empresa" processRef="Process_Empresa" />
  <messageFlow id="MessageFlow_1" sourceRef="..." targetRef="..." />
</collaboration>
```

Regra importante:

```text
sequenceFlow = fluxo dentro do mesmo processo/pool
messageFlow = comunicação entre pools diferentes
```

Não use `sequenceFlow` entre participantes diferentes.

---

## 10. Método prático para criar um `.bpmn` do zero

### Etapa 1 — Escreva o processo em texto

```text
1. Solicitação recebida.
2. Analisar solicitação.
3. Solicitação aprovada?
   - Sim: emitir contrato.
   - Não: comunicar recusa.
4. Encerrar processo.
```

### Etapa 2 — Transforme em elementos BPMN

```text
StartEvent_SolicitacaoRecebida
Task_AnalisarSolicitacao
Gateway_SolicitacaoAprovada
Task_EmitirContrato
Task_ComunicarRecusa
EndEvent_ContratoEmitido
EndEvent_RecusaComunicada
```

### Etapa 3 — Crie os `sequenceFlow`

```text
Start → Analisar
Analisar → Gateway
Gateway → Emitir contrato
Gateway → Comunicar recusa
Emitir contrato → Fim positivo
Comunicar recusa → Fim negativo
```

### Etapa 4 — Adicione `incoming` e `outgoing`

Cada elemento precisa “saber” quais fluxos entram e saem dele.

### Etapa 5 — Adicione BPMNDI

Crie:

```text
BPMNShape para cada evento, tarefa e gateway
BPMNEdge para cada sequenceFlow
Bounds para posição/tamanho
waypoints para as setas
```

### Etapa 6 — Teste no demo.bpmn.io

Abra o arquivo. Se renderizar sem erro, revise visualmente:

```text
Está legível?
As decisões estão claras?
As saídas do gateway estão nomeadas?
Há fim para todos os caminhos?
As linhas não cruzam?
```

---

## 11. Diagnóstico do arquivo enviado

O seu arquivo enviado está correto como **exemplo mínimo de exportação bpmn-js**, porque possui:

- `definitions` com namespaces corretos;
    
- `process`;
    
- `startEvent`;
    
- `task`;
    
- `exclusiveGateway`;
    
- `sequenceFlow`;
    
- `BPMNDiagram`;
    
- `BPMNPlane`;
    
- `BPMNShape`;
    
- `BPMNEdge`;
    
- `Bounds`;
    
- `waypoint`.
    

Mas, como processo completo, ele precisa melhorar:

|Ponto|Situação no arquivo|Ajuste recomendado|
|---|---|---|
|Evento inicial|Existe|Manter|
|Tarefa|Existe|Nomear com verbo + objeto|
|Gateway exclusivo|Existe|Adicionar saídas|
|Saídas do gateway|Não existem|Criar fluxos nomeados|
|Eventos finais|Não existem|Adicionar pelo menos um fim|
|Processo completo|Não|Fechar todos os caminhos|
|Legibilidade|Boa para exemplo mínimo|Melhorar nomes e caminhos|

Conclusão: use seu arquivo como **base de sintaxe**, mas não como modelo final de processo. Ele é um ponto de partida; para documentação profissional, precisa de caminhos completos, decisões fechadas e encerramentos claros.