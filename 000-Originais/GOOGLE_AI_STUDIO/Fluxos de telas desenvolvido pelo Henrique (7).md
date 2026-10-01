<ao_abrir>
Ao abrir o sistema, o usuário visualiza uma animação breve do logotipo da aplicação no centro da tela.

A animação deve durar aproximadamente 2 segundos e pode conter:
- fade-in do logotipo
- leve zoom
- transição suave para a tela inicial

Após a animação, o sistema encaminha automaticamente para a <tela_0>.
</ao_abrir>



<tela_0>
Tela de boas-vindas (Welcome Screen).

Elementos da tela:

- Logo do sistema centralizado.
- Pequena frase de apresentação da plataforma.
- Botão principal: "Entrar"
- Botão secundário: "Criar conta"

Comportamento dos botões:

Botão "Entrar"
→ encaminha para <tela_1>

Botão "Criar conta"
→ encaminha para <tela_1> (modo cadastro)

Rodapé da tela:

- link "Termos de uso"
- link "Política de privacidade"
</tela_0>



<tela_1>
Tela de autenticação (Login / Cadastro).

Elementos da tela:

Campo:
- Email

Campo:
- Senha

Botões:

Botão "Entrar"
→ valida credenciais
→ se válidas, encaminha para <tela_2>

Botão "Criar conta"
→ cria usuário
→ encaminha para <tela_2>

Link:

"Esqueci minha senha"
→ abre modal de recuperação de senha.

Layout sugerido:

- formulário centralizado
- logotipo no topo
- fundo simples

Após autenticação bem-sucedida o usuário é encaminhado para <tela_2>.
</tela_1>



<tela_2>
Tela principal do sistema (Dashboard).

Esta tela funciona como hub central da aplicação.

Elementos da tela:

Barra superior contendo:

- Logo da aplicação
- Botão "Nova análise"
- Botão "Histórico"
- Botão "Perfil"

Ações:

Botão "Nova análise"
→ encaminha para <tela_3>

Botão "Histórico"
→ encaminha para <tela_4>

Botão "Perfil"
→ abre menu com:
  - Configurações
  - Logout

Área central:

Cards com resumo das análises recentes do usuário.

Cada card contém:

- Tipo de análise
- Data
- Resultado resumido
- Botão "Abrir"

Botão "Abrir"
→ encaminha para <tela_8> (chat da análise existente)
</tela_2>



<tela_3>
Tela de criação de nova análise.

Título da tela:

"Nova análise"

Descrição:

O usuário deve escolher o tipo de análise que deseja realizar.

Opções disponíveis:

Card 1
"Análise Clínica"

Botão "Selecionar"
→ encaminha para <tela_5>

Card 2
"Análise de Água"

Botão "Selecionar"
→ encaminha para <tela_6>

Interface:

- cards grandes clicáveis
- ícones ilustrativos
</tela_3>



<tela_4>
Tela de histórico de análises.

Lista cronológica das análises realizadas pelo usuário.

Cada item do histórico deve conter:

- Tipo de análise
- Data
- Resultado resumido em uma linha
- Legislação aplicada
- Status de conformidade

Elementos dentro de cada bloco:

Resumo da análise:
exemplo:

"Análise clínica – identificação de bactéria X"

ou

"Análise água – água não conforme para consumo"

Informações adicionais:

- legislação aplicada
- indicador visual de conformidade

Botões em cada bloco:

Botão "Abrir análise"
→ encaminha para <tela_8>

Botão "Avaliar resultado"
→ abre formulário de feedback.

Filtro superior:

- filtrar por tipo
- filtrar por data
</tela_4>



<tela_5>
Fluxo de análise clínica.

Título:

"Tipo de amostra"

Usuário deve escolher o tipo de amostra analisada.

Opções:

- Sangue
- Urina
- Secreção

Cada opção é representada por um card clicável.

Seleção de qualquer opção
→ encaminha para <tela_7>
</tela_5>



<tela_6>
Fluxo de análise de água.

Título:

"Tipo de água analisada"

Usuário deve escolher o tipo de água conforme norma.

Lista de opções:

- água potável
- água subterrânea
- água superficial
- água de poço
- água mineral
- água de abastecimento público
- água para irrigação
- água industrial

Ao selecionar qualquer opção
→ encaminha para <tela_7>
</tela_6>



<norma_legal>
Todo o sistema deve estar em conformidade com:

- CONAMA 396/2008
- CONAMA 357/2005
- GM/MS 888/2021

Essas normas são utilizadas para validar os parâmetros de qualidade da água e interpretação dos resultados laboratoriais.

As respostas geradas pelo sistema devem citar essas normas quando aplicável.
</norma_legal>



<tela_7>
Tela de envio de arquivos.

Usuário deve enviar os documentos necessários para análise.

Elementos da tela:

Botão:

"Enviar PDF do teste"

Botão:

"Enviar manual do teste do laboratório"

Área de drag and drop para upload.

Arquivos aceitos:

- PDF
- imagem

Após upload concluído:

Botão "Continuar"
→ encaminha para <tela_8>
</tela_7>



<tela_8>
Tela de captura de imagem da análise.

O usuário deve tirar ou enviar uma foto do teste realizado.

Elementos da tela:

Botão:

"Tirar foto"

Botão:

"Enviar imagem"

Aviso importante:

"A qualidade do resultado depende diretamente da qualidade da foto."

Instruções exibidas:

- foto bem iluminada
- foco nítido
- evitar sombras

Processo automático:

A IA analisa a qualidade da imagem.

Sistema gera uma nota de qualidade de 0 a 10.

Se nota < 8

Mensagem exibida:

"A imagem não possui qualidade suficiente. Tire uma nova foto."

Se nota ≥ 8

Botão "Prosseguir"
→ encaminha para <tela_9>
</tela_8>



<tela_9>
Tela de resultado da análise.

Interface estilo chat entre usuário e IA.

Elementos da tela:

Mensagem inicial automática contendo:

1. Resumo da análise
2. Interpretação científica do resultado
3. Conformidade com legislação
4. Botão para baixar relatório completo

Botão:

"Baixar relatório em PDF"

Conteúdo do relatório:

- interpretação técnica
- parâmetros analisados
- base legal aplicada
- recomendações

Exemplos de resposta:

Análise água:

"Resultado não conforme para consumo humano conforme GM/MS 888/2021."

Análise clínica:

"Identificação da bactéria X. Associada à doença Y. Mecanismo de ação Z."

Após apresentar o resultado:

Mensagem final:

"Alguma dúvida sobre o resultado?"

Usuário pode interagir com a IA diretamente no chat.
</tela_9>