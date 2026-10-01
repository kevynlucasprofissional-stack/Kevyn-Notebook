---
Modificado:
  - Monday 61 02/03/2026
Criado: Monday 61 02/03/2026
---
Preciso de um prompt para o lovable e se necessario o script SQL para realizar os seguintes ajustes descritos abaixo

1. Tem que dar um jeito de nao confundir as marcas de caneta vermelha ou de outras cores com crescimento de colonia (vulgo UFC), para isso talvez seja interessante ajustar o system prompt da IA que faz a analise final da placa de petri e garantir que la tenha um aviso sobre observar duas vezes para garantir que conseguiu diferenciar o que e UFC do que e apenas marca de caneta.

2. No dashboard foi criado um botao que facilita a copiar o codigo de acesso, mas ele nao esta intuitivo, no sentido que a funcao dele nao esta totalmente clara, entao precisamos ajustar. Ao inves de ser como esta, poderiamos colocar algo como Copiar `Codigo de Acesso para este laboratorio` e nao precisar exibir o codigo, mas que quando o botao fosse clicado o codigo fosse copiado, ou algo parecido com isso, nao tenho absoluta certeza entao aceito sugestoes de como fazer isso de uma forma que o usuario nao precise de tantas instrucoes para entender como isso funciona. Somente o ADM do laboratorio pode ter acesso ao botao de copiar codigo de acesso, e os codigos de acesso nao devem ficar visiveis na tela de selecao de laboratorio.

3. Na parte de upload de documentos do BioVision em vez de ser `Metodologia de Analise` coloque `PDF da Metodologia`

4. No historico de analises e necessario aparecer tambem o historico de analises do BioVision, e tambem quero que remova a coluna de acao e coloque uma funcao de que ao clicar em qualquer lugar da linha o usuario e encaminhado para a respectiva analise. Quero que funda o painel de historico do BioVision com o painel de historico geral de analises. Quero que ao passar o mouse em cima de uma linha de analise ele fique levemente azulado indicando que e clicavel. Neste novo painel de historico unificado sera necessario que nas linhas seja identificado se a analise foi feita pela BioVision ou se foi inserida por um colaborador (no caso da segunda opcao tem que mostrar o nome do colaborar e sua funcao). No caso das analises do BioVision tem que mostrar se foi concluido ou se ficou so no rascunho, se esta conforme ou nao e a qualidade da foto da placa de petri.

5. Quero que o chat final do BioVision onde o usuario ve a analise final da placa de petri feita pelo BioVision, na parte do bloco `Foto` onde mostra a foto da placa e a nota, preciso que nessa parte tenha alem da nota uma explicacao de com quais parametros a foto foi analisada, a justificativa da nota e uma dica para alcancar nota 10 nas proximas fotos (a dica para alcancar nota 10 deve ser entregue apenas se a nota atual da foto nao for 10). Nessa mesma tela preciso que alem de ter um chat com a IA tenha um chat da amostra para os colaboradores conversarem entre si ou deixarem comentarios, isso pode ser logo abaixo do chat com o `Consultor Tecnico de Bancada`, este chat deve ser parecido com aquele disponivei na tela de detalhes e resultados da analise, la tem um bloco chamado `chat da amostra` quero que seja parecido com este. Ainda nessa tela do resultado final, o `consultor tecnico de bancada` deve usar um padrao de disparos de mensagens iniciais, este padrao esta no anexo com fundo escuro com a frase `modelo padrao de mensagem inicial do chat que vai abrir aqui`. Ainda nesta tela, ao lado do botao `reanalizar` deve ter um botao `Baixar PDF` que ira salvar na pasta de downloads do computador do usuario o pdf com o resultado completo da analise do BioVision. Ainda nesta tela, deve ser inserido um bloco escrito `Avalie este resultado` que fica abaixo no canto inferior direito abaixo do chat novo que sera inserido, deve ser interativo sera um pedido assim `Avalise este resultado` e logo abaixo 5 estrelas vazias que interagem com o mouse e se o usuario clica em uma das estrelas para avaliar o chat deve abrir um bloco onde o usuario podera digitar um comentario sobre a sua avaliacao, neste bloco novo que abrira deve ter escrito em cinza `Otimo, poderia por gentileza comentar sobre a sua avaliacao` dentro do bloco e este texto some quando o usuario comeca a digitar no bloco, alem disso ao clicar na estrela junto deste bloco do comentario tambem deve aparece o botao de enviar avaliacao, e quando o usuario clica neste botao todo o bloco de avaliacao fica verde com o escrito `obrigado por avaliar` e um botao pequeno embaixo escrito `editar avaliacao` e este feedbac deve ser armazenado para consulta pelos administradores posteriormente, entao deve ser criado uma tabela no bacend que indica o ID da analise, a nota em estrelas e o feedbac por escrito do usuario.

6. Deve ser criado um acesso para os administradores no qual eles terao acesso aos feedbacs dos usuarios, o login `adm@biovision.com` e senha `@microbiologia5.0` da acesso a um painel que mostra o feedbac de todos os usuarios coletados ao final dos resultados do BioVision.

7. O responsavel tecnica precisa ter acesso apenas a funcao de cadastrar amostra e dizer quais os testes daquela amostra e ao botao para adicionar novos testes e novas amostras. O tecnico tambem precisa conseguir acompanhar os resultados que o analista coloca em tempo real, e talvez isso meio que ja e feito pelo chat da amostra. E o analista precisa ter acesso as amostras que foram cadastradas e quais testes vao ser daquelas amostras. Precisamos separar as telas que as funcoes do responsavel tecnico e do analista tem acesso. O analista nao pode ter acesso as telas de cadastro de amostra quimica e microbiologica. Todos podem ter acesso ao BioVision.
   
   ## SQL

-- 1. Tabela para armazenar feedbacks das análises BioVision
CREATE TABLE IF NOT EXISTS biovision_feedbacks (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    run_id UUID REFERENCES biovision_runs(id) ON DELETE CASCADE,
    rating INT CHECK (rating >= 1 AND rating <= 5),
    comment TEXT,
    created_at TIMESTAMPTZ DEFAULT NOW()
);

-- 2. Remover a view antiga
DROP VIEW IF EXISTS lab_history;

-- 3. Criar a view de histórico unificado com lógica de cargo (RT vs Analista)
CREATE OR REPLACE VIEW lab_history AS
SELECT 
    s.id, 
    s.lab_id, 
    s.created_at, 
    'sample'::text as type, 
    ('Amostra: ' || s.code)::text as title, 
    s.validation_status::text as status,
    -- Lógica baseada na coluna is_admin do seu CSV
    (p.full_name || ' (' || (CASE WHEN lm.is_admin THEN 'Responsável Técnico' ELSE 'Analista' END) || ')')::text as author_info,
    s.sample_type::text as sub_title,
    NULL::text as result_value,
    NULL::text as photo_quality
FROM samples s
LEFT JOIN lab_members lm ON s.lab_id = lm.lab_id AND s.analyst_id = lm.user_id
LEFT JOIN profiles p ON lm.user_id = p.id

UNION ALL

SELECT 
    br.id, 
    br.lab_id, 
    br.created_at, 
    'biovision'::text as type, 
    ('Análise BioVision: ' || COALESCE(br.analysis_type, 'Geral'))::text as title, 
    COALESCE(br.ai_analysis_status, 'rascunho')::text as status,
    'BioVision AI'::text as author_info,
    COALESCE(br.matrix_type, 'Microbiologia')::text as sub_title,
    br.cfu_count::text as result_value,
    br.image_quality_score::text as photo_quality
FROM biovision_runs br;

-- 4. Habilitar segurança para respeitar o isolamento por laboratório
ALTER VIEW lab_history SET (security_invoker = on);

## Prompt Lovable

Preciso implementar uma série de ajustes técnicos e de interface conforme os requisitos abaixo:

### 1. Inteligência Artificial e Precisão (Prompt Gemini)
- Ajuste o System Prompt da análise BioVision: "Ao analisar a placa de petri, execute uma verificação dupla para distinguir o crescimento biológico (UFC) de marcas de caneta (geralmente traços ou círculos vermelhos/azuis no fundo da placa). Marcas de caneta devem ser ignoradas. Foque apenas na morfologia das colônias."

### 2. Dashboard e UX
- **Código de Acesso:** Substitua o botão atual por um botão escrito "Copiar Código de Acesso do Laboratório". Ele não deve exibir o código no texto, apenas o ícone de copiar. Ao clicar, exiba um toast: "Código copiado com sucesso!".
- **Upload BioVision:** Altere o label de "Metodologia de Análise" para "PDF da Metodologia".

### 3. Histórico Unificado e Navegação
- Use a view `lab_history` para o componente de histórico.
- **Visual:** Remova a coluna "Ação". A linha inteira deve ser clicável. Adicione um efeito de hover (bg-blue-50/10) e cursor-pointer.
- **Identificação:** Se for `sample`, mostre o nome do colaborador e função (`author_info`). Se for `biovision`, mostre o status (concluído/rascunho), o resultado de conformidade e a "Nota da Foto" (`photo_quality`).

### 4. Tela de Resultado BioVision (Ajustes Profundos)
- **Painel Foto:** Ao lado da nota (ex: 7/10), adicione um texto explicativo: Justificativa da nota baseada em nitidez e iluminação. Se a nota < 10, adicione um card: "Dica para Nota 10: Garanta que a placa esteja centralizada e sem reflexos de luz direta."
- **Consultor Técnico (Chat AI):** 
  1. A primeira mensagem deve ser o Aviso Legal: "Os resultados desta análise são apenas de apoio à decisão e não substituem laudos laboratoriais oficiais..." (fundo amarelo suave, conforme anexo).
  2. A segunda mensagem deve ser o resumo da análise terminando com "Alguma dúvida?".
- **Chat Interno:** Abaixo do chat da IA, insira um "Chat da Amostra" (comunicações entre membros), idêntico ao que existe na tela de detalhes da amostra.
- **Relatório PDF:** Adicione um botão "Baixar PDF" ao lado de "Reanalisar". Gere um PDF contendo Foto, Resultado de UFC, Conformidade e Data.
- **Sistema de Estrelas (Feedback):** No canto inferior direito, crie o bloco "Avalie este resultado" com 5 estrelas. Ao clicar em uma estrela, abra um campo de texto com placeholder cinza "Ótimo, poderia por gentileza comentar sobre a sua avaliação?". Ao enviar, mude o bloco para um feedback verde "Obrigado por avaliar" com um link "editar avaliação". Salve isso na tabela `biovision_feedbacks`.

### 5. Controle de Acesso (RBAC) e Admin
- **Restrições:**
  - **Analista:** Bloqueie o acesso às telas de cadastro de novas amostras (Química/Micro). Eles apenas visualizam o que foi designado e usam o BioVision.
  - **Responsável Técnico (RT):** Acesso total ao cadastro de amostras e definição de testes.
- **Painel Administrativo:** Crie uma lógica de login para `adm` com senha `@microbiologia5.0` que redireciona para uma tela exclusiva `/admin/feedbacks`, onde é possível ver todos os comentários e notas deixados pelos usuários no BioVision.

Use os componentes do shadcn/ui para os modais e chats. Garanta que o estado de "clicável" das linhas do histórico redirecione para `/samples/:id` ou `/biovision/run/:id` corretamente.

O banco de dados foi corrigido. A view lab_history agora está disponível com as colunas certas. Por favor, aplique as mudanças de interface solicitadas anteriormente:

1. **Histórico:** Linhas clicáveis, efeito hover azulado, ícones diferentes para BioVision e Amostras.
    
2. **Resultado BioVision:** Chat da IA com Aviso Legal, Chat de Amostra (colaboradores) abaixo, justificativa da nota da foto e botão 'Baixar PDF'.
    
3. **Feedback:** Sistema de 5 estrelas no canto inferior com o campo de comentário interativo que salva na tabela biovision_feedbacks.
    
4. **RBAC:** Garanta que Analistas não vejam botões de cadastro de amostras e que o usuário adm com a senha @microbiologia5.0 possa acessar os feedbacks.
    
5. **IA:** No prompt do BioVision, reforce para ignorar marcas de caneta vermelha ou de outras cores na contagem de UFC.

O SQL foi atualizado e agora o cargo (RT ou Analista) é extraído automaticamente da coluna is_admin. No Dashboard, use a coluna author_info para mostrar quem realizou as amostras manuais.