---
Modificado:
  - quinta-feira 197 16/07/2026
  - quarta-feira 196 15/07/2026
  - domingo 144 24/05/2026
Criado: sábado 143 23/05/2026
---
# Playbook V2 — Como gerar arquivos `.bpmn` funcionais, legíveis e próximos ao gabarito do professor no `demo.bpmn.io`

> **Objetivo da V2:** além de gerar um BPMN 2.0 XML funcional, a IA deve gerar um arquivo visualmente organizado, com piscina, raias, cores hardcoded, sequência lógica e disposição espacial próxima ao modelo manual do professor.

---

## 0. O que mudou da V1 para a V2

A V1 já tratava corretamente a base técnica: `definitions`, `process`, eventos, tarefas, gateways, `sequenceFlow`, `BPMNShape`, `BPMNEdge`, `Bounds` e `waypoint`.

A V2 acrescenta uma camada obrigatória de **organização visual**, porque o gabarito do professor não é apenas BPMN funcional: ele é um BPMN didático, com leitura rápida, cores semânticas e disposição compacta.

### Diferenças observadas entre o Resultado V1 e o Modelo de Organização

| Aspecto | Resultado V1 | Modelo do professor | Regra V2 |
|---|---|---|---|
| Cores | Sem cores nos elementos | Elementos coloridos por função | Aplicar cores hardcoded em todo `BPMNShape` |
| Início | Evento inicial simples | Evento inicial verde com ícone de mensagem | Quando o início vier de solicitação externa, usar `messageEventDefinition` |
| Primeira ação do cliente | O fluxo sai do início direto para a locadora | Cliente primeiro solicita aluguel | Não pular a primeira tarefa do ator que inicia o processo |
| Tamanho das tarefas | Geralmente `150x80` | `100x80` | Usar tarefas compactas de `100x80` |
| Tamanho do processo | Piscina muito larga | Piscina mais compacta, com mais uso vertical | Preferir empilhar etapas relacionadas em vez de alongar tudo horizontalmente |
| Raias | Cliente / Atendente / Funcionário da garagem | Cliente / Locadora / Garagista | Usar nomes de papéis macro quando o gabarito privilegiar clareza institucional |
| Exceções | Alguns fins negativos ficam em raias de cliente | Fins negativos ficam próximos ao ponto de decisão na locadora | Posicionar exceções perto do gateway que as gera |
| Decisões | Algumas decisões do cliente em raia Cliente | Decisões operacionais na Locadora | Gateway fica na raia de quem registra/controla a decisão no processo |
| Voucher | V1 incorpora tudo em uma tarefa | Modelo separa `Registra locação`, `Emite voucher` e objeto `voucher` | Representar documento relevante como `dataObjectReference` quando aparecer como entrega física/digital |
| Fluxo final | Sequência horizontal longa | Entrega ao cliente no topo e retirada desce para Garagista | Usar troca vertical de raia quando muda o responsável real |

---

## 1. Regra máxima

Um `.bpmn` bom para o `demo.bpmn.io` precisa satisfazer **três camadas ao mesmo tempo**:

1. **Camada semântica BPMN:** o processo precisa estar correto.
2. **Camada XML/BPMNDI:** o arquivo precisa ser importável e renderizável.
3. **Camada visual didática:** o desenho precisa parecer organizado, colorido e fácil de explicar em aula.

A V1 resolvia principalmente as camadas 1 e 2. A V2 deve resolver também a camada 3.

---

## 2. Estrutura técnica obrigatória

Use sempre esta estrutura de raiz, com prefixo `bpmn:` explícito e com os namespaces de cor incluídos:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<bpmn:definitions
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xmlns:bpmn="http://www.omg.org/spec/BPMN/20100524/MODEL"
  xmlns:bpmndi="http://www.omg.org/spec/BPMN/20100524/DI"
  xmlns:dc="http://www.omg.org/spec/DD/20100524/DC"
  xmlns:di="http://www.omg.org/spec/DD/20100524/DI"
  xmlns:bioc="http://bpmn.io/schema/bpmn/biocolor/1.0"
  xmlns:color="http://www.omg.org/spec/BPMN/non-normative/color/1.0"
  id="Definitions_NomeDoProcesso"
  targetNamespace="http://bpmn.io/schema/bpmn"
  exporter="bpmn-js (https://demo.bpmn.io)"
  exporterVersion="18.13.2">
```

### Por que usar `bioc` e `color`

O BPMNDI padrão guarda posições, tamanhos e caminhos, mas não cobre todos os aspectos visuais, como cor. Para o `demo.bpmn.io`, a forma mais segura de persistir as cores no XML é aplicar atributos diretamente no `bpmndi:BPMNShape` usando:

```xml
bioc:stroke="#..."
bioc:fill="#..."
color:background-color="#..."
color:border-color="#..."
```

Use **os dois padrões juntos** porque o modelo do professor usa ambos e porque isso aumenta a chance de o arquivo abrir colorido no `demo.bpmn.io` e continuar preservando as cores depois de editado/exportado.

---

## 3. Paleta obrigatória da V2

A IA deve colorir os elementos de acordo com sua função no fluxo.

| Função | Elemento BPMN | Cor de fundo | Cor de borda | Uso |
|---|---|---:|---:|---|
| Início do fluxo | `startEvent` | `#c8e6c9` | `#205022` | Verde |
| Etapa do fluxo | `task` | `#bbdefb` | `#0d4372` | Azul |
| Ponto de atenção/decisão | `exclusiveGateway` | `#ffe0b2` | `#6b3c00` | Amarelo |
| Fim de fluxo | `endEvent` | `#ffcdd2` | `#831311` | Vermelho |
| Documento/artefato relevante | `dataObjectReference` | `#ffcdd2` ou `#fff3e0` | `#831311` ou `#6b3c00` | Preferencialmente vermelho se for entrega/saída importante |

### 3.1. Shape de início verde

```xml
<bpmndi:BPMNShape
  id="StartEvent_SolicitacaoRecebida_di"
  bpmnElement="StartEvent_SolicitacaoRecebida"
  bioc:stroke="#205022"
  bioc:fill="#c8e6c9"
  color:background-color="#c8e6c9"
  color:border-color="#205022">
  <dc:Bounds x="282" y="152" width="36" height="36" />
</bpmndi:BPMNShape>
```

### 3.2. Shape de tarefa azul

```xml
<bpmndi:BPMNShape
  id="Task_SolicitarDocumentacao_di"
  bpmnElement="Task_SolicitarDocumentacao"
  bioc:stroke="#0d4372"
  bioc:fill="#bbdefb"
  color:background-color="#bbdefb"
  color:border-color="#0d4372">
  <dc:Bounds x="650" y="260" width="100" height="80" />
</bpmndi:BPMNShape>
```

### 3.3. Shape de gateway amarelo

```xml
<bpmndi:BPMNShape
  id="Gateway_ModeloDisponivel_di"
  bpmnElement="Gateway_ModeloDisponivel"
  isMarkerVisible="true"
  bioc:stroke="#6b3c00"
  bioc:fill="#ffe0b2"
  color:background-color="#ffe0b2"
  color:border-color="#6b3c00">
  <dc:Bounds x="525" y="275" width="50" height="50" />
</bpmndi:BPMNShape>
```

### 3.4. Shape de fim vermelho

```xml
<bpmndi:BPMNShape
  id="EndEvent_AtendimentoEncerrado_di"
  bpmnElement="EndEvent_AtendimentoEncerrado"
  bioc:stroke="#831311"
  bioc:fill="#ffcdd2"
  color:background-color="#ffcdd2"
  color:border-color="#831311">
  <dc:Bounds x="532" y="552" width="36" height="36" />
</bpmndi:BPMNShape>
```

---

## 4. Estrutura com piscina e raias

Para processos com mais de um responsável, use sempre:

```xml
<bpmn:collaboration id="Collaboration_AlugarVeiculo">
  <bpmn:participant
    id="Participant_AlugarVeiculo"
    name="Alugar Veículo"
    processRef="Process_AlugarVeiculo" />
</bpmn:collaboration>

<bpmn:process id="Process_AlugarVeiculo" isExecutable="false">
  <bpmn:laneSet id="LaneSet_AlugarVeiculo">
    ...
  </bpmn:laneSet>
  ...
</bpmn:process>
```

Quando existe `collaboration`, o `BPMNPlane` deve apontar para a colaboração:

```xml
<bpmndi:BPMNPlane id="BPMNPlane_1" bpmnElement="Collaboration_AlugarVeiculo">
```

### 4.1. Padrão visual do professor

O modelo do professor usa uma piscina horizontal com três raias:

```text
Cliente
Locadora
Garagista
```

A piscina fica mais compacta na largura e mais generosa na altura. O layout aproximado observado foi:

| Elemento visual | x | y | width | height |
|---|---:|---:|---:|---:|
| Piscina | 200 | 120 | 1700 | 700 |
| Raia Cliente | 230 | 120 | 1670 | 120 |
| Raia Locadora | 230 | 240 | 1670 | 420 |
| Raia Garagista | 230 | 660 | 1670 | 160 |

### 4.2. Regra geral para dimensionar raias

Use este algoritmo:

```text
pool_x = 200
pool_y = 120
lane_label_width = 30
lane_x = pool_x + lane_label_width

Para cada raia:
  se tiver poucas tarefas: height = 120 a 160
  se for a raia principal do processo: height = 300 a 440
  se for raia final/operacional curta: height = 140 a 180

pool_width:
  calcular pelo último elemento + margem direita
  evitar ultrapassar 1900px em processos médios
```

### 4.3. Regra de escolha dos nomes das raias

Prefira nomes que representam o papel no processo, não necessariamente a pessoa específica.

Use:

```text
Cliente
Locadora
Garagista
Financeiro
Atendimento
Gestor
Fornecedor
```

Evite, exceto quando o processo exigir:

```text
Pessoa
Funcionário 1
Fulano
Atendente 2
```

No processo de aluguel, o modelo do professor usa **Locadora** em vez de **Atendente** porque o papel representa a organização executando o atendimento.

---

## 5. Tamanhos padrão dos blocos

Para aproximar do gabarito do professor, use estes tamanhos:

| Elemento | Width | Height |
|---|---:|---:|
| `startEvent` | 36 | 36 |
| `endEvent` | 36 | 36 |
| `task` | 100 | 80 |
| `exclusiveGateway` | 50 | 50 |
| `dataObjectReference` | 36 | 50 |

A V1 usava tarefas maiores, como `150x80`. A V2 deve preferir `100x80`, que deixa o processo mais próximo do modelo manual.

---

## 6. Grade visual recomendada

### 6.1. Eixos Y por raia

Com o padrão do professor:

```text
Raia Cliente:
  centro visual principal: y = 170 ou 180
  tarefa: y = 130 ou 140
  evento: y = 152

Raia Locadora:
  linha principal: y = 300
  tarefa principal: y = 260
  gateway principal: y = 275
  exceções inferiores: y = 350, 455, 552
  pilha vertical de tarefas: y = 270, 390, 510

Raia Garagista:
  linha principal: y = 710
  tarefa: y = 670
  evento final: y = 692
```

### 6.2. Eixos X por coluna

Use colunas compactas e progressivas. O modelo observado segue aproximadamente esta lógica:

```text
x = 282   início
x = 370   primeira tarefa
x = 525   gateway
x = 650   tarefa seguinte
x = 800   verificação
x = 955   gateway
x = 1070  tarefa
x = 1265  gateway
x = 1390  pilha de tarefas
x = 1550  cliente recebe
x = 1690  cliente retira / garagista registra
x = 1832  fim
```

### 6.3. Regra de espaçamento

```text
Evento → tarefa: 50 a 90px
Tarefa → gateway: 50 a 70px
Gateway → tarefa: 60 a 100px
Tarefa → tarefa horizontal: 100 a 160px
Tarefa → tarefa vertical na mesma coluna: 40px de espaço entre blocos
Gateway → fim negativo: 40 a 80px, preferencialmente próximo
```

---

## 7. Regras de organização extraídas do gabarito

### 7.1. Fluxo principal deve ir da esquerda para a direita

O caminho positivo deve avançar para a direita sempre que possível.

Exemplo:

```text
Início → Solicita aluguel → Verifica disponibilidade → Modelo disponível? → Solicita documentação
```

### 7.2. Exceções devem ficar próximas ao gateway

Não leve exceções para o fim do diagrama. No modelo do professor:

```text
modelo disponível?
  não → Oferece outros modelos → cliente aceitou algum?
      não → encerra atendimento
```

O fim negativo fica logo abaixo do gateway correspondente, não no final do processo.

### 7.3. Use verticalidade para economizar largura

Quando três ou mais etapas pertencem à mesma fase e ao mesmo responsável, empilhe na mesma coluna.

No gabarito:

```text
Registra despesa no cartão
↓
Registra a locação
↓
Emite o voucher
```

Todos aparecem no mesmo `x`, com setas verticais.

Regra:

```text
Se as tarefas são sequenciais, curtas e do mesmo ator, empilhar verticalmente.
Se há troca de ator ou avanço de fase, deslocar para a direita.
```

### 7.4. Troca de raia deve ser visualmente explícita

Quando muda o responsável, a seta pode subir ou descer verticalmente.

Exemplos:

```text
Locadora solicita documentação → Cliente entrega documentos
Cliente entrega documentos → Locadora verifica documentação
Cliente retira veículo → Garagista registra saída
```

A troca de raia precisa ficar clara no desenho, mesmo que o `sequenceFlow` continue dentro do mesmo processo/pool.

### 7.5. Gateways ficam na raia de controle do processo

Mesmo quando a decisão envolve o cliente, coloque o gateway na raia de quem registra/controla o processo, quando este for o padrão didático do gabarito.

Exemplo:

```text
cliente aceitou algum?
```

No modelo do professor, esse gateway fica na raia **Locadora**, porque a locadora está conduzindo o atendimento e registrando a continuidade ou encerramento.

### 7.6. Não transforme todo texto em uma tarefa única

Se uma frase do processo contém duas ações importantes, separe em duas tarefas.

Exemplo ruim:

```text
Registrar locação e imprimir voucher
```

Exemplo preferido na V2:

```text
Registra a locação
Emite o voucher
```

Se o voucher é uma entrega relevante, adicione também:

```xml
<bpmn:dataObjectReference id="DataObjectReference_Voucher" name="voucher" dataObjectRef="DataObject_Voucher" />
<bpmn:dataObject id="DataObject_Voucher" />
```

### 7.7. O início pode ser evento de mensagem

Se o processo começa quando alguém solicita, envia, comparece, protocola, chama, pede, registra ou comunica algo, considere usar `messageEventDefinition` no `startEvent`.

```xml
<bpmn:startEvent id="StartEvent_SolicitacaoRecebida" name="solicitação recebida">
  <bpmn:outgoing>Flow_Start_Solicitar</bpmn:outgoing>
  <bpmn:messageEventDefinition id="MessageEventDefinition_Start" />
</bpmn:startEvent>
```

Isso gera o ícone de envelope dentro do evento inicial, como no modelo do professor.

---

## 8. Como transformar texto em elementos BPMN

### 8.1. Classifique cada frase do processo

Para cada frase recebida, a IA deve classificar:

```text
É gatilho inicial?
É ação de alguém?
É decisão?
É exceção?
É documento/artefato?
É encerramento?
É troca de responsável?
```

### 8.2. Mapeamento obrigatório

| Texto do processo | Elemento BPMN |
|---|---|
| “O processo inicia quando...” | `startEvent` |
| “Cliente solicita...” | `task` na raia Cliente |
| “Atendente verifica...” | `task` na raia Locadora/Atendimento |
| “Caso...” / “Se...” | `exclusiveGateway` |
| “Caso contrário...” | saída nomeada do gateway |
| “Encerra atendimento” | `endEvent` vermelho próximo ao desvio |
| “Imprime/entrega voucher/documento” | `task` + opcional `dataObjectReference` |
| “Funcionário registra...” | `task` na raia do funcionário/papel |
| “Processo finaliza...” | `endEvent` vermelho |

### 8.3. Nomeação dos elementos

Regra prática:

```text
Evento = estado/acontecimento
Tarefa = verbo + objeto
Gateway = pergunta
Fluxo de saída = resposta
```

Exemplos:

```text
StartEvent: solicitação de aluguel recebida
Task: Solicita Aluguel de Veículo
Task: Verifica disponibilidade do modelo
Gateway: modelo disponível?
Flow: sim
Flow: não
EndEvent: encerra atendimento
```

---

## 9. Workflow da IA para gerar o `.bpmn`

### Etapa 1 — Interpretar o processo

Extraia:

```text
Nome do processo
Atores/raias
Evento inicial
Caminho principal
Decisões
Caminhos negativos
Documentos/artefatos
Fim positivo
Fins negativos
```

### Etapa 2 — Escolher a estrutura visual

Decida:

```text
Precisa de pool? Sim, se houver mais de um ator.
Precisa de lane? Sim, se houver mais de um papel dentro do processo.
BPMNPlane aponta para process ou collaboration? Collaboration, se houver participant.
```

### Etapa 3 — Criar a lista canônica de elementos

Antes de escrever XML, monte uma tabela interna:

| Ordem | Tipo | ID | Nome | Raia | Cor | x | y | width | height |
|---:|---|---|---|---|---|---:|---:|---:|---:|

A IA só deve escrever o XML final depois de ter esta tabela mentalmente consistente.

### Etapa 4 — Criar `incoming` e `outgoing`

Todo elemento deve ter:

```text
startEvent: outgoing
task intermediária: incoming + outgoing
gateway: incoming + dois ou mais outgoing
endEvent: incoming
```

### Etapa 5 — Criar `sequenceFlow`

Todo `sequenceFlow` deve ter:

```xml
<bpmn:sequenceFlow
  id="Flow_Origem_Destino"
  name="sim"
  sourceRef="Gateway_Origem"
  targetRef="Task_Destino" />
```

Use `name` especialmente nos fluxos que saem de gateways.

### Etapa 6 — Criar BPMNDI

Para cada elemento visível, criar `BPMNShape`.

Para cada `sequenceFlow`, criar `BPMNEdge`.

Para cada artefato/documento, criar `BPMNShape` e associação visual, se aplicável.

### Etapa 7 — Aplicar cores

Nenhum shape de evento, tarefa, gateway ou fim deve ficar sem cor.

Checklist:

```text
startEvent tem verde?
task tem azul?
exclusiveGateway tem amarelo?
endEvent tem vermelho?
dataObjectReference tem cor?
```

### Etapa 8 — Validar layout

Antes de entregar, revisar:

```text
O fluxo principal avança para a direita?
As exceções estão próximas dos gateways?
As raias estão proporcionais?
Há cruzamento desnecessário de linhas?
As tarefas estão compactas?
As decisões têm saída sim/não?
Todos os caminhos chegam a um endEvent?
```

---

## 10. Padrão de layout recomendado para o processo “Alugar Veículo”

Use este padrão como referência para processos semelhantes:

| Ordem | Elemento | Raia | Posição sugerida |
|---:|---|---|---|
| 1 | Start: solicitação de aluguel/checkin | Cliente | x=282, y=152 |
| 2 | Solicita Aluguel de Veículo | Cliente | x=370, y=130 |
| 3 | Verifica disponibilidade do modelo | Locadora | x=370, y=260 |
| 4 | modelo disponível? | Locadora | x=525, y=275 |
| 5 | Oferece outros modelos | Locadora | x=500, y=350 |
| 6 | cliente aceitou algum? | Locadora | x=525, y=455 |
| 7 | encerra atendimento | Locadora | x=532, y=552 |
| 8 | Solicita documentação | Locadora | x=650, y=260 |
| 9 | Entrega documentos | Cliente | x=650, y=130 |
| 10 | Verifica documentação | Locadora | x=800, y=260 |
| 11 | cliente habilitado? | Locadora | x=955, y=275 |
| 12 | encerra atendimento | Locadora | x=962, y=372 |
| 13 | Solicita cartão para caução | Locadora | x=1070, y=260 |
| 14 | possui cartão? | Locadora | x=1265, y=275 |
| 15 | Entrega cartão | Cliente | x=1240, y=140 |
| 16 | encerra atendimento | Locadora | x=1272, y=362 |
| 17 | Registra despesa no cartão | Locadora | x=1390, y=270 |
| 18 | Registra a locação | Locadora | x=1390, y=390 |
| 19 | Emite o voucher | Locadora | x=1390, y=510 |
| 20 | DataObject: voucher | Locadora | x=1282, y=525 |
| 21 | Recebe o voucher | Cliente | x=1550, y=140 |
| 22 | Retira o veículo | Cliente | x=1690, y=140 |
| 23 | Registra a saída do veículo | Garagista | x=1690, y=670 |
| 24 | Locação finalizada | Garagista | x=1832, y=692 |

---

## 11. Padrão de waypoints

### 11.1. Fluxo horizontal simples

Use quando origem e destino estão na mesma linha:

```xml
<bpmndi:BPMNEdge id="Flow_1_di" bpmnElement="Flow_1">
  <di:waypoint x="470" y="300" />
  <di:waypoint x="525" y="300" />
</bpmndi:BPMNEdge>
```

### 11.2. Fluxo vertical simples

Use quando origem e destino estão na mesma coluna:

```xml
<bpmndi:BPMNEdge id="Flow_Registrar_Emitir_di" bpmnElement="Flow_Registrar_Emitir">
  <di:waypoint x="1440" y="470" />
  <di:waypoint x="1440" y="510" />
</bpmndi:BPMNEdge>
```

### 11.3. Fluxo em L

Use quando há troca de raia ou deslocamento vertical:

```xml
<bpmndi:BPMNEdge id="Flow_EntregaDocs_VerificaDocs_di" bpmnElement="Flow_EntregaDocs_VerificaDocs">
  <di:waypoint x="750" y="170" />
  <di:waypoint x="850" y="170" />
  <di:waypoint x="850" y="260" />
</bpmndi:BPMNEdge>
```

### 11.4. Fluxo com subida para o cliente

```xml
<bpmndi:BPMNEdge id="Flow_PossuiCartao_EntregaCartao_di" bpmnElement="Flow_PossuiCartao_EntregaCartao">
  <di:waypoint x="1290" y="275" />
  <di:waypoint x="1290" y="220" />
</bpmndi:BPMNEdge>
```

### 11.5. Fluxo longo com troca de raia

```xml
<bpmndi:BPMNEdge id="Flow_EmiteVoucher_RecebeVoucher_di" bpmnElement="Flow_EmiteVoucher_RecebeVoucher">
  <di:waypoint x="1490" y="550" />
  <di:waypoint x="1520" y="550" />
  <di:waypoint x="1520" y="180" />
  <di:waypoint x="1550" y="180" />
</bpmndi:BPMNEdge>
```

---

## 12. Como representar documentos e voucher

Se uma etapa gera um documento importante, use `dataObjectReference`.

Exemplo semântico:

```xml
<bpmn:task id="Task_EmiteVoucher" name="Emite o voucher">
  <bpmn:incoming>Flow_RegistraLocacao_EmiteVoucher</bpmn:incoming>
  <bpmn:outgoing>Flow_EmiteVoucher_RecebeVoucher</bpmn:outgoing>
  <bpmn:dataOutputAssociation id="DataOutputAssociation_Voucher">
    <bpmn:targetRef>DataObjectReference_Voucher</bpmn:targetRef>
  </bpmn:dataOutputAssociation>
</bpmn:task>

<bpmn:dataObjectReference
  id="DataObjectReference_Voucher"
  name="voucher"
  dataObjectRef="DataObject_Voucher" />

<bpmn:dataObject id="DataObject_Voucher" />
```

Exemplo visual:

```xml
<bpmndi:BPMNShape
  id="DataObjectReference_Voucher_di"
  bpmnElement="DataObjectReference_Voucher"
  bioc:stroke="#831311"
  bioc:fill="#ffcdd2"
  color:background-color="#ffcdd2"
  color:border-color="#831311">
  <dc:Bounds x="1282" y="525" width="36" height="50" />
</bpmndi:BPMNShape>

<bpmndi:BPMNEdge id="DataOutputAssociation_Voucher_di" bpmnElement="DataOutputAssociation_Voucher">
  <di:waypoint x="1390" y="550" />
  <di:waypoint x="1318" y="550" />
</bpmndi:BPMNEdge>
```

---

## 13. Checklist final da V2

Antes de entregar qualquer `.bpmn`, a IA deve confirmar:

### XML

- [ ] Começa com `<?xml version="1.0" encoding="UTF-8"?>`.
- [ ] Usa `bpmn:definitions`.
- [ ] Inclui namespaces `bpmn`, `bpmndi`, `dc`, `di`, `xsi`.
- [ ] Inclui namespaces de cor `bioc` e `color`.
- [ ] IDs são únicos.
- [ ] IDs não têm acento, espaço ou caractere especial.
- [ ] Não há `&` solto no XML.

### Semântica BPMN

- [ ] Existe `collaboration` quando há pool/participant.
- [ ] Existe `participant` com `processRef`.
- [ ] Existe `process`.
- [ ] Existe `laneSet` quando há raias.
- [ ] Cada `flowNodeRef` aponta para um elemento real.
- [ ] Existe pelo menos um `startEvent`.
- [ ] Existe pelo menos um `endEvent`.
- [ ] Todo gateway divergente tem pelo menos duas saídas.
- [ ] Saídas de gateway têm `name`, como `sim` e `não`.
- [ ] Todos os caminhos terminam em evento final.

### Visual

- [ ] Piscina e raias têm `BPMNShape`.
- [ ] Todo evento/tarefa/gateway/documento tem `BPMNShape`.
- [ ] Todo fluxo tem `BPMNEdge`.
- [ ] Todo edge tem pelo menos dois `waypoint`.
- [ ] Tarefas usam `100x80`, salvo exceção justificada.
- [ ] Gateways usam `50x50`.
- [ ] Eventos usam `36x36`.
- [ ] Start está verde.
- [ ] Tasks estão azuis.
- [ ] Gateways estão amarelos.
- [ ] End events estão vermelhos.
- [ ] Fluxo principal vai da esquerda para a direita.
- [ ] Exceções estão próximas dos gateways.
- [ ] Não há cruzamentos desnecessários.
- [ ] O desenho cabe de forma compacta no canvas inicial do `demo.bpmn.io`.

### Importação

- [ ] Abrir no `demo.bpmn.io`.
- [ ] Verificar se não aparece erro de importação.
- [ ] Verificar se não aparece alerta de importação.
- [ ] Conferir visualmente as cores.
- [ ] Conferir se as setas encostam nos elementos corretos.
- [ ] Conferir se as raias estão na ordem correta.

---

## 14. Prompt operacional para uma IA gerar o arquivo `.bpmn`

Use este prompt quando quiser que uma IA transforme um processo textual em BPMN:

```text
Você é um gerador técnico de arquivos BPMN 2.0 XML para o demo.bpmn.io.

Sua tarefa é transformar o processo fornecido em um arquivo `.bpmn` funcional, validável e visualmente organizado conforme o padrão V2 abaixo.

Regras obrigatórias:

1. Gere XML BPMN 2.0 real, não um desenho genérico.
2. Use `bpmn:definitions` com namespaces:
   - bpmn
   - bpmndi
   - dc
   - di
   - xsi
   - bioc
   - color
3. Se houver mais de um ator, crie `collaboration`, `participant`, `process`, `laneSet` e lanes horizontais.
4. Se houver `collaboration`, faça o `BPMNPlane` apontar para a collaboration.
5. Use sequenceFlow apenas dentro do mesmo processo/pool.
6. Classifique os elementos:
   - início = `startEvent`
   - etapa = `task`
   - decisão = `exclusiveGateway`
   - encerramento = `endEvent`
   - documento relevante = `dataObjectReference`
7. Nomeie:
   - evento como estado/acontecimento;
   - tarefa como verbo + objeto;
   - gateway como pergunta;
   - saída de gateway como resposta: `sim` / `não`.
8. Crie `incoming` e `outgoing` em todos os elementos.
9. Crie `BPMNShape` para todos os elementos visíveis.
10. Crie `BPMNEdge` para todos os `sequenceFlow`.
11. Use cores hardcoded nos shapes:
   - startEvent: `bioc:fill="#c8e6c9"` e `bioc:stroke="#205022"`;
   - task: `bioc:fill="#bbdefb"` e `bioc:stroke="#0d4372"`;
   - exclusiveGateway: `bioc:fill="#ffe0b2"` e `bioc:stroke="#6b3c00"`;
   - endEvent: `bioc:fill="#ffcdd2"` e `bioc:stroke="#831311"`.
12. Repita as mesmas cores também em:
   - `color:background-color`
   - `color:border-color`
13. Use layout horizontal, da esquerda para a direita.
14. Use tarefas compactas de `100x80`.
15. Use gateways de `50x50`.
16. Use eventos de `36x36`.
17. Use exceções próximas dos gateways.
18. Use empilhamento vertical quando várias tarefas forem sequenciais e do mesmo responsável.
19. Use troca vertical de raia quando o responsável mudar.
20. Se o processo começar por solicitação externa, use `messageEventDefinition` dentro do startEvent.
21. Se houver voucher, comprovante, contrato, nota, autorização ou documento final, represente como `dataObjectReference` quando isso ajudar a leitura.
22. Antes de entregar, valide mentalmente:
   - todos os IDs existem;
   - todos os sourceRef/targetRef apontam para IDs reais;
   - todo fluxo aparece como incoming/outgoing;
   - todo caminho termina em endEvent;
   - todo shape tem cor;
   - todo edge tem waypoints.

Entregue apenas o conteúdo XML completo do arquivo `.bpmn`.
```

---

## 15. Mini-template de shape colorido

Sempre que gerar um shape, escolha o bloco correto:

### Start

```xml
bioc:stroke="#205022"
bioc:fill="#c8e6c9"
color:background-color="#c8e6c9"
color:border-color="#205022"
```

### Task

```xml
bioc:stroke="#0d4372"
bioc:fill="#bbdefb"
color:background-color="#bbdefb"
color:border-color="#0d4372"
```

### Gateway

```xml
isMarkerVisible="true"
bioc:stroke="#6b3c00"
bioc:fill="#ffe0b2"
color:background-color="#ffe0b2"
color:border-color="#6b3c00"
```

### End

```xml
bioc:stroke="#831311"
bioc:fill="#ffcdd2"
color:background-color="#ffcdd2"
color:border-color="#831311"
```

---

## 16. Nota sobre compatibilidade

As cores são uma extensão visual. O BPMN 2.0 continua válido como processo, mas a preservação das cores depende do suporte da ferramenta. Para o objetivo desta aula, que é abrir e editar no `demo.bpmn.io`, o uso combinado de `bioc:*` e `color:*` é adequado porque segue o padrão observado no arquivo exportado pelo próprio ambiente usado pelo professor.

---

## 17. Fontes técnicas consultadas

- OMG — BPMN 2.0 Specification: https://www.omg.org/spec/BPMN/2.0/
- bpmn.io — bpmn-js toolkit: https://bpmn.io/toolkit/bpmn-js/
- bpmn.io — Colors are Here: https://bpmn.io/blog/posts/2016-colors-bpmn-js
- bpmn-io GitHub — bpmn-js examples/colors: https://github.com/bpmn-io/bpmn-js-examples/blob/main/colors/README.md
- BPMN MIWG — BPMN Model Interchange: https://www.omgwiki.org/bpmn-miwg/lib/exe/fetch.php?media=20150611_submission.pdf

