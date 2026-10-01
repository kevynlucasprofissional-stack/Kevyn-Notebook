<introducao>
Este documento é um guia prático para a criação de prompts usando uma metodologia estruturada com tags. O objetivo é transformar uma tarefa complexa em componentes lógicos e referenciáveis, aumentando a precisão e o controle sobre a resposta da IA.

Cada pedaço de informação, contexto, regra ou instrução é encapsulado em suas próprias tags, como <exemplo_de_tag>.
</introducao>

<principios_fundamentais>
Para criar um prompt eficaz neste formato, siga estes princípios:

1.  **<principio_encapsulamento>**
    Toda e qualquer instrução deve estar dentro de um par de tags de abertura e fechamento. O nome da tag deve descrever de forma clara e concisa o seu conteúdo.
    Exemplo: em vez de um parágrafo longo, separe o público-alvo em `<publico_alvo>` e o tom de voz em `<tom_de_voz>`.
    **</principio_encapsulamento>**

2.  **<principio_modularidade>**
    Crie blocos de informação reutilizáveis. Por exemplo, informações legais, personas ou regras de formatação podem ser definidas em uma tag específica, como <regras_gerais>, e depois apenas referenciadas quando necessário.
    **</principio_modularidade>**

3.  **<principio_referencia>**
    Conecte os diferentes blocos lógicos mencionando o nome de outras tags. Isso cria um fluxo de trabalho claro para a IA seguir.
    Exemplo: "Após executar a <tarefa_1>, use o resultado como entrada para a <tarefa_2>."
    **</principio_referencia>**

4.  **<principio_hierarquia>**
    Organize as tags de forma lógica, começando do mais geral para o mais específico. Use a indentação para visualizar a hierarquia e a relação entre as diferentes partes do prompt.
    **</principio_hierarquia>**
</principios_fundamentais>

</manual_de_prompting_estruturado>