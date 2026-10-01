Crie um aplicativo marketplace mobile chamado **TPM — Tudo Para Mulheres**.

O objetivo do app é conectar mulheres que procuram serviços de beleza em domicílio com profissionais que oferecem esses serviços.

Este é um marketplace de serviços similar ao modelo Uber / Airbnb, mas focado em serviços de beleza HomeCare.

Os dois tipos de usuário são:

1) Cliente (quem contrata)
2) Profissional (quem oferece serviços)

A V1 deve focar apenas no núcleo do marketplace.

Não incluir ainda:
- blog
- loja
- IA concierge
- conteúdo
- programas premium

A prioridade é:

cadastro → descoberta de profissionais → perfil → agendamento → gestão de pedidos → avaliação.

--------------------------------------------------

ARQUITETURA GERAL DO APP

O app possui dois ambientes principais:

CLIENTE
PROFISSIONAL

O sistema deve identificar o tipo de conta no login e direcionar para a área correta.

--------------------------------------------------

TIPOS DE USUÁRIOS

CLIENTE

Campos do usuário:

- id
- nome
- data de nascimento
- telefone
- email
- senha
- cidade
- bairro
- endereço padrão
- favoritos
- avaliações feitas

PROFISSIONAL

Campos:

- id
- nome
- nome profissional
- telefone
- email
- senha
- cidade
- bairros atendidos
- categorias de serviço
- descrição profissional
- tempo de experiência
- atende em domicílio (boolean)
- dias disponíveis
- horários disponíveis
- fotos de portfólio
- serviços cadastrados
- avaliação média
- status do perfil (em análise / ativo)

--------------------------------------------------

ENTIDADE SERVIÇO

Cada profissional pode cadastrar vários serviços.

Campos:

- id
- profissional_id
- nome
- descrição
- preço inicial
- duração média
- observações

--------------------------------------------------

ENTIDADE AGENDAMENTO

Campos:

- id
- cliente_id
- profissional_id
- serviço_id
- data
- horário
- endereço
- observações
- valor
- status

Status possíveis:

- solicitado
- aceito
- recusado
- cancelado
- concluído

--------------------------------------------------

ENTIDADE AVALIAÇÃO

Campos:

- id
- cliente_id
- profissional_id
- agendamento_id
- nota (1 a 5)
- comentário

Avaliações só podem ocorrer após status "concluído".

--------------------------------------------------

TELAS DO APLICATIVO

SPLASH

Exibir logo TPM
Texto curto: "Beleza onde você estiver"

Após alguns segundos abrir tela de boas vindas.

--------------------------------------------------

TELA 0 — BOAS VINDAS

Elementos:

Logo
Título: Tudo Para Mulheres

Botões:

Entrar
Criar conta
Quero divulgar meus serviços

Fluxos:

Entrar → Tela Login
Criar conta → Cadastro Cliente
Quero divulgar meus serviços → Cadastro Profissional

--------------------------------------------------

TELA LOGIN

Campos:

email ou telefone
senha

Botões:

Entrar
Continuar com Google
Esqueci senha

Fluxos:

login cliente → Home Cliente
login profissional → Home Profissional

--------------------------------------------------

CADASTRO CLIENTE

Campos:

nome
data nascimento
telefone
email
senha
confirmar senha
cidade
bairro
aceite termos

Após cadastro → Home Cliente

--------------------------------------------------

CADASTRO PROFISSIONAL

ETAPA 1

nome
nome profissional
telefone
email
senha
cidade
bairro
aceite termos

ETAPA 2

categoria principal
categorias secundárias
descrição profissional
tempo experiência
regiões atendidas
atende em domicílio
dias disponíveis
horários disponíveis

ETAPA 3

cadastro de serviços
preço
duração

ETAPA 4

portfólio
foto perfil
fotos trabalhos
documento
chave pix

Após finalizar → Home Profissional

--------------------------------------------------

HOME CLIENTE

Elementos:

campo de busca
categorias
lista de profissionais próximas
banner

Categorias:

Cabelo
Manicure
Pedicure
Maquiagem
Sobrancelhas
Unhas
Todos

Barra inferior:

Início
Buscar
Agendamentos
Favoritos
Perfil

--------------------------------------------------

BUSCA DE PROFISSIONAIS

Filtros:

serviço
bairro
faixa preço
avaliação
disponibilidade hoje
fim de semana

Ordenação:

mais próximas
melhor avaliadas
menor preço

Cada profissional deve mostrar:

foto
nome
serviços
nota
bairro
preço inicial

Botão:

Ver perfil

--------------------------------------------------

PERFIL DA PROFISSIONAL

Elementos:

foto
nome
nota média
descrição
serviços
preços
portfólio
regiões atendidas
horários

Botões:

Favoritar
Solicitar agendamento
Enviar mensagem

--------------------------------------------------

SOLICITAR AGENDAMENTO

Campos:

serviço
data
horário
endereço
observações
forma pagamento

Botão:

Enviar solicitação

Status inicial:

SOLICITADO

--------------------------------------------------

AGENDAMENTOS CLIENTE

Abas:

Pendentes
Confirmados
Finalizados
Cancelados

Cada item deve mostrar:

profissional
serviço
data
horário
endereço
status

--------------------------------------------------

DETALHE DO AGENDAMENTO

Informações:

serviço
profissional
data
endereço
valor
observações

Ações possíveis:

cancelar
reagendar
falar com profissional
avaliar

--------------------------------------------------

CHAT

Chat simples entre cliente e profissional.

Funções:

mensagens
envio de imagens

--------------------------------------------------

AVALIAÇÃO

Após atendimento concluído:

nota de 1 a 5
comentário opcional

--------------------------------------------------

HOME PROFISSIONAL

Elementos:

resumo do dia
pedidos pendentes
agenda
serviços cadastrados

Menu inferior:

Início
Pedidos
Agenda
Portfólio
Perfil

--------------------------------------------------

PEDIDOS RECEBIDOS

Abas:

Novos
Aceitos
Recusados
Finalizados

Ações:

Aceitar
Recusar
Ver detalhes

--------------------------------------------------

AGENDA PROFISSIONAL

Visualização:

Hoje
Semana
Mês

Mostrar:

cliente
serviço
horário
endereço

--------------------------------------------------

PORTFÓLIO

Adicionar fotos
Remover fotos
Reordenar fotos

--------------------------------------------------

REGRAS DE NEGÓCIO

Cliente só pode solicitar atendimento se tiver conta criada.

Profissional só aparece na busca se:

- tiver cadastro completo
- tiver pelo menos 1 serviço
- tiver região definida
- estiver com status ativo

Avaliações só podem ocorrer após atendimento concluído.

--------------------------------------------------

OBJETIVO DA V1

Construir um marketplace funcional com:

- cadastro
- busca
- perfil profissional
- solicitação de atendimento
- gestão de pedidos
- agenda
- avaliação