## 1º Configuração Inicial do Tipo
- Importe o tipo (texto) para uma nova composição.
- Aplique o efeito **Quick Field Blur** com raio 3.
- Duplique essa camada do tipo e:
	- Reduza a opacidade para **40%**.
    - Aumente o raio do blur.
- Repita esse processo mais **2 ou 3 vezes**, sempre com opacidade em 40% e raio do desfoque gradualmente maior.
## 2º Realce de Brancos
- Crie uma **camada de ajuste**.
- Aplique **Correção de Tom (Tone Correction)** para intensificar os brancos e trazer nitidez às áreas claras.
## 3º Aplicação do Ruído Fractal
- Copie o **Ruído Fractal** da composição do **Gradiente RGB**, especificamente aquele que está abaixo do **Luma** (tons de cinza).
- Cole essa camada de ruído na composição atual e ajuste:
	- Nova **distribuição aleatória**.
    - **Dimensionamento** no **máximo possível**.
    - **Contraste** para **150**.
    - Modo de mesclagem: **Exclusão (Exclusion)**.
## 4º Curva de Contraste
- Adicione uma **camada de ajuste** por cima.
- Aplique o efeito **Curves** com uma curva em “S” bem acentuada, aumentando o contraste e a profundidade visual.
## 5º Criação do Mapa de Deslocamento
- Em uma nova composição, importe o **mapa do tipo**.
- Aplique o efeito **Deslocamento (Displacement Map)** e ajuste os valores até encontrar uma forma visual interessante.
- Ative a opção **"Repeat Edge Pixels"** para evitar bordas vazias.
	- Obs: O ideal é que a composição contenha material além das bordas da tela para evitar vazios nos extremos da imagem.
## 6º Integração com o Gradiente RGB
- Importe a **composição do Gradiente RGB** acima do mapa do tipo.
- Aplique o **Deslocamento** no **gradiente RGB**, usando como referência a **camada do tipo**.
	- Em “Camada de Displacement”, selecione: **"Efeitos e Máscaras"**.
    - Ajuste os valores para que o deslocamento do gradiente **acompanhe** a distorção aplicada ao tipo.
## 7º Harmonização Final
- Para reduzir a intensidade cromática e gerar uma composição mais coerente, aplique o efeito **Transform** (acima do deslocamento) na camada do Gradiente RGB.
- Use esse transform para **escalonar** o gradiente e reduzir a variação de cores visível na tela.