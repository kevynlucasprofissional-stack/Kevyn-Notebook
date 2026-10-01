---
Modificado:
  - domingo 144 24/05/2026
Criado: domingo 144 24/05/2026
---
## Como criei o GPT de BPMN Automático?

1. Peguei uma demonstração do código, expliquei meu objetivo para o ChatGPT, ativei o pensamento estendido e a busca na web, e pedi para ele pesquisar também as melhores práticas de formatação BPMN 2.0 em XML.

2. Depois disso, anexei um exemplo da estrutura XML que eu precisava e solicitei que, com base nas informações encontradas e no modelo anexado, ele criasse um manual ensinando como gerar um arquivo BPMN 2.0 em XML válido, capaz de ser lido pelo site demo.bpmn.io. Com isso, ele criou a primeira versão do manual.

Nessa etapa 1 e 2 eu usei o seguinte prompt:

```txt
Estuda esse arquivo e pesquisa na web sobre as melhores práticas para criar diagramas em .bpmn, que fique 100% de acordo com as regras e que seja 100% fácil de ser lido pelo site https://demo.bpmn.io/

Estuda o arquivo e entenda a formatação, a sintaxe, a linguagem.

Me retorna um playbook, um manual de como criar um fluxograma de processo de acordo com as melhores práticas de BPMN e em uma formatação .bpmn funcional.
```

O resultado foi esse: [ChatGPT - Playbook BPMN 2.0](https://chatgpt.com/share/6a12fbf1-36c4-83e9-8ea7-474e369416e8)

Esse foi o resultado do fluxograma BPMN gerado pela primeira versão do manual:
![[{D9010A0B-741A-4125-8EF5-CC8FEB3CAE4D}.png]]

3. Porém, essa versão ainda apresentava alguns problemas. O principal deles era que os nós não eram coloridos automaticamente. No padrão BPMN, é comum que o nó inicial seja verde, os nós de atenção ou de divisão de fluxo sejam amarelos, as etapas principais do processo sejam azuis e os nós de encerramento do fluxo sejam vermelhos.

4. Por sorte, descobri que, na estrutura XML utilizada pelo demo.bpmn.io, as cores dos blocos já eram hardcoded na própria formatação BPMN 2.0. Foi isso que permitiu criar uma versão 2.0 do manual, que passou a colorir automaticamente os nós de acordo com o papel de cada um dentro do processo.

5. Depois disso, eu queria que a organização visual ficasse mais parecida com a organização feita pelo professor. Então, pedi um modelo de formatação feito por ele e solicitei que o ChatGPT analisasse a lógica utilizada nessa estrutura. A partir dessa análise, pedi que fossem criadas regras replicáveis para que o playbook conseguisse reproduzir automaticamente o mesmo padrão organizacional.

6. Com todos esses dados — o arquivo do professor, a análise sobre as cores hardcoded e o guia de significado das cores dentro do fluxo — o ChatGPT, utilizando o modelo Pro, pensamento estendido e busca na web, conseguiu criar a segunda versão do playbook.

Nas etapas de 3 a 6 eu usei o seguinte prompt:

```txt
Estou em uma aula sobre estruturação de processos em bpmn e estamos utilizando o demo.bpmn.io para gerar fluxograma de processos. O professor me pediu para criar uma maneira automática de criar o fluxograma no site do demo.bpmn.io, para isso estamos criando um playbook que ensine uma IA a estruturar corretamente esse tipo de arquivo de acordo com as especificações.
O arquivo resultado V1 é o resultado de um .bpmn gerado a partir do atual playbook.
O arquivo modelo de organização é o gabarito final do professor, este é o modelo máximo e o resultado final de fluxo de processo gerados pelo playbook devem se aproximar ao máximo deste modelo.

Preciso atualizar o playbook de gerar .bpmn, este mesmo que anexei em .md
O primeiro passo é analisar o arquivo de modelo de organização e observar como ele é diferente em relação ao resultado V1, já adianto que uma das diferenças são as cores, ou seja, o playbook final deve conseguir colorir os quadradados de fluxo: Verde para inicio do fluxo, azul para etapa de fluxo, amarelo para ponto de atenção/decisão e vermelho para fim de fluxo. Além do mais estude a organização, a disposição dos blocos de fluxo que o professor fez manualmente, observe como ele organizou e trate isso como um modelo a ser seguido.

Eu coloquei também uma print de como ficou visualmente a organização do professor contida em "Modelo de organização", aprenda com ele, retire regras de replicação, framework e worflow e coloque na V2 do Playbook. Não se esqueça de analisar como os blocos são coloridos hardcoded no .bpmn e coloque instruções no V2 do playbook para colorir os blocos de acordo com sua função no fluxo.
```

O resultado foi esse: [ChatGPT - Atualização Playbook BPMN V2](https://chatgpt.com/share/6a12fe68-d5b4-83e9-905e-06e8aa4cabb1)

Esse foi o resultado do fluxograma BPMN gerado pela segunda versão do manual:
![[{1F8921AE-4217-4DCB-9AA1-2A609BD8CDD4}.png]]

Depois disso, eu quero falar um pouco mais sobre o meu trabalho.

Na área de tecnologia, meu trabalho já é bastante abrangente. Eu desenvolvo:
- Sites
- Landing pages
- E-commerces
- Soluções digitais utilizando programação.

Também quero apresentar:
- K tools New
- BioVision
- Agora
- Atom.