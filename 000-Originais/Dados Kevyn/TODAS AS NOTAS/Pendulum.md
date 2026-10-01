Ela é uma oscilação que se decai até a inércia no final de uma animação.
Desta expressão é possível controlar 3 parâmetros.

>**Amplitude:** Quanto que ela irá oscilar.
>**Frequência:** Quantas vezes por segundo irá oscilar.
>**Decaimento:** Velocidade de decaimento até a inércia.

amp = .05;
freq = 3;
decay = 4.5;

n = 0;
if (numKeys > 0){
n = nearestKey(time).index;
if (key(n).time > time){
n--;
}}

if (n == 0){ t = 0;
}else{
t = time - key(n).time;
}

if (n > 0){
v = velocityAtTime(key(n).time - thisComp.frameDuration/10);
value + v*amp*Math.sin(freq*t*2*Math.PI)/Math.exp(decay*t);
}else{value}

**OBS: Esta expressão só é aplicada em Keyframes lineares.**