---
Modificado:
  - quarta-feira 70 11/03/2026
  - Monday 61 02/03/2026
  - domingo 53 22/02/2026
  - sexta-feira 44 13/02/2026
  - domingo 39 08/02/2026
Criado: domingo 39 08/02/2026
---
<ao_abrir>
Animação do logo principal e transição para a <tela_0>
</ao_abrir>

<tela_0>
Tela de login, feito login, encaminhasse para <tela_1>
<\tela_0>

<tela_1>
Botão de "Nova Análise" leva para <tela_2>
Botão de "Histórico" leva para <tela_3>
</tela_1>

<tela_3>
Histórico.
Cada bloco de histórico deve ter:
- Resumo de uma linha da análise, incluindo tipo de teste e resultado
- Legislação que segue.
- Avalie este resultado
</tela_3>

<tela_2>
Escolha do tipo de análise:
- Clínica leva para a <tela_4>
- Qualidade água leva para a<tela_5>

Na parte superior é melhor copiar esta estrutura:
![[Pasted image 20260128221901.png]]
</tela_2>

<tela_4>
Análise clínica precisa dar a opção do usuário informar o tipo de amostra:
- Sangue
- Secreção
- Urina

Encaminha para <tela_7>
</tela_4>

<tela_5>
Aqui o usuário precisa escolher o tipo da água dentre as 8 opções conforme documentação descrito em <norma_legal>
Encaminha para <tela_7>
<tela_5>

<norma_legal>
Todo o app deve ser feito em conformidade com a documentação do Conama 396 de 2008, Conama 357 de 2005 e GM/MS 888/2021.
<norma_legal>

<tela_7>
Opção de o usuário subir o PDF do teste, o PDF do manual de teste que o laboratório usa, tipo um botão de upload. Escolhido a opção, o usuário é encaminhado para a <tela_8>

Exemplo de testes:
![[Pasted image 20260128225227.png]]
</tela_7>

<tela_8>
Podemos nos inspirar no exemplo abaixo. Feito este passo, usuário é encaminhado para <tela_9>

Colocar um aviso de que a qualidade do resultado depende 100% de uma foto boa. Pedir para a foto ser bem iluminada, nítida.

Salva-guarda para IA analisar a foto e dar uma nota de 0 a 10 para a qualidade. Se a nota for abaixo de 8, pedir para tirar a foto de novo.

![[Pasted image 20260128225951.png]]
</tela_8>

<tela_9>
**Modelo padrão de mensagem inicial do chat que vai abrir aqui:**
1. ![[Pasted image 20260128233200.png]]
2. O resultado completo em PDF para baixar.
3. Pedido de avaliação do resultado.
4. O resumo do resultado com pergunta "Alguma dúvida?"

Essa é a tela de resultado, o resultado final deve ser como um chat no qual o pesquisador pode conversar com a IA que já está contextualizada.
Aqui daríamos o resumo e uma opção de baixar o documento em PDF com uma análise completa.

"Em conformidade com a lei, não conforme..." - Análise água.

"Identificação de bactéria e fundo, mecanismo de ação, responsável por x doença" - Análise Clínica.

E no final fazer uma pergunta se o pesquisador ficou com alguma dúvida.
</tela_9>