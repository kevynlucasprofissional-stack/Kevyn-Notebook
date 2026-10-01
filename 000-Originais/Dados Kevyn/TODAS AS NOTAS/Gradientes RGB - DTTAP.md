## 1º Configuração inicial dos padrões fractais
- Crie uma **nova composição** e adicione um **sólido com o efeito Ruído Fractal**.
- **Reduza a complexidade** e o **foco (ou "Detalhe")** do fractal para suavizar o padrão.
- Ative a **evolução cíclica** para gerar uma animação contínua.
- **Duplique essa camada duas vezes**, mudando a **distribuição aleatória** em cada duplicata. Agora você terá **três camadas com padrões diferentes** de ruído fractal.
## 2º Separação dos canais RGB
- Crie uma **camada de ajuste** e adicione o efeito `Canais > Definir Canais (Set Channels)`.
- Para cada canal (R, G e B), conecte um dos três padrões criados:
	- Configure o **canal de origem** correspondente a cada camada de ruído.
	- Ajuste os **canais de destino** para montar a imagem RGB com base nos padrões distintos.
## 3º Criação de máscaras dinâmicas com padrões adicionais
- **Duplique novamente** o ruído fractal, altere a **distribuição aleatória** e mova esta camada para o topo da pilha.
- Repita este processo mais uma vez, ficando agora com **duas camadas adicionais** de padrões no topo.
- Na **camada imediatamente inferior**, ajuste o **"Fosco" (Track Matte)** para **"Luma Mask"**, usando a camada acima como base luminosa para criar uma máscara dinâmica de revelação.
## 4º Ajuste de contraste e escala do padrão
- Adicione uma **camada de ajuste** com o efeito `Curvas (Curves)` e configure uma **curva quase horizontal** para criar um contraste elevado e dramático nos padrões.
- Se necessário, adicione uma **nova camada de ajuste** com o efeito `Transform` para **escalonar todo o padrão** globalmente — isso é mais eficiente do que ajustar escala camada por camada.