## 1º Criação do padrão pixelado
- Após adicionar o **tipo (texto)**, crie uma **nova composição** com um **sólido contendo o efeito Ruído Fractal**.
- Configure o **tipo** do fractal como **"Simples"** e a **falha** como **"Bloquear"** — isso fará com que o padrão fique naturalmente pixelado.
- Ajuste a **complexidade para 2** e escale o fractal de forma que os pixels fiquem **retangulares** (largos e estreitos).
- Ative o **"Ciclo de Evolução"** para gerar uma animação contínua.
## 2º Criação da segunda textura
- **Duplique** a composição do ruído fractal.
- Altere a **distribuição aleatória (random seed)** e aplique **deslocamento** na nova camada.
- Aplique essa camada de deslocamento **sobre a camada original**, exagerando o deslocamento **horizontal** para criar uma distorção visível.
- Adicione uma **Curva em S invertida** para realçar os tons de cinza e aumentar o contraste visual do ruído.
## 3º Combinação com o tipo
- Em uma nova composição, **importe o texto (tipo)** e as **duas composições de textura** criadas.
- Aplique no tipo o efeito `Distorção > Deslocamento`.
	- No **primeiro efeito de deslocamento**, selecione como camada de referência a **primeira textura**, ative a opção **"Usar bordas"** e ajuste o **deslocamento vertical**.
	- **Duplique** o efeito de deslocamento, zere o deslocamento vertical, selecione como referência a **segunda textura** e ajuste o **deslocamento horizontal**.
## 4º Composição final e acabamento
- Crie uma **nova composição** e importe novamente:
- As **duas texturas animadas**
	- O **tipo com efeitos de deslocamento**
	- Aplique uma das **texturas em sobreposição** e a camada do tipo com o modo de mesclagem em **"Diferença"**.
- Adicione uma **camada de ajuste** com o efeito `Desfoque Direcional`:
	- Direção em **90°**
	- Modo de mesclagem em **"Luz Dura"**
- Adicione outra **camada de ajuste** com o efeito `Estilização > Espalhamento` e defina a **opacidade para 20%**.
## 5º Realce do tipo com brilho e contraste
- Por cima de tudo, adicione o **tipo original (raiz)** com o modo de mesclagem em **"Exclusão"**.
- Em uma nova **camada de ajuste**, aplique `Brilho e Contraste`, definindo o **contraste para 100**.
- **Duplique o tipo raiz**, mude a mesclagem para **"Multiplicação Negativa"** e ajuste a **opacidade para 5%**.
- Finalize adicionando um **novo "Brilho e Contraste"** acima das texturas, com **brilho em 40%**, para gerar mais movimento e energia visual ao fundo.