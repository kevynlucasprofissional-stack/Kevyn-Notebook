# Fluxo de Extração

### Pré-prompt
Eu quero um número, qual o número de notas atômicas dá para fazer com estes dados?
Me dê uma idéia de quantas notas seriam ideal para um estudo essencial, para um estudo profundo e para um estudo exaustivo. E a partir desses três números, em quantas notas você me recomenda mirar, qual o ponto ideal entre profundidade e praticidade para estes dados?

### Prompt Mapeamento
Aja como um analista minucioso. Identifique e liste todos os conceitos, idéias, argumentos e princípios filosóficos presentes nestes dados. Quero extrair o máximo possível (alta granularidade).

Me dê apenas uma lista numerada da seguinte forma:

Nota [número da nota]:
Título: [Nome único, curto, impactante e pesquisável sugerido para a nota atômica]
Resumo: [Breve descrição (uma linha)]

Objetivo: Identificar pelo menos  notas neste trecho. Aguardo a lista.

### Prompt Execução
Aqui está o bloco de notas para processar agora.

Lembre-se:

1. Consulte o arquivo '00_lista_de_notas' (que contém todos os títulos do mapeamento) para criar as conexões da Teia Local.
2. Consulte o arquivo '00_notas_do_cofre' para os Insights. Somente crie links nos insights para notas que já existem e que estão descritas em '00_notas_do_cofre', seja rigoroso com isso.
3. Cuidado extremo com os Flashcards (Sem Links [[ ]]). Siga de forma rigorosa as regras contidas em <regras_flashcards><\regras_flashcards>
4. As regras contidas em <definicao_campos><\definicao_campos> são de prioridade máxima, sempre organize o JSON respeitando de forma rigorosa as instruções ali contidas.

Notas para processar:



Gere o JSON correspondente.