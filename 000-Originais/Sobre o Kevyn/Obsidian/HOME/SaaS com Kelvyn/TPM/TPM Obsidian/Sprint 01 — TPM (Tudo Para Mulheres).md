# Marketplace HomeCare de Beleza — Estrutura Base do App

<objetivo_do_sprint>  
Estruturar a primeira versão funcional do app TPM com foco em conectar mulheres que procuram serviços de beleza em domicílio com profissionais que oferecem esses serviços.

Neste Sprint 01, o objetivo não é ainda desenvolver tudo, mas organizar com clareza:

- como cada tela funciona;
    
- quais botões levam para onde;
    
- como será a navegação base;
    
- quais informações cada perfil precisa preencher;
    
- como acontece a jornada de contratação;
    
- como acontece a jornada de cadastro da profissional.
    

A ideia é deixar o fluxo pronto e bem amarrado antes de passar para o Lovable.  
</objetivo_do_sprint>

<contexto_do_produto>  
O TPM nasceu como uma proposta de plataforma que conecta mulheres a serviços, produtos e conteúdos em um ecossistema unificado. Nos materiais anexados, aparecem marketplace, conteúdo e outras frentes, mas para esta etapa inicial o foco deve ser reduzido para o núcleo mais viável do projeto: serviços HomeCare de beleza.

Ou seja: a V1 do TPM será um app de intermediação entre:

- Cliente: mulher que quer contratar um serviço de beleza;
    
- Profissional: mulher que oferece esse serviço.
    

Serviços iniciais sugeridos para a V1:

- Cabeleireira
    
- Manicure
    
- Pedicure
    
- Maquiagem
    
- Designer de sobrancelhas
    
- Alongamento de unhas
    

A lógica principal do app será:  
buscar profissional → ver perfil → escolher serviço → agendar/solicitar → confirmar atendimento.  
</contexto_do_produto>

<ao_abrir>  
Animação simples com logo TPM e transição para <tela_0>.

Sugestão:

- fundo clean;
    
- logo central;
    
- subtítulo curto: “Beleza onde você estiver”;
    
- após alguns segundos, seguir automaticamente para <tela_0>.  
    </ao_abrir>
    

<tela_0>  
Tela de boas-vindas / entrada.

Elementos:

- Logo TPM
    
- Título: “Tudo Para Mulheres”
    
- Subtítulo: “Encontre profissionais de beleza para atendimento onde você estiver”
    
- Botão “Entrar”
    
- Botão “Criar conta”
    
- Link “Quero divulgar meus serviços”
    

Fluxos:

- Botão “Entrar” leva para <tela_1>
    
- Botão “Criar conta” leva para <tela_2>
    
- Link “Quero divulgar meus serviços” leva para <tela_3>
    

Observação:  
Aqui já começamos a separar claramente os dois públicos do app:

- cliente;
    
- profissional.  
    </tela_0>
    

<tela_1>  
Tela de login.

Campos:

- E-mail ou celular
    
- Senha
    

Botões:

- “Entrar”
    
- “Continuar com Google”
    
- “Esqueci minha senha”
    

Fluxos:

- Login bem-sucedido de cliente leva para <tela_5>
    
- Login bem-sucedido de profissional leva para <tela_20>
    
- “Esqueci minha senha” leva para <tela_4>
    

Observação:  
O app deve identificar o tipo de conta e redirecionar para a área correta.  
</tela_1>

<tela_2>  
Tela de criação de conta como cliente.

Campos:

- Nome completo
    
- Data de nascimento
    
- Celular
    
- E-mail
    
- Senha
    
- Confirmar senha
    
- Cidade
    
- Bairro
    
- Aceite dos termos
    

Botão:

- “Criar conta”
    

Fluxo:

- Cadastro concluído leva para <tela_5>
    

Observação:  
Cidade e bairro já ajudam no início da recomendação de profissionais próximas.  
</tela_2>

<tela_3>  
Tela de início do cadastro da profissional.

Texto de apoio:  
“Cadastre seus serviços no TPM e receba pedidos de clientes da sua região.”

Campos:

- Nome completo
    
- Nome profissional
    
- Celular
    
- E-mail
    
- Senha
    
- Cidade de atendimento
    
- Bairro base
    
- Aceite dos termos
    

Botão:

- “Continuar cadastro profissional”
    

Fluxo:

- Leva para <tela_21>  
    </tela_3>
    

<tela_4>  
Tela de recuperação de senha.

Campo:

- E-mail ou celular
    

Botão:

- “Enviar código”
    

Fluxo:

- Após envio, mostrar mensagem de confirmação e opção de voltar para <tela_1>  
    </tela_4>
    

<tela_5>  
Home da cliente.

Objetivo:  
Ser a principal tela de descoberta e busca de profissionais.

Elementos:

- Campo de busca: “Qual serviço você procura?”
    
- Campo/localização atual
    
- Banner principal
    
- Categorias em destaque
    
- Lista de profissionais em destaque
    
- Seção “Próximas de você”
    
- Barra de navegação inferior
    

Categorias sugeridas:

- Cabelo
    
- Manicure
    
- Pedicure
    
- Maquiagem
    
- Sobrancelhas
    
- Unhas
    
- Todos
    

Barra inferior:

- Início
    
- Buscar
    
- Agendamentos
    
- Favoritos
    
- Perfil
    

Fluxos:

- Tocar em categoria leva para <tela_6>
    
- Tocar em profissional leva para <tela_8>
    
- Aba “Buscar” leva para <tela_6>
    
- Aba “Agendamentos” leva para <tela_12>
    
- Aba “Favoritos” leva para <tela_13>
    
- Aba “Perfil” leva para <tela_14>  
    </tela_5>
    

<tela_6>  
Tela de busca/listagem de profissionais.

Filtros:

- Serviço
    
- Bairro/região
    
- Atendimento em domicílio
    
- Faixa de preço
    
- Avaliação
    
- Disponibilidade hoje
    
- Disponibilidade fim de semana
    

Ordenação:

- Mais próximas
    
- Melhor avaliadas
    
- Menor preço
    
- Mais recomendadas
    

Cada card de profissional deve ter:

- Foto
    
- Nome profissional
    
- Serviços principais
    
- Nota
    
- Bairro/região
    
- Faixa de preço inicial
    
- Botão “Ver perfil”
    

Fluxos:

- Card ou botão “Ver perfil” leva para <tela_8>
    
- Botão filtros abre <tela_7>  
    </tela_6>
    

<tela_7>  
Tela/modal de filtros.

Campos:

- Categoria do serviço
    
- Região
    
- Preço mínimo e máximo
    
- Atendimento em casa
    
- Dias disponíveis
    
- Horários disponíveis
    
- Avaliação mínima
    

Botões:

- “Aplicar filtros”
    
- “Limpar filtros”
    

Fluxo:

- “Aplicar filtros” volta para <tela_6> com resultados filtrados  
    </tela_7>
    

<tela_8>  
Tela de perfil da profissional.

Elementos:

- Foto de capa ou perfil
    
- Nome profissional
    
- Nota média
    
- Número de avaliações
    
- Cidade / bairros atendidos
    
- Descrição profissional
    
- Serviços oferecidos
    
- Preços
    
- Fotos de trabalhos
    
- Formas de atendimento
    
- Horários disponíveis
    
- Botão “Favoritar”
    
- Botão “Solicitar agendamento”
    
- Botão “Enviar mensagem”
    

Fluxos:

- “Solicitar agendamento” leva para <tela_9>
    
- “Enviar mensagem” leva para <tela_11>
    
- “Favoritar” salva e pode levar item para <tela_13>
    

Observação:  
Essa é uma das telas mais importantes do app, porque aqui acontece a conversão.  
</tela_8>

<tela_9>  
Tela de solicitação/agendamento.

Campos:

- Serviço selecionado
    
- Data desejada
    
- Horário desejado
    
- Endereço do atendimento
    
- Complemento
    
- Observações
    
- Opção: “Quero atendimento em domicílio”
    
- Forma de pagamento preferida
    

Botão:

- “Enviar solicitação”
    

Fluxo:

- Envia pedido para a profissional e leva para <tela_10>  
    </tela_9>
    

<tela_10>  
Tela de confirmação de solicitação enviada.

Mensagem:  
“Seu pedido foi enviado para a profissional. Você será avisada quando ela aceitar.”

Botões:

- “Ir para meus agendamentos”
    
- “Continuar buscando”
    

Fluxos:

- “Ir para meus agendamentos” leva para <tela_12>
    
- “Continuar buscando” leva para <tela_5>  
    </tela_10>
    

<tela_11>  
Tela de conversa entre cliente e profissional.

Objetivo:  
Permitir alinhamento antes da confirmação final.

Funções:

- Mensagens de texto
    
- Envio de foto de referência
    
- Confirmação de detalhes
    
- Status do atendimento
    

Botões/ações:

- Campo de mensagem
    
- Anexar imagem
    
- “Solicitar agendamento” caso ainda não tenha agendado
    

Fluxos:

- Pode retornar ao perfil <tela_8>
    
- Pode seguir para <tela_9>  
    </tela_11>
    

<tela_12>  
Tela de agendamentos da cliente.

Abas:

- Pendentes
    
- Confirmados
    
- Finalizados
    
- Cancelados
    

Cada card deve mostrar:

- Nome da profissional
    
- Serviço
    
- Data e horário
    
- Endereço
    
- Status
    
- Botão de detalhes
    

Fluxos:

- Tocar no card leva para detalhes do agendamento em <tela_15>  
    </tela_12>
    

<tela_13>  
Tela de favoritos.

Lista de profissionais salvas pela cliente.

Cada item:

- Foto
    
- Nome
    
- Serviço principal
    
- Nota
    
- Botão “Ver perfil”
    

Fluxo:

- “Ver perfil” leva para <tela_8>  
    </tela_13>
    

<tela_14>  
Perfil da cliente.

Seções:

- Dados pessoais
    
- Endereços salvos
    
- Métodos de pagamento
    
- Notificações
    
- Termos e privacidade
    
- Ajuda
    
- Sair
    

Fluxos:

- Editar dados abre subtelas simples de edição  
    </tela_14>
    

<tela_15>  
Detalhe do agendamento.

Informações:

- Profissional
    
- Serviço contratado
    
- Data e hora
    
- Endereço
    
- Valor combinado
    
- Forma de pagamento
    
- Observações
    
- Status do pedido
    

Ações possíveis conforme status:

- Cancelar solicitação
    
- Reagendar
    
- Falar com a profissional
    
- Avaliar atendimento
    

Fluxos:

- “Falar com a profissional” leva para <tela_11>
    
- “Avaliar atendimento” leva para <tela_16>  
    </tela_15>
    

<tela_16>  
Tela de avaliação da profissional.

Campos:

- Nota de 1 a 5
    
- Comentário opcional
    

Botão:

- “Enviar avaliação”
    

Fluxo:

- Após enviar, volta para <tela_12> ou <tela_15>  
    </tela_16>
    

<tela_20>  
Home da profissional.

Objetivo:  
Ser o painel principal da prestadora de serviço.

Elementos:

- Saudação inicial
    
- Resumo do dia
    
- Solicitações pendentes
    
- Próximos atendimentos
    
- Serviços cadastrados
    
- Botões rápidos
    

Barra inferior:

- Início
    
- Pedidos
    
- Agenda
    
- Portfólio
    
- Perfil
    

Fluxos:

- “Pedidos” leva para <tela_24>
    
- “Agenda” leva para <tela_25>
    
- “Portfólio” leva para <tela_26>
    
- “Perfil” leva para <tela_27>  
    </tela_20>
    

<tela_21>  
Continuação do cadastro profissional.

Campos:

- Categoria principal
    
- Categorias secundárias
    
- Descrição profissional
    
- Tempo de experiência
    
- Cidade
    
- Bairros/regiões onde atende
    
- Atende em domicílio? sim/não
    
- Dias disponíveis
    
- Horários disponíveis
    

Botão:

- “Continuar”
    

Fluxo:

- Leva para <tela_22>  
    </tela_21>
    

<tela_22>  
Cadastro de serviços e preços.

A profissional poderá adicionar múltiplos serviços.

Cada serviço deve conter:

- Nome do serviço
    
- Descrição curta
    
- Preço inicial
    
- Tempo médio
    
- Observação opcional
    

Botão:

- “Adicionar serviço”
    
- “Continuar”
    

Fluxo:

- “Continuar” leva para <tela_23>  
    </tela_22>
    

<tela_23>  
Cadastro de portfólio e validação do perfil.

Campos:

- Foto de perfil
    
- Fotos de trabalhos
    
- Documento de identificação
    
- Chave Pix ou dados de recebimento
    
- Termo de responsabilidade
    

Botão:

- “Finalizar cadastro”
    

Fluxo:

- Cadastro finalizado leva para <tela_20>
    

Observação:  
Pode haver status “perfil em análise” antes de ativar publicamente.  
</tela_23>

<tela_24>  
Tela de pedidos recebidos.

Abas:

- Novos pedidos
    
- Aceitos
    
- Recusados
    
- Finalizados
    

Cada card deve mostrar:

- Cliente
    
- Serviço solicitado
    
- Data/hora sugerida
    
- Local
    
- Observações
    
- Botões de ação
    

Botões:

- “Aceitar”
    
- “Recusar”
    
- “Ver detalhes”
    

Fluxos:

- “Aceitar” atualiza status e envia para agenda
    
- “Recusar” encerra solicitação
    
- “Ver detalhes” leva para <tela_28>  
    </tela_24>
    

<tela_25>  
Agenda da profissional.

Visualizações:

- Hoje
    
- Semana
    
- Mês
    

Cada agendamento deve exibir:

- Cliente
    
- Serviço
    
- Horário
    
- Endereço
    
- Status
    

Fluxos:

- Tocar em agendamento leva para <tela_28>  
    </tela_25>
    

<tela_26>  
Portfólio da profissional.

Funções:

- Adicionar fotos
    
- Excluir fotos
    
- Reordenar fotos
    
- Destacar melhores trabalhos
    

Botões:

- “Adicionar foto”
    
- “Salvar alterações”  
    </tela_26>
    

<tela_27>  
Perfil da profissional.

Seções:

- Dados pessoais
    
- Informações profissionais
    
- Regiões atendidas
    
- Serviços e preços
    
- Formas de pagamento
    
- Conta bancária/Pix
    
- Notificações
    
- Suporte
    
- Sair
    

Fluxos:

- Editar cada seção em subtelas de edição  
    </tela_27>
    

<tela_28>  
Detalhe do pedido/agendamento para profissional.

Informações:

- Nome da cliente
    
- Serviço
    
- Data e horário
    
- Endereço
    
- Observações
    
- Valor
    
- Status
    

Ações:

- Aceitar pedido
    
- Recusar pedido
    
- Falar com cliente
    
- Marcar como concluído
    

Fluxos:

- “Falar com cliente” leva para <tela_29>  
    </tela_28>
    

<tela_29>  
Chat entre profissional e cliente.

Funções:

- Mensagens de texto
    
- Envio de imagens de referência
    
- Confirmação de detalhes
    
- Registro do combinado
    

Observação:  
Este chat deve ser simples na V1. O objetivo principal é facilitar alinhamento.  
</tela_29>

<regras_de_negocio>

1. O app possui dois perfis principais:
    

- Cliente
    
- Profissional
    

2. Uma cliente só pode solicitar um atendimento após:
    

- ter conta criada;
    
- informar endereço;
    
- selecionar um serviço.
    

3. Uma profissional só aparece nas buscas após:
    

- concluir cadastro;
    
- cadastrar pelo menos um serviço;
    
- informar região de atendimento;
    
- ter perfil aprovado, se houver validação manual.
    

4. O status básico dos pedidos deve ser:
    

- solicitado
    
- aceito
    
- recusado
    
- concluído
    
- cancelado
    

5. Avaliações só podem ser feitas após atendimento concluído.
    
6. Na V1, o foco deve estar em:
    

- cadastro;
    
- descoberta de profissionais;
    
- perfil profissional;
    
- solicitação de atendimento;
    
- gestão de pedidos;
    
- agenda;
    
- avaliação.
    

7. Itens como blog, viagens, IA concierge, plano TPM Pro e motor avançado de recomendação existem no conceito maior do projeto, mas não precisam entrar agora nesta primeira sprint funcional. Eles aparecem nos materiais do TPM como parte da visão ampliada do produto, mas devem ficar fora do escopo inicial para evitar dispersão.  
    </regras_de_negocio>
    

<fluxo_macro_cliente>  
<tela_0> → <tela_1> ou <tela_2> → <tela_5> → <tela_6> → <tela_8> → <tela_9> → <tela_10> → <tela_12> → <tela_15> → <tela_16>  
</fluxo_macro_cliente>

<fluxo_macro_profissional>  
<tela_0> → <tela_3> → <tela_21> → <tela_22> → <tela_23> → <tela_20> → <tela_24> / <tela_25> / <tela_26> / <tela_27>  
</fluxo_macro_profissional>

<componentes_essenciais_da_v1>

- Login e cadastro
    
- Separação entre perfil cliente e profissional
    
- Home da cliente
    
- Busca com filtros
    
- Perfil da profissional
    
- Solicitação de agendamento
    
- Tela de pedidos/agendamentos
    
- Chat simples
    
- Painel da profissional
    
- Cadastro de serviços e preços
    
- Agenda da profissional
    
- Avaliações  
    </componentes_essenciais_da_v1>
    

<fora_do_escopo_deste_sprint>

- Loja de produtos
    
- Blog e conteúdos inspiracionais
    
- Módulo de viagens
    
- Motor de IA concierge
    
- Painel analítico avançado tipo TPM Pro
    
- Programa TPM Impulsiona
    
- Selos, gamificação e campanhas especiais
    

Esses itens podem virar Sprints futuros.  
</fora_do_escopo_deste_sprint>

<entrega_esperada_apos_este_sprint>  
Ao final deste Sprint 01, devemos ter:

- mapa completo das telas;
    
- jornadas principais definidas;
    
- botões e redirecionamentos claros;
    
- regras de negócio iniciais;
    
- escopo da V1 delimitado;
    
- material pronto para ser transformado em prompt estruturado para o Lovable.  
    </entrega_esperada_apos_este_sprint>
    
