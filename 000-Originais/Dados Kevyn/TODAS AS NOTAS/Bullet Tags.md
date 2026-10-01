**Rigid Body:** Um modelo sólido.
**Soft Body:** Um modelo "mole"
	Quanto mais segmentos no modelo, mais deformação irá ter, mais legal fica e mais pesado fica.
**Collider Body:** Um modelo de colisão, ficará estático na cena e recebe física.
	 O Collider das Bullet Tags só interage com outros bullets tags.

É possível configurar vários dos parâmetros das bullets tags. Nos Rigid Body por exemplo, dá para ajustar a potência no qual a gravidade vai afetar o modelo com a tag, se você zera esse parâmetro, o modelo se mantêm parado no espaço, como se estivesse no vácuo.

É possível ativar e desativar o Dynamics, usando isso com KeyFrames você pode definir em que momento o Dynamics irá ser ativado. Só quando o Dynamics é ativado que a animação começa a roda.

As vezes será necessário mudar a configuração de Shape dos modelos com Collider Body. Configurações de Shape estão disponíveis no menu "Collider" nas propriedades da tag Collider Body.
##### **Trigger:**
Nas propriedades dos Dynamics Tags, existe esta opção chamada "Trigger", que irá definir as condições para o início da animação Dynamics.
##### **Bounce:**
Está presente nas propriedades de Collision, no menu de configuração das Dynamics Tags. Ela se refere a elasticidade e ao movimento de quicar.
##### **Friction:**
É fricção, é a taxa de resistência que um objeto vai ter ao colidir ou deslizar por uma superfície.
##### **Pressure:**
É um atributo de inflação. Aumentar este parâmetro do Soft Body faz com que o modelo infle.