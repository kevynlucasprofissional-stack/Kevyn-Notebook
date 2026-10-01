---
Modificado:
  - segunda-feira 117 27/04/2026
  - domingo 116 26/04/2026
Criado: domingo 116 26/04/2026
---
Investi logo, investi o mais cedo possível,

Vai começar a investir em ação? Calcule o risco médio e o retorno esperado médio e faça um gráfico tipo esse:

![[Pasted image 20260426085840.png]]

Saiba mais em: [Google Search](https://www.google.com/search?sca_esv=71797cf33852cfd3&rlz=1C1GCEA_enBR1205BR1205&sxsrf=ANbL-n4nXZd62TSZFHpQHEffnT1YaeAqmA:1777204583243&udm=2&fbs=ADc_l-acAb_3MMOAUx0zmbUpgBqRiigBgL2I_pgQa-94zvB054Dys3s2x_Qm_GJcU2DlSXgtwykOhjc8tZDD70ApjQy2F_7G9F-2oFDI3kA5ZHm8DWcH1qQX1hoG2dDc1piP455MeZNwhf7fasNTLlWKk8qxulqUqLEuihNF5L2F84TD-NgOBlvqIdrNdvvB_CCq5ynEGEKyo-iOzsq_-fUDrerYiyS8dg&q=Gr%C3%A1fico+de+retorno+x+risco&sa=X&ved=2ahUKEwi0nIL_uouUAxVxrJUCHURDEsQQtKgLegQIFBAB&biw=1536&bih=730&dpr=1.25#sv=CAMSVhoyKhBlLUJ0RlZXdU5rem5WX21NMg5CdEZWV3VOa3puVl9tTToOdm5YTjE4WFFMY1NhdE0gBCocCgZtb3NhaWMSEGUtQnRGVld1Tmt6blZfbU0YADABGAcgjJj3pwdKCBABGAEgASgB)

Depois faça a diversificação de carteira para minimizar o risco. Por causa da mágica da diversificação de risco, quando diversificamos a carteira com ações de retornos e riscos diversos, o retorno será a média de todas as ações mas o risco vai ficar abaixo da média.

Sim — **a ideia geral está correta**, mas a frase precisa de dois ajustes importantes.

A forma mais precisa seria:

> Quando diversificamos uma carteira com ativos que não se movem perfeitamente juntos, o retorno esperado da carteira é a média ponderada dos retornos esperados dos ativos; já o risco da carteira pode ficar abaixo da média ponderada dos riscos individuais.

Essa é a base da **Teoria Moderna do Portfólio**, criada por **Harry Markowitz** no artigo _Portfolio Selection_, de 1952. Markowitz ganhou o Nobel de Economia em 1990 por desenvolver a teoria de escolha de portfólio. ([JSTOR](https://www.jstor.org/stable/2975974?utm_source=chatgpt.com "Portfolio Selection"))

## 1. O retorno é média

Se você monta uma carteira com várias ações, o retorno esperado é uma média ponderada:

E(R_p)=\sum_{i=1}^{n} w_iE(R_i)

Ou seja:

- se você coloca 50% em uma ação e 50% em outra, o retorno esperado é a média simples;
    
- se coloca 70% em uma e 30% em outra, é uma média ponderada.
    

Exemplo:

|Ativo|Peso|Retorno esperado|
|---|--:|--:|
|Ação A|50%|10%|
|Ação B|50%|20%|

Retorno esperado da carteira:

**15% ao ano**

Aqui não tem “mágica”: retorno é soma ponderada.

## 2. O risco não é média

O ponto poderoso da diversificação está no risco.

O risco da carteira não depende só do risco de cada ação isolada. Ele depende também de **como elas se comportam entre si**.

A fórmula para duas ações é:

\sigma_p^2=w_A^2\sigma_A^2+w_B^2\sigma_B^2+2w_Aw_B\sigma_A\sigma_B\rho_{AB}

Onde:

- (\sigma_p^2) = variância da carteira;
    
- (\sigma_A) e (\sigma_B) = risco individual de cada ação;
    
- (w_A) e (w_B) = peso de cada ação;
    
- (\rho_{AB}) = correlação entre as duas ações.
    

O segredo está nesse último termo: **correlação**.

## 3. O que a correlação faz

A correlação mede se os ativos sobem e caem juntos.

|Correlação|Interpretação|Efeito na diversificação|
|---|---|---|
|+1|sobem e caem perfeitamente juntos|não reduz risco|
|0|movimentos independentes|reduz risco|
|-1|movem-se em direções opostas|pode reduzir muito o risco|

Então a frase “o risco fica abaixo da média” só é verdadeira quando os ativos **não têm correlação perfeita positiva**.

Exemplo simples:

Duas ações:

- Ação A: risco de 20%;
    
- Ação B: risco de 20%;
    
- peso: 50% em cada.
    

Se a correlação for **+1**, o risco da carteira será:

**20%**

Ou seja, igual à média dos riscos. Não houve ganho de diversificação.

Se a correlação for **0**, o risco cai para aproximadamente:

**14,1%**

Mesmo com as duas ações tendo risco individual de 20%, a carteira ficou menos arriscada.

Se a correlação for **-1**, teoricamente o risco poderia cair até:

**0%**

Isso aconteceria se uma ação compensasse perfeitamente a oscilação da outra.

## 4. Então por que isso acontece?

Porque o risco de uma ação tem duas partes:

### Risco diversificável

É o risco específico de uma empresa ou setor.

Exemplos:

- má gestão;
    
- queda nas vendas;
    
- problema jurídico;
    
- perda de mercado;
    
- crise em um setor específico.
    

Esse risco pode ser reduzido com diversificação.

### Risco não diversificável

É o risco do mercado como um todo.

Exemplos:

- juros;
    
- inflação;
    
- recessão;
    
- crise política;
    
- pandemia;
    
- choque global.
    

Esse risco não desaparece apenas comprando mais ações, porque afeta várias empresas ao mesmo tempo.

Por isso, diversificar reduz bastante o risco específico, mas não elimina totalmente o risco da carteira.

## 5. A prova matemática em português simples

Imagine que cada ação tem uma oscilação própria.

Quando você mistura ativos diferentes, algumas oscilações se compensam:

- uma ação cai enquanto outra sobe;
    
- uma cai muito enquanto outra cai pouco;
    
- uma reage bem a juros altos enquanto outra sofre;
    
- uma depende do dólar enquanto outra depende do mercado interno.
    

Como essas variações não são perfeitamente iguais, parte do “barulho” individual é cancelado dentro da carteira.

Matematicamente, isso aparece na fórmula da variância. O retorno soma de forma direta; o risco, não. O risco depende da **covariância** entre os ativos. Esse foi o grande salto da Teoria Moderna do Portfólio: analisar não apenas “qual ativo é bom isoladamente”, mas **como cada ativo contribui para o risco do conjunto**. ([ResearchGate](https://www.researchgate.net/publication/228051028_Portfolio_Selection?utm_source=chatgpt.com "(PDF) Portfolio Selection"))

## 6. A versão mais correta da sua frase

Eu escreveria assim:

> Pela Teoria Moderna do Portfólio, o retorno esperado de uma carteira é a média ponderada dos retornos esperados dos ativos. Já o risco da carteira pode ficar abaixo da média ponderada dos riscos individuais quando os ativos não são perfeitamente correlacionados. Isso acontece porque parte das oscilações específicas de cada ativo se compensa dentro da carteira.

Ou, ainda mais simples:

> Diversificação não aumenta retorno por mágica. Ela melhora a relação risco-retorno porque permite combinar ativos que não oscilam exatamente do mesmo jeito. O retorno vira média ponderada; o risco pode cair mais do que a média.

# Distribuição normal, linha de markowitz e linha segura de mercado
![[Pasted image 20260426091416.png]]
A imagem é praticamente **o mapa visual da teoria que explica a “mágica” da diversificação**.

Ela mostra a **Teoria Moderna do Portfólio**, do Markowitz: como combinar ativos para buscar o melhor retorno possível para cada nível de risco.

## 1. O eixo X é o risco

Na horizontal está:

**Risco = desvio-padrão dos retornos**

Ou seja: quanto mais para a direita, mais a carteira oscila.

## 2. O eixo Y é o retorno esperado

Na vertical está:

**Retorno esperado**

Quanto mais para cima, maior o retorno esperado.

Então o investidor quer, em tese:

> ficar o mais para cima possível, com o menor deslocamento possível para a direita.

Ou seja: **mais retorno com menos risco**.

## 3. A curva azul é a fronteira eficiente de Markowitz

A curva azul representa as carteiras “boas” possíveis.

Ela mostra combinações de ativos em que, para cada nível de risco, você tem o **maior retorno esperado possível**.

Isso tem tudo a ver com o que falamos antes:

> quando você mistura ativos que não se movem exatamente juntos, o risco total da carteira pode cair sem que o retorno caia na mesma proporção.

É por isso que a curva fica “dobrada”. Ela mostra que algumas combinações de ativos entregam uma relação risco-retorno melhor do que os ativos isolados.

## 4. A parte vermelha é ineficiente

A parte vermelha representa combinações ruins.

Por quê?

Porque existe outra carteira na parte azul que entrega:

- o mesmo risco com maior retorno; ou
    
- o mesmo retorno com menor risco.
    

Então ninguém racional escolheria uma carteira na parte vermelha se pudesse escolher uma equivalente na fronteira eficiente.

## 5. O ponto da esquerda é a taxa livre de risco

A estrela roxa à esquerda representa a **taxa livre de risco**.

É o retorno de um investimento considerado “sem risco” dentro do modelo, como títulos públicos de curto prazo em economias estáveis.

Ela tem risco próximo de zero, por isso fica no canto esquerdo.

## 6. A linha verde é a Linha de Mercado de Capitais

A linha verde sai da taxa livre de risco e encosta na fronteira eficiente no ponto **T**.

Esse ponto **T** é o chamado **portfólio de mercado** ou **carteira tangente**.

Ele é importante porque, dentro da teoria, seria a melhor carteira de ativos arriscados em termos de relação entre retorno e risco.

A partir daí, o investidor pode fazer duas coisas:

- investir parte na taxa livre de risco e parte no portfólio de mercado;
    
- ou tomar risco adicional para aumentar o retorno esperado.
    

A linha verde mostra justamente essa combinação entre:

> ativo livre de risco + carteira eficiente de ativos arriscados.

## 7. Onde entra a diversificação?

Entra na formação da fronteira eficiente.

A diversificação permite criar carteiras que não são apenas uma “média simples” dos riscos individuais.

O retorno da carteira é uma média ponderada:

[  
E(R_p)=\sum w_iE(R_i)  
]

Mas o risco depende também da correlação entre os ativos:

[  
\sigma_p^2=w_A^2\sigma_A^2+w_B^2\sigma_B^2+2w_Aw_B\sigma_A\sigma_B\rho_{AB}  
]

O termo importante é esse:

[  
\rho_{AB}  
]

Ele representa a **correlação**.

Se os ativos não sobem e caem juntos perfeitamente, parte do risco se cancela. É isso que gera a curvatura da fronteira eficiente.

## 8. E a “distribuição normal”?

A distribuição normal entra como uma suposição comum da teoria.

A ideia é que os retornos dos ativos podem ser analisados por duas medidas principais:

- **média**: retorno esperado;
    
- **desvio-padrão**: risco.
    

Se os retornos seguem aproximadamente uma distribuição normal, então média e desvio-padrão resumem bem o comportamento do investimento.

Por isso o gráfico usa exatamente essas duas dimensões:

- retorno esperado;
    
- risco medido pelo desvio-padrão.
    

## 9. Resumindo em uma frase

A imagem mostra que a diversificação permite montar carteiras mais eficientes: o retorno esperado continua sendo uma média ponderada dos ativos, mas o risco pode cair abaixo da média dos riscos individuais porque os ativos não se movimentam perfeitamente juntos.

Ou seja: ela é a representação visual da conversa anterior. A “mágica” da diversificação é justamente o que cria a fronteira eficiente de Markowitz.

# Frases interessantes e links

"Ninguém quer ficar rico devagar, e eu nunca vi ninguém quebrar por estar ganhando pouquinho." - Warren Buffet

Selfmade Man é o super homem de Nietzsche, o homem que se superou, o homem que veio de baixo, cresceu e fez uma fortuna.

[Mapa de Calor de Ações](https://br.tradingview.com/heatmap/stock/#%7B%22dataSource%22%3A%22SPX500%22%2C%22blockColor%22%3A%22change%22%2C%22blockSize%22%3A%22Value.Traded%7C1M%22%2C%22grouping%22%3A%22sector%22%7D)

[GitHub - feremabraz/bloomberg-terminal: Bloomberg-like terminal with AI. It uses Redis with AlphaVantage data and local simulations to avoid hitting the API too much.](https://github.com/feremabraz/bloomberg-terminal)

# Idéia de solução
E se pudéssemos comprar ações e operar na bolsa de valores através de uma UI GPT-like ou WhatsApp Like?

# Como medir o valor de qualquer empresa, desde o início
Primeiro tira os ativos e os passivos (Circulantes e a longo prazo), depois calcula um monte de coisas.

Ou você pode simplesmente somar dívida + equity, o equity você pode descobrir simplesmente pesquisando no google "Market caps [nome da empresa]"
