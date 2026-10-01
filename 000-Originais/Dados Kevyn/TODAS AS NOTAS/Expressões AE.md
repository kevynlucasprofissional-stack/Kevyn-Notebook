#flashcards #infomativo
## [[JS + Expressões AE = Eficiência máxima]]
## [[Expressões interagem com efeitos]]
## [[Separando expressões]]
## [[Inserindo expressões]]
## [[Ativando e Desativando Expressões]]
## **[[Loop simples em formas de máscara e outras propriedades não numéricas (Curvas, por exemplo)]]**
## **[[Variáveis]]**
## **[[Time]]**
## **[[Math.round()]]**
## **[[LoopOut()]]**
## **[[LoopIn()]]**
## **[[Wiggle(Frequência,Amplitude)]]**
## **[[SeedRandom()]]**
## **[[Pendulum]]**
## **[[Bounce]]**
## **[[Variáveis de Loop]]**
## Flashcards

A expressão **Pendulum** deve ser aplicada de forma que o último keyframe seja {{linear}}, pois é nesse keyframe que a expressão será ativada.
<!--SR:!2025-05-30,17,269-->

A expressão {{Pendulum}} controla os parâmetros de {{Amplitude}}, {{Frequência}} e {{Decaimento}}.
<!--SR:!2025-05-31,18,269!2025-05-17,13,249!2025-05-28,15,250!2025-05-29,16,269-->

A expressão {{SeedRandom()}} define um valor para os {{movimentos aleatórios}}.
<!--SR:!2025-05-29,16,269!2025-05-30,17,269-->

A função {{Math.round()}} faz com que um valor matemático fique {{arredondado, sem casas decimais}}.
<!--SR:!2025-05-31,18,269!2025-05-29,16,269-->

A variável de loop {{("Continue")}} faz com que a animação {{continue linearmente após o último keyframe}}. Só funciona com keyframes lineares.
<!--SR:!2025-06-09,27,270!2025-05-29,16,269-->

A variável de loop {{("Offset")}} faz com que a animação {{continue após o último keyframe, levando em consideração a posição no último keyframe}}. Sendo ideal para animações que exigem movimentos contínuos e lineares, que avançam no espaço.
<!--SR:!2025-05-29,16,269!2025-05-30,17,269-->

A variável de loop {{("Pingpong")}} faz a animação {{se inverter ao chegar ao último keyframe, indo até o primeiro e se invertendo novamente}}.
<!--SR:!2025-05-31,18,269!2025-05-29,16,269-->

A variável de loop {{("Cycle")}} faz com que a animação {{repita em ciclo, voltando ao frame inicial após o último frame}}.
<!--SR:!2025-05-31,18,269!2025-06-10,28,270-->

Ao arrastar o chicote do menu de expressões até um efeito do Effect Control, a expressão irá {{interagir com o efeito}}.
<!--SR:!2025-05-16,12,249-->

Como manter a escala do Wiggle uniforme?;;Usar a expressão w=wiggle(4,100); [w[0], w[0]]
<!--SR:!2025-05-22,9,229-->

Na expressão {{Bounce}}, o parâmetro {{Energia (e)}} controla {{quanto o modelo irá quicar}} e {{quanto tempo levará para voltar à inércia}}.
<!--SR:!2025-05-20,16,249!2025-05-15,11,249!2025-05-31,18,269!2025-05-15,11,229-->

Na expressão {{Wiggle(Frequência, Amplitude)}}, **Frequência** se refere a {{quantas vezes por segundo o parâmetro se movimenta}} e **Amplitude** se refere ao {{nível ou potência do movimento}}.
<!--SR:!2025-05-30,17,269!2025-06-13,31,270!2025-05-31,18,269-->

No menu de efeitos, há alguns efeitos que podem te ajudar a controlar melhor as expressões. Para acessar facilmente, clique com o botão direito e siga para {{"Effects > Expression Controls"}}.
<!--SR:!2025-05-16,12,249-->

O ideal para tirar o melhor proveito de expressões é aprender a {{programar em JavaScript}}.
<!--SR:!2025-05-30,17,269-->

O que a expressão **Pendulum** faz e quais parâmetros ela controla?
?
Cria uma oscilação que decai até a inércia no final da animação. Controla os parâmetros:
- **Amplitude:** Quanto ela irá oscilar.
- **Frequência:** Quantas vezes por segundo irá oscilar.
- **Decaimento:** Velocidade de decaimento até a inércia.
<!--SR:!2025-05-16,3,209-->

O que a função **Math.round()** faz?;;Faz com que um valor matemático fique arredondado, sem casas decimais.
<!--SR:!2025-05-30,17,269-->

O que acontece ao arrastar o chicote do menu de expressões até um efeito no "Effect Control"?;;A expressão interage com o efeito.
<!--SR:!2025-06-07,25,270-->

O que faz a combinação de teclas "Alt + (Click no relógio de animação)" no After Effects?;;Abre o menu de expressões.
<!--SR:!2025-06-14,32,270-->

O que faz a expressão **LoopIn("Pingpong")**?;;A animação se inverte ao chegar ao último keyframe, indo até o keyframe inicial e se invertendo novamente. E por ser LoopIn, a animação irá ser iniciada desde o início da camada.
<!--SR:!2025-05-31,18,269-->

O que faz a expressão **LoopIn()** no After Effects?;;A animação inicia antes de chegar ao primeiro KeyFrame e se repete até o último frame.
<!--SR:!2025-05-31,18,269-->

O que faz a expressão **LoopOut("Cycle")**?;; Repete a animação em ciclo, voltando ao keyframe inicial após o último keyframe. E por ser LoopOut, apenas irá iniciar o ciclo após o último keyframe animado manualmente.
<!--SR:!2025-06-11,29,270-->

O que faz a expressão **LoopOut()** no After Effects?;;Repete em loop a animação após o último Keyframe.
<!--SR:!2025-05-30,17,269-->

O que faz a expressão **SeedRandom()**?;;Define um valor para os movimentos aleatórios, padronizando os movimentos de acordo com um número. Esse número pode ser usado para tornar idênticos os movimentos de Wiggle em dois modelos separados.
<!--SR:!2025-05-30,17,269-->

O que faz a variável de loop **("Continue")**?;;Faz com que a animação de um modelo continue após o último keyframe na mesma direção e velocidade (só funciona com keyframes lineares).
<!--SR:!2025-05-29,16,269-->

O que faz a variável de loop **("Offset")**?;;Faz com que a animação continue após o último keyframe, mas leva em consideração a posição no qual o modelo está no último frame. Ideal para animações com movimento que avançam no espaço.
<!--SR:!2025-05-30,17,269-->

Para manter a escala do Wiggle uniforme, a expressão é {{w=wiggle(4,100); [w[0], w[0]]}}
<!--SR:!2025-05-23,10,249-->

Quais são os parâmetros da expressão **Bounce** e o que cada um faz?
?
- **Energia (e):** Quanto maior, mais o modelo irá quicar e mais tempo levará para voltar à inércia.
- **g:** Gravidade.
- **nMax:** Número máximo de quicadas.
<!--SR:!2025-05-14,1,189-->

Quais são os parâmetros da expressão **Wiggle()** e o que cada um significa?
?
- **Frequência:** Quantas vezes por segundo o parâmetro irá se movimentar.
- **Amplitude:** O nível, ou seja, a potência no qual o parâmetro irá se movimentar.
<!--SR:!2025-05-31,18,269-->

{{LoopIn()}} faz com que a animação {{inicie no primeiro frame e se repita em loop até a chegada do último frame}}.
<!--SR:!2025-05-29,16,269!2025-05-30,17,269-->

{{LoopOut()}} faz com que a animação {{repita após o último keyframe}}.
<!--SR:!2025-05-29,16,269!2025-06-10,28,270-->

{{Alt}} + (Click no relógio de animação): {{Abre o menu de expressões}}.
<!--SR:!2025-05-29,25,270!2025-05-21,17,269-->

Geralmente, para a seedRandom() funcionar corretamente, é necessário {{que ela esteja na primeira linha}}.
<!--SR:!2025-05-14,1,207-->

A seedRandom() deve ter dois parâmetros separados por uma vírgula, o primeiro é {{a semente}}, que é representado por um número, a segunda é o {{estado da expressão}}, que para ser definido como habilitado deve ser {{True}}.
<!--SR:!2025-05-20,7,267!2025-05-20,7,266!2025-05-20,7,267-->