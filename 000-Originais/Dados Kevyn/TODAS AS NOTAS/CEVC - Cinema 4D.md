A bolinha de cima é para visualização na Viewport, e a de baixo serve para definir se será ou não renderizado, e o da direita é o liga e desliga. Isto é na janela das "Camadas".

Tem como deixar um modelo no modo "X-Ray", no qual ele fica tipo semi-transparente.

É possível desfazer ações realizadas apenas no menu View.

Tem como bloquear os eixos para ele não se mover em alguma dimensão durante a movimentação livre.

Clicar em Enter alterna entre os modos de edição de arestas, faces e nós.

Nas propriedades das ferramentas de seleção, existe uma opção chamada "Visible Only", que quando ativado, significa que apenas o que está visível na Viewport será selecionado.

Quando uma face está selecionada, estará disponível ao clicar no botão direito do mouse a ferramenta "Extrude", que cria uma etapa de volume externo. Também estará disponível o "Extrude Inner", que cria uma extrusão interna. Ferramentas muitíssimo úteis.

Greyscalegorilla é um site de uma empresa que vende assets e plugins para o modelagem em 3D.

Existe no C4D a possibilidade de criar hierarquia entre os objetos. Para isto basta arrastar um objeto para cima de outro na janela de "Camadas". E aí o objeto arrastado será agora como que o filho do objeto que recebeu o objeto arrastado. Funciona bem parecido com o Parent & Link do After Effects.

[Elementos passivos] são aqueles que são estáticos e que não tem nenhum tipo de atividade ou movimento ao logo do tempo, toda transformação nestes objetos dependem do designer. Objetos paramétricos ou editáveis, enquanto não tem nenhuma tag de animação, são objetos passivos. Geralmente são representados pela cor azul.

[Elementos ativos] são aqueles que já tem por origem uma função de movimento e uma atividade que é realizada com o passar do tempo. Emitter, Pyro, Objetos com tags de animação ou simulação são exemplos de elementos ativos. Geralmente são representados pela ==cor verde (Para geradores que precisam ter um modelo como filha)== ou ==lilás (Para deformadores que precisam ser filhos de um modelo).==

Elemento passivos conseguem receber influências de elementos ativos.

É possível usar uma imagem como textura para um modelo. Basta criar um material, ir em "Texture" no menu "Color" e clicar em "Load Image".

No caso de se necessitar deformar uma spline com extrude, é necessário criar um nulo, jogar a spline extrudada como filha do nulo e jogar o deformador também como filha do nulo. Assim, as deformações personalizadas no deformador irão afetar a spline extrudada.

No caso de se necessitar deformar com Bend um modelo paramétrico ou editável que já tenha espessura (Que já é 3D), basta colocar o Bend como filho deste modelo.

Ao trabalhar com Splines, geralmente é mais interessante trabalhar usando uma viewport travado em alguma perspectiva (Topo, baixo, esquerda, direita, frente ou trás).

Nas novas versões do C4D, as ferramentas de "Caneta de Spline" foram para a barra  lateral esquerda, podem também ser encontradas na no botão direito do Mouse ou no menu "Spline" na barra superior.

É possível fechar um Spline pela janela de propriedades, basta clicar em "Close Spline".

É possível tornar um Spline em editável. Atalho C.

Para aplicar extrude em mais de uma spline ao mesmo tempo, usando um único extrude, basta colocar as duas splines como filhas do extrude e ativar "Hierarchical".

Lathe é um gerador bem interessante, ele cria a partir de uma spline e de um ponto central um modelo que é o resultado da spline duplicada em 360 graus. Ótimo para criar vasos e diveros outros tipos de modelo.

O Sweep precisa de um caminho para repetir uma spline, e uma spline que será repetida, assim ele alonga a spline acima por todo o caminho da spline abaixo.

Ao editar fontes em spline, você pode ganhar um enorme controle sobre todos os aspectos de um texto ao ativar nas propriedades do texto spline a caixa "Show 3D GUI", disponível em "Kerning".

É interessante, ao se trabalhar integrando o Illustrator com o C4D, que todos os elementos que serão importados do Ai para o C4D estejam necessariamente em vetores. Nem bitmaps e nem efeitos 3D nativos do Ai irão funcionar no C4D. 

Ao salvar Ai com o objetivo de importar para o C4D, [salve em Illustrator 8]. É o formato mais seguro para fazer a integração entre estes dois softwares, pois este formato não contém as compressões adicionais que os formatos mais recentes fazem. Salvar em Illustrator 8 irá ser integrado no C4D como vários splines. Pode ocorrer, ao salvar em illustrator 8, um erro bem comum, que é o de buracos serem salvos a parte de suas splines original, ou seja, se você extruda a letra A importada de um arquivo Ai 8, provavelmente o A estará sem o furo, e o furo será extrudado separado do A.
==Nota pessoal: Salvar o arquivo nas últimas versões do Illustrator garante uma maior integração entre o C4D e o Ai, visto que ao importar no formato mais recente, além de já vir colorido e com extrusão, o modelo continua sendo editável no Ai, sendo que qualquer modificação no arquivo Ai será atualizado no C4D com o clicar de um botão (Que é o de atualizar, nas propriedades da camada do Ai no C4D).

Clicando no botão direito é possível acessar a ferramenta "Close Polygon Hole", que como o nome diz, pode te ajudar a fechar buracos em polígonos. Para esta mesma tarefa, a Polygon Pen pode te servir bem também.

Um problema bem como que pode acontecer, é de os normals dos polígonos estarem bugados. Para resolver basta selecionar todos, clicar no botão direito e ir em "Align Normals" (Atalho U~A)

A ferramenta bridge, como o nome diz, facilitar criar pontes entre um vértice e outro. Caso precise unir dois elementos separados, porém que estão soldados na mesma camada, a ferramenta bridge pode fazer um bom trabalho neste caso.

Para conectar dois polígonos em uma única camada, use o connect objects. Isso unirá os polígonos camada só, o C4D irá tratar os dois polígonos, mesmo que separados, como um único modelo.

==Dicas válidas para criar splines com vista Top:== É possível, ao segurar Ctrl e arrastar um vértice, criar uma extrusão daquele vértice. Se segurar Ctrl + Shift e passar o mouse por uma aresta, ela se tornará uma curva, e ao clicar no botão esquerdo do mouse e arrastar para a esquerda ou direita, se controla a quantidade de subdivisões que a curva terá, soltar o botão esquerdo do mouse confirma a criação da curva.

**Booler:** Ele é um gerador, representado pela cor verde. Basicamente é o Pathfinder 3D. O booler trabalha com os elementos que estiverem como filhos dele, e a depender dos parâmetros configurados, ele irá subtrair ou unir os objetos filhos.

Segurar Alt e clicar nas duas bolinhas nas camadas, ativa ou desativa ambas ao mesmo tempo. Segurar Shift e arrastar pelas camadas, irá ativar ou desativar de todas as camadas que passar o mouse a bolinha que clicou primeiro, de acordo com a configuração dessa primeira bolinha (Se clicou na de cima para ativar, irá ativar a bolinha de cima de todas as camadas que passar o Mouse). Ao Segurar Ctrl, irá ativar ou desativar de todas as camadas ao mesmo tempo com o único clique a bolinha que clicar (Se clicar na de cima para ativar, irá ativar a bolinha de cima de todas as camadas com um único clique).

Sempre ajuste finamente a malha, buscando sempre o equilíbrio entre qualidade e quantidade de polígonos. Muitos polígonos fica pesado e pouco funcional, poucos polígonos fica leve porém com pouca qualidade, pouca nitidez. Procure o caminho do meio.

Segurar com o Ctrl e arrastar um modelo nas camadas irá duplicar a camada do modelo arrastado.

O gerador Loft une splines e cria um modelo a partir da união das splines.

Array e Cloner se parecem bastante. Ambos duplicam modelos.

==Deformadores são lilás, geradores são verdes, campos (Ou fields) são rosa.==

Bend é um deformador básico que deve ser filho de um modelo a ser deformado. Ele trabalha melhor com modelos com maior quantidade de faces, ou seja, uma maior quantidade de subdivisões, pois assim as deformações irão ser mais lisas, mais fluídas, mais redondinhas. É importante clicar em "Fit to Parent", para que o Bend se adapte ao tamanho do modelo a ser deformado. É possível fazer com que o Bend se aplique apenas em uma parte do modelo, deixando ele em contato com o modelo apenas na área que deseja que se deforme, para isto basta mover o Bend enquanto filho do modelo. Uma outra maneira de trabalhar com o Bend é tornar o modelo e o Bend como filhos de um objeto nulo, isso resulta em uma dinâmica um pouco diferente de colocar o Bend diretamente como filho do objeto Nulo, e que na minha opinião é melhor.

O Bend também tem algo que pode ser comparado a um Field Interno. Bem, pelo que entendi, o falloff foi removido do C4D nas últimas versões, e no lugar colocaram uma maior interação entre os deformadores e os fields. Fields são os novos falloff.

Os fields, quando trabalham com um deformador, irão ter duas áreas, uma interna que é 100% de força de deformação, e outra externa, que serve como um feather da deformação, criando uma área morna de influência do deformador.

Spline Wrape faz a deformação de um modelo respeitando uma spline.

Wind é um deformador que já trás uma animação pré-definida, que é a de onda. Ela serve para facilmente criar uma bandeira, e movimentos ondulatórios. Ele aplica a animação a depender da direção no qual está rotacionado e na sua posição em relação ao modelo no qual é filho. Como sempre, diversos parâmetros personalizáveis no menu de propriedades.

Uma das maneiras de animar alguma parâmetro, é ir clicar com o botão direito no keyframe de um parâmetro (Geralmente a esquerda dele) e ir em "Animation > Add keyframe", assim você cristaliza na timeline a configuração específica daquele parâmetro naquele frame específico da timeline.

Sempre trabalhe com interpolação de keyframes no modo linear. Isso vai definir uma suavidade para a maneira com qual o C4D se comporta ao passar por um keyframe.
==Nota pessoal: Não sei aonde a opção de interpolação de Keyframe foi parar nas novas versões do C4D, mas desconfio que tenha se transformado no menu "Animation" na janela de propriedades do projeto.==

Duplo clique na janela do material manager cria um material padrão pronto para ser editado. Clicar e arrastar um material para o modelo na viewport ou para uma camada, irá aplicar o material neste modelo ou camada.

Clicar duas vezes em um material irá abrir o material editor. Assim é possível editar as propriedades do material de modo mais amplo.

Ao transformar um modelo em filho de um outro modelo, é possível alinhar o primeiro modelo ao segundo zerando as coordenadas dele. E o primeiro modelo não perde o alinhamento caso seja desvinculado do pai, ele continua na mesma posição, mas não irá seguir mais o pai, como aconteceria se continuasse sendo filho.

Do mesmo jeito que se pode colocar uma imagem como textura (Escolhendo a imagem ao clicar em "Material editor > Color > Texture > Load Image) é possível colocar um vídeo como textura, pelo mesmo caminho. Mas quando se tem um vídeo como textura, é importante habilitar "Material Editor > Viewport > Animate Preview" para que a pre-visualização do vídeo como textura seja renderizada na viewport.

Bump é um efeito de material que trabalha com as sombras e a luz para criar texturas com profundidade. Ideal para criar deformações, relevos e imperfeições na textura do objeto.

A diferença entre Bump e Displacement é que o Bump gera a deformação na textura, e o Displacement gera a deformação diretamente no objeto (Respeitando a textura). Ambos servem para gerar relevo.

Interactive Render Region cria uma área na tela que será renderizada em tempo real, sendo possível ver uma preview do render a medida que você edita o projeto. É um opção bem pesada. A seta na direita da janela de render interativo irá definir a qualidade do render preview, quanto mais no alto, mais qualidade, quanto mais baixo, menos qualidade.

É possível criar reflexos parecido com o de espelhos nos parâmetros de "Reflectance" no material editor. Basta ir em "Material editor > Reflectance > Add > Reflection (Legacy)" e configurar os parâmetros para chegar no resultado desejado. Recomendo que ajuste principalmente a mesclagem em "Layer color" e "Layer Mask", caso seu objetivo seja que o objeto tenha apenas uma leve configuração de reflexo. Caso seu objetivo seja que o objeto seja um espelho 100%, apenas exibindo o que ele consegue refletir do que está ao redor, então não será necessário ajustar layer color e layer mask.

O material "Transparência" vai definir exatamente isto, a taxa de transparência de um objeto, podendo ser personalizado a reflexão, a taxa do quão transparente o objeto vai ser, enfim, diversos parâmetros.

Quanto ao material "Alpha" serve para inserir uma textura criada, tornando transparente todo o restante do modelo (Exceto a textura inserida). O que significa que dá para você escrever um texto no photoshop e deixar ele flutuando no formato de um modelo. Ou inserir um Png em um modelo e realmente deixar ele sem fundo, o detalhe é que este png vai se dobrar de acordo com o formato do modelo texturizado com alpha e textura personalizada.

Ao se aplicar um material em um modelo, o material vira uma tag naquele modelo. Ao ir nas configurações de tag do material é possível ajustar o modo de projeção do material. A projeção cilíndrica geralmente facilita a se criar um encarte ou rótulo de um produto. É possível personalizar a textura de um objeto tanto pelo modo de manipulação de textura (Está junto dos modos de manipulação de pontos, arestas, faces e modelo), ou diretamente pelos parâmetros disponíveis na tag do material. Quando o modo de projeção é frontal, apenas se pode ajustar parâmetros pela janela de propriedades. Como sempre, diversos parâmetros personalizáveis.

O cloner no modo linear trabalha com deformações progressivas, mantendo o elemento original sem deformações o máximo possível, sendo assim, as deformações configuradas nos parâmetro irão ser aplicadas apenas nos clones. O cloner tem a função de clonar objetos (Dã). Ele se parece um pouco com o Array.

O Cloner tem vários modos, sendo eles object, honeycomb, radial, grid e linear. Cada um com sua função específica. Como sempre, é possível animar diversos parâmetros do cloner na janela de propriedades do objeto.

O modo object faz com que o cloner trabalhe seguindo de referência um objeto de modelo. A depender da maneira que você configura o cloner no modo object, você pode fazer com que o cloner aja apenas nos limites do modelo, que ele crie de acordo com as vertex, edges ou points do modelo, que a clonagem seja feita na superfície do objeto. Enfim, como sempre, diversos parâmetros personalizáveis e animáveis.

Para manter um modelo em seu lugar, e evitar resetar o PSR ao aplicar cloner, basta desativar a opção "Reset Coordinates" nas configurações do cloner. 

Usando o modo de objeto do cloner, é possível fazer com o cloner siga uma spline. Diversos parâmetros novos e personalizáveis são apresentados neste modo de seguir spline. Inclusive o Rail, que faz com que os objetos clonados sejam influenciados por um terceiro objeto, pode gerar variações de escala, tornar ele um centro de interesse dos clones (Target, modo alvo, no qual os clones se viram em direção ao modelo rail).