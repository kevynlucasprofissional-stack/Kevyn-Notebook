<ao_abrir>  
Animação curta do logo Neuron em fundo limpo, com sensação de produto moderno e inteligente. A animação dura poucos segundos e leva o usuário para uma checagem silenciosa de sessão. Se existir sessão válida e perfil já criado, o sistema encaminha para <tela_5>. Se existir sessão válida, mas o perfil de aluno ainda não estiver completo, encaminha para <tela_4>. Se não existir sessão, encaminha para <tela_0>. Essa abertura precisa transmitir a proposta central do produto: aprendizado simples, intuitivo, gamificado e sem ruído, com foco em uma jornada guiada baseada em pergunta simples, feedback imediato e progresso rápido.
</ao_abrir>  

<tela_0>  
Tela inicial pública do Neuron. Esta tela funciona como landing de entrada curta, não como página institucional longa. Na área principal aparecem o nome do produto, uma frase curta de valor como “Aprenda IA com microdesafios e feedback imediato”, um botão primário “Entrar”, um botão secundário “Criar conta” e, abaixo, uma prévia visual simples mostrando a lógica do produto: conceito rápido, exercício curto, feedback e progresso. O botão “Entrar” leva para <tela_1>. O botão “Criar conta” leva para <tela_2>. Se o usuário já tiver uma sessão ativa e tentar acessar esta tela por URL, o sistema redireciona automaticamente para <tela_5>. Esta tela deve ser extremamente limpa porque o Neuron não quer parecer um curso tradicional, e sim um ambiente de aprendizado com baixíssima fricção.
</tela_0>  

<tela_1>  
Tela de login. Campos de e-mail e senha, botão principal “Entrar”, link “Esqueci minha senha”, link secundário “Criar conta” e opção de retorno para <tela_0>. Ao clicar em “Entrar”, o sistema valida preenchimento mínimo, formato de e-mail e senha não vazia. Se os dados estiverem corretos e a autenticação funcionar, o sistema verifica se o perfil de aluno existe. Se o perfil estiver completo, leva para <tela_5>. Se o perfil ainda não existir ou estiver incompleto, leva para <tela_4>. O link “Esqueci minha senha” leva para <tela_3>. O link “Criar conta” leva para <tela_2>. Em caso de erro, a mesma tela exibe mensagem objetiva logo abaixo do campo ou em bloco discreto no topo, sem quebrar o fluxo: “E-mail ou senha incorretos”, “Preencha os campos obrigatórios” ou “Não foi possível entrar agora”.
</tela_1>  

<tela_2>  
Tela de cadastro. Campos mínimos de e-mail, senha e confirmação de senha, além do botão principal “Criar conta”. Abaixo, link “Já tenho conta” que leva para <tela_1>. Ao submeter, o sistema valida formato do e-mail, tamanho mínimo da senha, igualdade entre senha e confirmação e eventual aceite mínimo de termos. Se o cadastro for concluído com sucesso, o sistema cria a conta e encaminha o usuário para <tela_4>, onde será criado o perfil de aluno. Se houver exigência de confirmação por e-mail, a conta é criada, a tela mostra estado de sucesso e o botão “Ir para login” leva para <tela_1>; se o fluxo for direto com sessão iniciada, leva imediatamente para <tela_4>. O objetivo desta tela é reduzir ao máximo o tempo até a primeira lição.
</tela_2>  

<tela_3>  
Tela de recuperação de senha. Campo de e-mail e botão principal “Enviar link de recuperação”. Link “Voltar para login” leva para <tela_1>. Ao enviar, o sistema exibe confirmação simples como “Se existir uma conta com este e-mail, enviamos as instruções de recuperação”. O fluxo precisa ser seguro e não revelar se aquele e-mail existe ou não. Ao clicar no link enviado por e-mail, o usuário vai para uma variação desta mesma etapa, com campos “Nova senha” e “Confirmar nova senha”, botão “Salvar nova senha” e redirecionamento para <tela_1> após sucesso. Em caso de token expirado, mostrar estado claro e oferecer reenvio do link.
</tela_3>  

<tela_4>  
Tela de criação de perfil do aluno no primeiro acesso. Esta tela aparece logo após o cadastro ou após login bem-sucedido quando ainda não houver perfil completo. Campos essenciais: nome, nome de exibição opcional, objetivo principal com IA em formato simples de seleção como “trabalho”, “estudo”, “negócio”, “curiosidade”, e nível percebido em formato acessível como “iniciante”, “já uso um pouco”, “quero aprofundar”. Também pode haver uma pergunta curta “Quanto tempo você quer estudar por sessão?” com opções rápidas, como 2 min, 5 min, 10 min, para ajudar a personalizar o ritmo. O botão principal “Continuar” salva o perfil e leva para <tela_4a>. O botão secundário “Pular por agora”, se existir, também leva para <tela_4a>, mas o sistema cria perfil mínimo para não bloquear progresso. O aluno só tem acesso ao próprio perfil e às próprias preferências.
</tela_4>  

<tela_4a>  
Tela de onboarding guiado. Esta não deve ser um carrossel longo e cansativo. O ideal são de duas a três etapas rápidas. Na primeira, o Neuron apresenta sua lógica: aprender um conceito por vez, com microdesafio e feedback imediato. Na segunda, apresenta a trilha inicial “Engenharia de Prompt” como rota principal do MVP. Na terceira, entrega uma chamada direta para começar imediatamente e já conquistar a primeira pequena vitória. O botão principal “Começar agora” leva para <tela_4b>. Um link “Pular para dashboard” leva para <tela_5>, mas o fluxo recomendado é conduzir o usuário à primeira experiência de aprendizado o mais cedo possível, porque o valor do produto aparece na prática.
</tela_4a>  

<tela_4b>  
Tela de primeira vitória. Esta é uma microlição de ativação, ainda antes do dashboard completo. O topo mostra algo como “Vamos aprender em menos de 1 minuto”. Surge o texto: "o que é prompt engineering e por que a forma de pedir altera a qualidade da resposta?". Em seguida, aparece um microexercício simples: A aparece um botão clicável com o texto “Me fale sobre marketing”, e um momento depois aparece em baixo deste um novo botão clicável com o texto “Explique marketing digital para iniciantes em 5 passos com exemplos práticos”, mais um momento depois abaixo dos dois botões aparece o texto "Qual prompt você acha que tende a gerar a melhor resposta?". Ao clicar no botão “Explique marketing digital para iniciantes em 5 passos com exemplos práticos”, o sistema mostra feedback imediato, reforça a lógica de instrução clara e mostra um microestado de progresso, como “1ª vitória conquistada”. Se o usuário clicar no botão "Me fale sobre marketing", a botão treme e fica vermelho enquanto o botão “Explique marketing digital para iniciantes em 5 passos com exemplos práticos” fica verde. O botão “Ir para meu dashboard” leva para <tela_5>. Este ponto implementa diretamente a lógica do product loop: curiosidade, desafio rápido, feedback imediato e pequena vitória.
</tela_4b>  

<tela_5>  
Dashboard logado. Esta é a tela inicial principal do aluno autenticado. No topo aparece uma saudação curta, um bloco de progresso geral, o card “Continuar aprendendo” apontando exatamente para a próxima lição disponível do usuário e um indicador de sequência diária, se houver ao menos uma lição concluída. Abaixo fica a seção de trilhas disponíveis; no MVP, apenas a trilha “Engenharia de Prompt” deve aparecer como trilha principal, em destaque visual. Também existe um card ou ícone minimalista “Seja Premium”, sempre visível em posição discreta e elegante, levando para <tela_11>. Na mesma tela pode haver um resumo do plano atual, como Free ou Premium, e um atalho para perfil no canto superior direito, levando para <tela_15>. Se o usuário tocar na trilha de Engenharia de Prompt, vai para <tela_6>. Se tocar em “Continuar aprendendo”, vai direto para a próxima lição disponível em <tela_8>. Se tocar em “Seja Premium”, vai para <tela_11>. O dashboard precisa mostrar progresso visível e sensação de avanço sem parecer complexo.
</tela_5> 

<tela_5_estado_vazio>  
Variação do dashboard para usuário sem progresso. O card principal não mostra “Continuar aprendendo”, e sim “Começar trilha”. A seção de progresso exibe zero concluído, a streak ainda não existe e a trilha de Engenharia de Prompt aparece com CTA principal “Iniciar”. O objetivo aqui é empurrar o primeiro passo com clareza máxima. A ação principal leva para <tela_6>.
</tela_5_estado_vazio>  

<tela_5_estado_progresso>  
Variação do dashboard para usuário com progresso em andamento. O card principal mostra exatamente onde ele parou, por exemplo “Continuar no módulo 2, lição 3”. O percentual da trilha, a barra de módulo atual e a sequência aparecem já preenchidos. O CTA leva para <tela_8> na lição correta. O loop aqui é retomar sem pensar.
</tela_5_estado_progresso>  

<tela_5_estado_premium>  
Variação do dashboard para usuário premium. O card “Seja Premium” deixa de ser CTA de aquisição e vira um selo discreto como “Premium ativo”, que ao ser clicado leva para <tela_14> de gerenciamento de assinatura. Nenhum texto de anúncio aparece na jornada.
</tela_5_estado_premium>  

<tela_6>  
Tela da trilha “Engenharia de Prompt”. Esta tela apresenta visão geral da trilha, descrição curta, total de módulos, progresso do usuário, tempo médio por lição e status da trilha, como “não iniciada”, “em andamento” ou “concluída”. Abaixo aparece a lista de módulos em ordem. Cada módulo mostra nome, objetivo, quantidade de lições, percentual concluído e estado de bloqueio ou desbloqueio. O primeiro módulo fica liberado desde o início. Os demais aparecem bloqueados até a conclusão do módulo anterior. O botão principal no topo muda conforme o estado: “Iniciar trilha”, “Continuar trilha” ou “Revisar trilha”. “Iniciar” leva para a primeira lição do primeiro módulo em <tela_8>. “Continuar” leva para a próxima lição disponível do usuário. Ao tocar em um módulo desbloqueado, vai para <tela_7>. Ao tocar em módulo bloqueado, o sistema exibe microinteração explicando “Conclua o módulo anterior para desbloquear”. Esta tela precisa deixar muito visível o avanço, porque o desbloqueio é parte central do engajamento.
</tela_6>  

<trilha_prompt_engineering>  
A trilha de Engenharia de Prompt é a rota inicial e principal do MVP. Ela deve ser reorganizada pedagogicamente a partir dos temas do livro “The Art of Asking ChatGPT for High-Quality Answers”, em vez de simplesmente copiar a ordem dos capítulos. O livro apresenta fundamentos de prompt engineering, fórmula com task, instructions e role, além de técnicas como instructions prompting, role prompting, standard prompts, zero-shot, one-shot, few-shot, “let’s think about this”, self-consistency, seed-word, knowledge generation, knowledge integration, multiple choice, interpretable soft prompts, controlled generation, question-answering, summarization, dialogue, adversarial, clustering, reinforcement learning, curriculum learning, sentiment analysis, named entity recognition, text classification e text generation. O Neuron transforma isso em uma jornada progressiva, curta e prática, pensada para sessões rápidas com feedback imediato.
</trilha_prompt_engineering>

<tela_7>
Módulos da Trilha de Prompt Engineering

Tela de módulo da trilha. Ao entrar em um módulo desbloqueado, o usuário vê:

- nome do módulo
    
- objetivo do módulo
    
- breve introdução explicando o conceito principal
    
- lista de lições
    
- barra de progresso do módulo
    

Cada lição mostra:

- título da lição
    
- duração estimada curta (2 a 4 minutos)
    
- estado: **não iniciada**, **em andamento** ou **concluída**
    
- ícone de checkpoint
    

No topo aparece o botão principal:

**Começar módulo** ou **Continuar módulo**

Esse botão leva para a primeira ou próxima lição em `<tela_8>`.

Ao clicar em uma lição concluída, o usuário pode revisitar em **modo revisão**.

Ao clicar em uma lição futura:

- se progressão linear → bloqueado
    
- se progressão flexível → permitido
    

Para o MVP do Neuron:

**apenas a próxima lição é liberada**, garantindo ritmo didático e progressão clara.

<modulo_1>

### Fundamentos do Prompt

Objetivo do módulo:  
fazer o aluno entender que **a qualidade da resposta depende da forma como a pergunta é formulada**.

Introdução:

Prompt engineering é a habilidade de estruturar pedidos para que a IA gere respostas úteis e relevantes.

Todo prompt possui três elementos fundamentais:

- **Task**
    
- **Instructions**
    
- **Role**
    

### Lições

**Lição 1 — O que é Prompt Engineering**

Mostra como perguntas vagas produzem respostas vagas.

Exemplo comparativo:

Prompt ruim  
"Explique marketing."

Prompt melhor  
"Explique marketing digital para iniciantes em 5 passos simples."

**Exercício**

Escolher qual prompt gera melhor resposta.

A  
Explique marketing

B  
Explique marketing digital para iniciantes em 5 passos com exemplos

Resposta correta: B

Feedback:  
Prompts claros produzem respostas mais úteis.

---

**Lição 2 — Task**

Explica que a **task define o que precisa ser feito**.

Exemplo:

"Liste 5 ideias de negócios online."

Exercício:

O aluno deve identificar qual parte do prompt é a task.

---

**Lição 3 — Instructions**

Instructions definem **como a resposta deve ser gerada**.

Exemplo:

"Explique blockchain em linguagem simples."

Exercício:

Adicionar instructions ao prompt:

Prompt base  
Explique inteligência artificial

Resposta esperada  
Explique inteligência artificial em linguagem simples para iniciantes em 5 passos.

---

**Lição 4 — Role**

Role define **quem está respondendo**.

Exemplo:

"Como professor de marketing, explique funil de vendas."

Exercício:

Adicionar um papel ao prompt.

Prompt base  
Explique liderança

Resposta esperada  
Como especialista em liderança, explique liderança em 5 princípios práticos.

---

**Lição 5 — Combinando Task + Instructions + Role**

Exemplo final:

"Como especialista em marketing digital, explique funil de vendas para iniciantes em 5 passos simples."

Exercício do módulo:

Reescrever **3 prompts ruins** transformando-os em prompts claros.

Critério de avaliação:

- clareza
    
- especificidade
    
- adequação do papel
    

Critério de conclusão:

- concluir todas as lições
    
- enviar ao menos **1 resposta válida por exercício**
    

<modulo_2>

### Instructions que melhoram respostas

Objetivo:

ensinar **instructions prompting**, técnica que controla o formato e qualidade da resposta.

### Lições

1 — Instruções específicas melhoram respostas  
2 — Formatos de saída (lista, passos, resumo)  
3 — Restrições (tamanho, público, objetivo)  
4 — Combinar instructions com role  
5 — Caso prático

Exemplo:

"Explique funil de vendas para pequeno empreendedor em 5 passos com exemplo prático."

### Exercício

Transformar pedido amplo em pedido com instruções claras.

Prompt inicial:

Explique produtividade

Resposta esperada:

Explique produtividade para estudantes em 5 dicas práticas.

Feedback aponta:

- falta de público
    
- falta de formato
    
- falta de restrições
    

Conclusão do módulo:

o aluno demonstra que sabe **controlar a saída da IA usando instruções claras**.

<modulo_3>

### Perspectiva e contexto com papéis

Objetivo:

ensinar **role prompting** para orientar respostas por especialidade ou perspectiva.

### Lições

1 — O que é role prompting  
2 — Quando o papel ajuda e quando é irrelevante  
3 — Combinar role + instructions  
4 — Combinar role + task + seed word  
5 — Comparar respostas com papéis diferentes

### Exercício

Criar três prompts diferentes para o mesmo tema:

Tema: marketing digital

Versão 1  
Como professor explique marketing digital

Versão 2  
Como copywriter explique marketing digital

Versão 3  
Como consultor estratégico explique marketing digital

Feedback verifica:

- coerência do papel
    
- adequação ao objetivo
    

Conclusão:

o aluno demonstra que sabe usar papel **como contexto funcional**.

<modulo_4>

### Estruturas básicas de prompting

Objetivo:

ensinar as estruturas:

- standard prompts
    
- zero-shot
    
- one-shot
    
- few-shot
    

### Lições

1 — Standard prompt  
2 — Zero-shot prompting  
3 — One-shot prompting  
4 — Few-shot prompting  
5 — Escolher a técnica correta

### Exercício

O aluno recebe cenários e deve escolher a técnica correta.

Exemplo:

Classificar sentimento de texto.

Com exemplos fornecidos.

Resposta esperada:

**few-shot prompting**

Feedback analisa:

adequação entre tarefa e técnica.

<modulo_5>

### Raciocínio guiado e consistência

Objetivo:

ensinar técnicas para melhorar raciocínio da IA.

Técnicas:

- Let's Think About This
    
- Self-consistency
    

### Lições

1 — Pensar passo a passo  
2 — Decomposição de problemas  
3 — Verificação de coerência  
4 — Revisão automática  
5 — Combinação das técnicas

### Exercício

Melhorar prompt confuso:

Prompt inicial  
Explique por que empresas falham.

Resposta esperada:

Vamos pensar passo a passo por que empresas falham.

Depois adicionar:

Revise a resposta e verifique inconsistências.

Feedback avalia:

- organização lógica
    
- presença de etapa de revisão
    

<modulo_6>

### Ampliação semântica e geração de conhecimento

Objetivo:

ensinar técnicas de expansão de ideias.

Técnicas:

- seed word prompting
    
- knowledge generation
    
- knowledge integration
    

### Lições

1 — Seed word  
2 — Gerar conhecimento  
3 — Integrar conhecimento  
4 — Conectar ideias  
5 — Aplicação prática

### Exercício

Seed word:

retenção

Passo 1  
gerar ideias sobre retenção

Passo 2  
integrar ideias ao cenário:

SaaS educacional

Feedback avalia:

- foco
    
- relevância
    
- capacidade de integração
    


<modulo_7>

### Controle de saída e formatos úteis

Objetivo:

ensinar prompts orientados a **formato e utilidade prática**.

Técnicas:

- multiple choice prompts
    
- controlled generation
    
- question answering
    
- summarization
    
- dialogue prompting
    

### Lições

1 — Respostas em alternativas  
2 — Controle de geração  
3 — Pergunta e resposta  
4 — Resumos  
5 — Diálogo iterativo

### Exercício

Receber texto longo.

Passo 1  
gerar resumo para iniciante

Passo 2  
criar três perguntas úteis

Passo 3  
transformar em diálogo educativo

Feedback verifica:

- utilidade
    
- clareza
    
- formato
    

<modulo_8>

### Análise e classificação com IA

Objetivo:

mostrar aplicações analíticas de prompting.

Técnicas:

- clustering
    
- sentiment analysis
    
- named entity recognition
    
- text classification
    

### Lições

1 — Agrupamento por semelhança  
2 — Análise de sentimento  
3 — Reconhecimento de entidades  
4 — Classificação de textos  
5 — Escolha da técnica

### Exercício

Receber comentários de clientes.

Tarefas:

- classificar sentimento
    
- identificar entidades
    
- separar comentários por tema
    

Feedback verifica:

clareza do critério de classificação.


<modulo_9>

### Geração avançada e robustez

Objetivo:

introduzir repertório avançado de prompting.

Técnicas:

- text generation
    
- adversarial prompts
    
- interpretable soft prompts
    
- reinforcement learning prompts
    
- curriculum learning prompts
    

### Lições

1 — Geração controlada de texto  
2 — Prompts adversariais  
3 — Soft prompts (visão conceitual)  
4 — Aprendizado por feedback  
5 — Estrutura progressiva de prompts

### Exercício

Criar prompt robusto para resolver problema complexo.

Critérios:

- clareza
    
- controle
    
- revisão
    
- robustez
    


<modulo_10>

### Projeto final da trilha

Objetivo:

consolidar todas as técnicas aprendidas.

### Lições

1 — Caso profissional  
2 — Caso de estudo  
3 — Caso criativo  
4 — Revisão guiada do prompt  
5 — Desafio final

### Exercício final

Criar um prompt completo contendo:

- task clara
    
- instructions específicas
    
- role adequado
    
- técnica estrutural (zero/one/few-shot)
    
- seed word
    
- etapa de revisão
    

Feedback final mostra:

- pontos fortes
    
- melhorias
    
- evolução do aluno
    

Ao concluir o módulo:

a trilha inteira é marcada como **concluída**

Usuário é levado para <tela_10>
</tela_7>

<tela_8>  
Tela de lição. Esta é a tela mais importante do produto. O topo mostra progresso global da trilha, progresso do módulo atual, nome da trilha, nome do módulo e título da lição. Abaixo, em blocos curtos, aparecem: conceito rápido, explicação objetiva, exemplo de prompt, exercício e área de envio. Cada lição precisa parecer curta, vencível e recompensadora. O conteúdo nunca deve parecer um capítulo longo de curso. O bloco de conceito apresenta uma explicação em linguagem simples. O bloco de exemplo mostra um prompt bom e, quando fizer sentido, compara com uma versão ruim. O bloco de exercício pode ser de múltipla escolha, reescrita, completar prompt ou escrever um prompt do zero. O botão principal “Enviar resposta” ativa a avaliação e leva para o estado de feedback dentro da própria tela, ou para <tela_9> se a implementação preferir separar. Há também um botão secundário “Voltar ao módulo” que leva para <tela_7>. Se o usuário sair antes de concluir, a lição fica como “em andamento”. Se ele concluir, o sistema salva progresso imediatamente.
</tela_8>  

<tela_8_microinteracoes>  
Na digitação do exercício, a UI pode mostrar dicas leves, como contador de caracteres, lembrete de clareza e pequenos chips de apoio como “defina o objetivo”, “diga para quem é”, “especifique o formato”. Essas ajudas não devem parecer correção prematura, mas assistência. Se a lição for de múltipla escolha, ao tocar numa alternativa a seleção fica clara, porém o feedback só vem ao enviar. Se a lição for de escrita livre, o botão “Enviar resposta” só habilita quando houver conteúdo mínimo. Esta tela deve sempre reforçar a sensação de que aprender é agir, não apenas ler.
</tela_8_microinteracoes>  

<tela_9>  
Estado de feedback imediato da lição. Assim que o usuário envia a resposta, o sistema avalia conforme critérios da lição. O feedback mostra, de forma curta e útil, se o prompt enviado está forte, razoável ou fraco, e por quê. Em vez de só dizer “certo” ou “errado”, o sistema deve destacar dimensões como clareza da tarefa, presença de instruções, adequação do papel, especificidade, utilidade do formato e potencial de melhoria. Também deve sugerir uma melhoria pontual, por exemplo “faltou dizer para quem a resposta é” ou “você definiu o papel, mas não disse qual formato quer na saída”. Se a resposta estiver boa, a tela reforça a pequena vitória com mensagem curta como “Boa. Seu prompt já direciona melhor a IA” ou “Você deixou o pedido mais claro e útil”. Se a resposta estiver fraca, a mensagem deve incentivar sem punir, oferecendo botão “Melhorar e tentar de novo” e mostrando uma dica. O botão principal muda conforme o caso: “Próxima lição” se concluída, ou “Refinar resposta” se o sistema quiser exigir uma segunda tentativa. “Próxima lição” leva para a próxima <tela_8> ou, se a lição concluída for a última do módulo, leva para <tela_10a>.
</tela_9>  

<tela_9_logica_feedback>  
A lógica mínima do feedback precisa estar vinculada à resposta enviada pelo usuário. Mesmo que o MVP use IA para gerar texto de feedback, a estrutura da avaliação deve seguir critérios estáveis da lição. Em uma lição sobre instructions prompting, o sistema precisa procurar se o usuário explicitou instruções. Em uma lição sobre role prompting, precisa verificar se o papel escolhido é coerente. Em uma lição sobre zero-shot versus few-shot, precisa avaliar se a técnica selecionada faz sentido para a tarefa. O feedback automatizado pode ser suportado por IA, mas o estado de conclusão da lição deve depender de regras claras.
</tela_9_logica_feedback>  

<tela_9_anuncio_free>  
Se o usuário estiver no plano free e concluir uma lição, após o feedback concluído aparece um anúncio curto e bem delimitado antes da transição final para a próxima lição ou para a conclusão do módulo. Esse anúncio pode surgir em uma etapa intermediária simples, com botão “Continuar” habilitado ao final da exibição mínima. O anúncio só deve aparecer ao final de lições, nunca interrompendo a leitura do conceito ou a execução do exercício. Se o usuário for premium, essa etapa não existe e o fluxo segue direto.
</tela_9_anuncio_free>  

<tela_10a>  
Tela de conclusão de módulo. Ao concluir a última lição de um módulo, o usuário vê uma celebração curta e elegante, com o nome do módulo concluído, percentual total da trilha atualizado, resumo do que aprendeu e destaque para o próximo módulo agora desbloqueado. O botão principal “Ir para próximo módulo” leva para <tela_7> do módulo recém-liberado ou direto para sua primeira lição em <tela_8>. O botão secundário “Revisar módulo” leva para <tela_7> do módulo concluído. Esta tela precisa materializar o loop de progressão: completar lição, completar módulo, desbloquear próximo, avançar.
</tela_10a>  

<tela_10>  
Tela de conclusão da trilha. Ao terminar todos os módulos, o usuário vê uma tela com sensação de conquista real. Aparecem o nome da trilha concluída, uma síntese do que agora ele é capaz de fazer, porcentagem final 100%, total de lições concluídas e um selo visual de trilha concluída. O botão principal “Voltar ao dashboard” leva para <tela_5>. O botão secundário “Revisar trilha” leva para <tela_6>. Se existirem trilhas futuras bloqueadas por roadmap, a tela pode mostrar um teaser discreto “Novas trilhas em breve”. Se o usuário ainda for free, essa tela também pode trazer uma chamada delicada para o premium, mas sem poluir o momento de vitória.
</tela_10>  

<tela_11>  
Tela de benefícios do Premium. Esta tela é acessada pelo dashboard, pela área de perfil ou por pontos contextuais suaves ao longo do produto. No topo, o usuário vê o título “Seja Premium” e uma frase de valor direta. Abaixo aparece comparação clara entre Free e Premium. No Free, o usuário aprende normalmente, mas vê anúncios ao final das lições. No Premium, não há anúncios, a experiência é mais fluida e o status da conta fica atualizado no perfil. Se houver futuros benefícios planejados, eles podem ser listados como “em breve”, mas o MVP deve ser honesto: o benefício central é remoção de anúncios. O botão principal “Assinar Premium” leva para <tela_12>. O botão secundário “Agora não” retorna para <tela_5> ou para a tela anterior. Se o usuário já for premium, esta tela muda o estado e mostra “Seu Premium está ativo”, com botão para gerenciar assinatura em <tela_14>.
</tela_11>  

<tela_12>  
Tela de seleção e confirmação de plano. O usuário vê plano mensal ou anual, se ambos existirem; se o MVP tiver apenas um plano, a tela mostra esse plano único de forma objetiva. Cada opção mostra preço, período e benefício central. O botão principal “Continuar para pagamento” leva para <tela_13>. O botão “Voltar” retorna para <tela_11>. O sistema só permite este fluxo para usuários autenticados. O estado visual deve ser simples, sem excesso de comparações comerciais, mantendo coerência com a sofisticação minimalista do produto.
</tela_12>  

<tela_13>  
Tela de pagamento e processamento da assinatura. Aqui o sistema integra checkout seguro, como Stripe. O usuário confirma o plano, informa pagamento ou é redirecionado ao ambiente seguro do provedor. Se o pagamento for aprovado, o sistema atualiza o status no backend e leva para <tela_13a>. Se o pagamento falhar, leva para <tela_13b>. Se o usuário desistir, retorna para <tela_11> sem alterar status. A assinatura nunca deve depender de alteração insegura no frontend; o status premium precisa ser validado por backend.
</tela_13>  

<tela_13a>  
Tela de sucesso da assinatura. Mensagem principal “Premium ativado”. A tela informa que os anúncios foram removidos e que o novo status já está refletido na conta. O botão principal “Voltar ao dashboard” leva para <tela_5_estado_premium>. O botão secundário “Ver assinatura” leva para <tela_14>. Esta tela também pode mostrar uma pequena animação de conquista, mas sem parecer festiva demais a ponto de perder elegância.
</tela_13a>  

<tela_13b>  
Tela de falha de pagamento. Esta tela explica de forma direta que não foi possível concluir a assinatura. O botão principal “Tentar novamente” leva de volta para <tela_13>. O botão secundário “Voltar aos planos” leva para <tela_12>. O status da conta permanece Free. O texto não deve culpar o usuário; apenas indicar que pode haver problema no cartão, na conexão ou no provedor.
</tela_13b>  

<tela_14>  
Tela de gerenciamento de assinatura. Nesta tela o usuário vê status atual, tipo do plano, data de renovação ou expiração e ações disponíveis, como “Atualizar pagamento” se houver, “Cancelar assinatura” ou “Reativar”, conforme o provedor suportar. Se a assinatura estiver ativa, o estado mostra “Premium ativo”. Se estiver cancelada, mas ainda válida até o fim do período, mostrar “Cancelada, ativa até X”. Se estiver expirada, mostrar “Free” e CTA “Assinar novamente”, levando para <tela_11>. O botão “Voltar ao perfil” leva para <tela_15>.
</tela_14>  

<tela_15>  
Tela de perfil do aluno. O topo mostra foto ou avatar opcional, nome, nível atual da jornada e status do plano. Abaixo aparecem progresso geral, trilhas iniciadas, trilhas concluídas e atalho para continuar aprendendo. Também aparecem seções “Minhas trilhas”, “Meu progresso” e “Configurações”. Tocar em “Meu progresso” pode rolar a própria tela ou abrir um detalhamento em <tela_15a>. Tocar em “Configurações” leva para <tela_16>. Tocar em “Assinatura” leva para <tela_14>. Tocar em uma trilha iniciada leva para <tela_6>. Esta tela precisa fazer o usuário sentir posse da jornada.
</tela_15>  

<tela_15a>  
Detalhamento de progresso. Mostra a trilha de Engenharia de Prompt com percentual total, módulos concluídos, lições concluídas, lição atual e, se fizer sentido, sequência diária. Também pode mostrar histórico simples como “última atividade” e “tempo médio por sessão”. O botão “Continuar aprendendo” leva para <tela_8> da próxima lição. O botão “Voltar ao perfil” leva para <tela_15>.
</tela_15a>  

<tela_16>  
Tela de configurações. Aqui ficam ações do usuário: editar perfil, alterar senha, preferências básicas e sair da conta. “Editar perfil” leva para <tela_16a>. “Alterar senha” leva para <tela_16b>. “Gerenciar assinatura” leva para <tela_14>. “Sair da conta” encerra a sessão e leva para <tela_0>. Preferências básicas podem incluir notificações de aprendizado, lembrete diário, idioma de interface se houver e duração preferida de sessão. O design desta tela precisa ser simples e administrativo, sem perder a linguagem do produto.
</tela_16>  

<tela_16a>  
Tela de edição de perfil. Permite alterar nome, objetivo com IA, nível percebido e preferências leves de estudo. O botão “Salvar alterações” retorna para <tela_15> com confirmação discreta. O botão “Cancelar” retorna para <tela_16>. O usuário só pode editar o próprio perfil.
</tela_16a>  

<tela_16b>  
Tela de alteração de senha. Campos “senha atual”, “nova senha” e “confirmar nova senha”. O botão “Salvar nova senha” valida e atualiza. Em caso de sucesso, retorna para <tela_16> com confirmação. Em caso de erro, exibe orientação objetiva na própria tela.

<estado_primeiro_acesso>  
No primeiro acesso, o sistema deve encadear <tela_4> para <tela_4a> e depois <tela_4b>, evitando jogar o usuário diretamente em um dashboard vazio. A lógica é entregar valor antes de pedir exploração livre. Isso está alinhado ao conceito do Neuron como aprendizado rápido, guiado e intuitivo.  
</estado_primeiro_acesso>

<estado_usuario_sem_progresso>  
Se o aluno não tiver nenhuma lição concluída, o dashboard exibe CTA forte de início, a trilha aparece com status “não iniciada” e o perfil mostra progresso zero sem parecer punitivo. O foco é empurrar a primeira sessão curta.  
</estado_usuario_sem_progresso>

<estado_usuario_com_progresso>  
Se houver progresso em andamento, o sistema sempre prioriza retomada. O botão “Continuar aprendendo” deve ser o elemento mais visível do dashboard e do perfil.  
</estado_usuario_com_progresso>

<estado_usuario_free>  
O usuário free tem acesso normal à trilha do MVP, vê o card “Seja Premium” no dashboard e anúncios ao final de cada lição concluída. Em nenhum momento o free deve parecer um usuário de segunda categoria; ele apenas tem uma camada de fricção monetizada ao fim das lições.  
</estado_usuario_free>

<estado_usuario_premium>  
O usuário premium vê remoção total de anúncios, status refletido no dashboard e no perfil, e acesso mais fluido entre feedback e próxima lição.  
</estado_usuario_premium>

<estado_modulo_bloqueado>  
Módulos futuros aparecem visualmente bloqueados, com opacidade reduzida e ícone de cadeado. Ao tocar, o sistema explica o requisito de desbloqueio. Isso precisa gerar desejo de avanço, não frustração.  
</estado_modulo_bloqueado>

<estado_licao_concluida>  
Lição concluída recebe marca visual de checkpoint e pode ser revisitada. O sistema atualiza progresso imediatamente e aponta a próxima ação disponível.  
</estado_licao_concluida>

<estado_erro_login>  
Se login falhar, permanecer em <tela_1>, preservar o e-mail já digitado e mostrar mensagem objetiva. Nunca limpar os campos sem necessidade.  
</estado_erro_login>

<estado_recuperacao_senha>  
Se a recuperação for solicitada com sucesso, manter linguagem neutra e segura. Se o link expirar, oferecer nova solicitação sem ruído.  
</estado_recuperacao_senha>

<estado_falha_pagamento>  
Se pagamento falhar, o sistema não muda o plano do usuário e oferece retry simples. O retorno ao aprendizado deve ser sempre possível.  
</estado_falha_pagamento>

<estado_assinatura_cancelada_ou_expirada>  
Se a assinatura for cancelada ou expirar, o status premium some do dashboard e do perfil, o usuário volta ao plano free e os anúncios reaparecem ao final das lições futuras. Esse retorno de estado deve ser refletido imediatamente pelo backend.  
</estado_assinatura_cancelada_ou_expirada>

<regra_negocio>  
Todo usuário do MVP é um aluno; existe autenticação para áreas internas; cada usuário possui um único perfil de aluno; o dashboard mostra trilhas disponíveis; no MVP só existe a trilha Engenharia de Prompt; trilhas possuem módulos; módulos possuem lições; lições possuem conteúdo, exercício e feedback; o progresso é salvo por usuário; o usuário continua de onde parou; módulos podem ser desbloqueados conforme avanço; free vê anúncios; premium não vê anúncios; assinatura é validada por backend seguro; o aluno edita apenas o próprio perfil e o próprio progresso; a área administrativa não é editável pelo aluno.  
</regra_negocio>

<fluxo_principal>  
Abrir app leva à checagem de sessão. Sem conta, o usuário entra por cadastro ou login. Após autenticação, cria perfil de aluno. Em seguida, o onboarding mostra a lógica do produto e oferece uma primeira pequena vitória. Depois disso, o usuário cai no dashboard, entra na trilha de Engenharia de Prompt, acessa um módulo, faz uma lição, recebe feedback imediato, conclui a lição, avança, conclui módulos, desbloqueia novos módulos e completa a trilha. Paralelamente, o loop de monetização aparece pelo card “Seja Premium” e pelos anúncios ao final das lições do plano free. O fluxo inteiro deve sempre reforçar curiosidade, desafio rápido, feedback imediato, pequena vitória, progresso visível, desbloqueio e retorno diário.  
</fluxo_principal>

<observacao_final_de_produto>  
O Neuron precisa parecer menos uma plataforma de curso e mais uma máquina de progresso. Cada sessão idealmente entrega um conceito, um exercício e uma pequena vitória em poucos minutos. Esse é o centro do sprint, da navegação e da trilha de Prompt Engineering.  
</observacao_final_de_produto>
</tela_16b>  