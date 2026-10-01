---
Modificado:
  - sábado 115 25/04/2026
Criado: sábado 115 25/04/2026
---
Não alterei o código. Pelo desenho atual do repo, a feature fica concentrada em parser + expansão do tipo de card + UI de revisão + editor, sem tocar no algoritmo de repetição.

**Obrigatórios**
- [src/card/questions/question.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/card/questions/question.ts>) - adicionar `CardType.MultipleChoice` ao enum e manter o tipo reconhecível no domínio.
- [src/parser.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/parser.ts>) - reconhecer o marcador `?mc` e emitir o novo `CardType`; esse é o ponto que decide qual tipo de flashcard a nota contém.
- [src/card/questions/question-type.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/card/questions/question-type.ts>) - implementar o handler/formatter de MultipleChoice; aqui você vai parsear até 4 opções, garantir 1 correta e gerar o `front/back` com a UI interativa.
- [src/ui/obsidian-ui-components/content-container/card-container/card-container.tsx](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/ui/obsidian-ui-components/content-container/card-container/card-container.tsx>) - ligar os cliques/seleção das alternativas, revelar a dica quando errar e manter o fluxo normal de `Show Answer` + `Again/Hard/Good/Easy`.
- [src/ui/obsidian-ui-components/content-container/card-container/card-container.css](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/ui/obsidian-ui-components/content-container/card-container/card-container.css>) - estilizar lista de opções, estado selecionado/correto/incorreto e a dica.
- [src/ui/obsidian-ui-components/modals/edit-modal.tsx](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/ui/obsidian-ui-components/modals/edit-modal.tsx>) - fazer o `?mc` round-trip corretamente no editor; sem isso, o modal tende a confundir `?mc` com o separador `?` já existente.

**Docs**
- [README.md](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/README.md>) - adicionar o novo tipo na lista de recursos e nos exemplos.
- [docs/docs/en/flashcards/flashcards-overview.md](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/docs/docs/en/flashcards/flashcards-overview.md>) - atualizar a tabela de tipos suportados.
- [docs/docs/en/flashcards/q-and-a-cards.md](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/docs/docs/en/flashcards/q-and-a-cards.md>) ou uma nova página `multiple-choice-cards.md` - depende se você quer manter tudo na página atual ou separar por tipo.
- [mkdocs.yml](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/mkdocs.yml>) - só é necessário se você criar uma página nova no nav.
- [docs/docs/zh/flashcards.md](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/docs/docs/zh/flashcards.md>) ou a página chinesa equivalente - se você mantiver a tradução sincronizada.
- `styles.css` - só como artefato gerado do build, se o repositório continuar versionando o CSS compilado; a fonte real é o CSS em `src/ui/...`.

**Testes**
- [tests/unit/parser.test.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/tests/unit/parser.test.ts>) - cobrir o `?mc`, o fim de card, comentários/codeblocks e números de linha.
- [tests/unit/card/questions/questions-type.test.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/tests/unit/card/questions/questions-type.test.ts>) - validar a geração do `front/back` do MultipleChoice e as regras de 4 opções / 1 correta.
- [tests/unit/note-question-parser.test.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/tests/unit/note-question-parser.test.ts>) - garantir que o novo tipo atravessa o pipeline até `Question` e `Card` sem mexer em scheduling.
- um novo teste de UI em `tests/unit/...` se você quiser automatizar o clique na opção errada e a exibição da dica; hoje o repositório não tem cobertura real para `CardContainer`.

**Condicionais**
- [src/ui/obsidian-ui-components/content-container/settings-page/flashcards-page.tsx](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/ui/obsidian-ui-components/content-container/settings-page/flashcards-page.tsx>) - só se você quiser mostrar/validar o conflito do `?mc` com o separador multiline configurável.
- [src/settings.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/settings.ts>) e [tests/unit/settings.test.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/tests/unit/settings.test.ts>) - só se você adicionar validação/migração para reservar `?mc` como token fixo.
- `src/ui/styles.css` - só se você optar por classes utilitárias compartilhadas em vez de manter os estilos localizados no `card-container.css`.

**Riscos técnicos**
- `?mc` começa com `?`, então ele conflita visualmente com o multiline atual; o parser precisa checar `?mc` antes do `?` genérico, e o editor precisa tratar isso explicitamente.
- O `CardContainer` hoje só ignora `INPUT` e `TEXTAREA` no atalho global; se as alternativas forem `button`, `Space/Enter` pode disparar `Show Answer` por engano. Radios/inputs são a opção mais segura.
- O pipeline atual não isola exceções por card; se o novo handler lançar erro, você pode quebrar o parse da nota inteira ou truncar dados de agendamento.
- Se você decidir guardar metadados além de `front/back`, talvez precise ampliar `Card`, `CardFrontBack` e a criação de cards; se mantiver tudo em HTML gerado, evita essa expansão.
- Texto de opção e dica pode conter markdown/HTML; você precisa definir se isso será escapado ou renderizado.

**Melhor estratégia**
- Reservar `CardType.MultipleChoice` no enum e reconhecer `?mc` no parser.
- Implementar o MultipleChoice como um handler puro em `question-type.ts`, gerando um único `CardFrontBack` com `front` interativo e `back` simples.
- Manter o algoritmo e `processReview` intactos; a escolha da alternativa não deve chamar `processReviewHandler`.
- Fazer a interação de clique no `card-container.tsx`, não no motor de agendamento.
- Preservar a edição via `edit-modal.tsx` para round-trip de `?mc`.
- Se quiser melhor organização, extrair a lógica nova para um helper próprio em `src/card/questions/` e um helper de DOM em `src/ui/.../card-container/`, deixando os arquivos grandes só com a integração.

**O que testar antes de escrever código**
- Parser aceita exatamente o formato `?mc` e não confunde com `?`.
- Parser rejeita ou trata de forma segura casos com mais de 4 opções e com mais de 1 correta.
- A renderização mostra as opções na frente, mantém os botões de revisão normais e revela a dica quando a opção errada é escolhida.
- A escolha da alternativa não agenda o cartão nem altera o fluxo de `Again/Hard/Good/Easy`.
- O modal de edição salva e reabre o mesmo `?mc` sem transformar o bloco em outro tipo de card.
- Um teste de integração em `note-question-parser.test.ts` para garantir que o novo tipo atravessa o pipeline inteiro.
- Um smoke test manual em Obsidian para teclado + mouse, porque a UI de revisão não tem boa cobertura automatizada hoje.

Se quiser, na próxima etapa eu posso marcar as funções exatas dentro desses arquivos e te passar uma ordem segura de implementação.

# Resposta Codex:

Não alterei o código. Pelo desenho atual do repo, a feature fica concentrada em parser + expansão do tipo de card + UI de revisão + editor, sem tocar no algoritmo de repetição.

**Obrigatórios**
- [src/card/questions/question.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/card/questions/question.ts>) - adicionar `CardType.MultipleChoice` ao enum e manter o tipo reconhecível no domínio.
- [src/parser.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/parser.ts>) - reconhecer o marcador `?mc` e emitir o novo `CardType`; esse é o ponto que decide qual tipo de flashcard a nota contém.
- [src/card/questions/question-type.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/card/questions/question-type.ts>) - implementar o handler/formatter de MultipleChoice; aqui você vai parsear até 4 opções, garantir 1 correta e gerar o `front/back` com a UI interativa.
- [src/ui/obsidian-ui-components/content-container/card-container/card-container.tsx](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/ui/obsidian-ui-components/content-container/card-container/card-container.tsx>) - ligar os cliques/seleção das alternativas, revelar a dica quando errar e manter o fluxo normal de `Show Answer` + `Again/Hard/Good/Easy`.
- [src/ui/obsidian-ui-components/content-container/card-container/card-container.css](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/ui/obsidian-ui-components/content-container/card-container/card-container.css>) - estilizar lista de opções, estado selecionado/correto/incorreto e a dica.
- [src/ui/obsidian-ui-components/modals/edit-modal.tsx](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/ui/obsidian-ui-components/modals/edit-modal.tsx>) - fazer o `?mc` round-trip corretamente no editor; sem isso, o modal tende a confundir `?mc` com o separador `?` já existente.

**Docs**
- [README.md](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/README.md>) - adicionar o novo tipo na lista de recursos e nos exemplos.
- [docs/docs/en/flashcards/flashcards-overview.md](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/docs/docs/en/flashcards/flashcards-overview.md>) - atualizar a tabela de tipos suportados.
- [docs/docs/en/flashcards/q-and-a-cards.md](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/docs/docs/en/flashcards/q-and-a-cards.md>) ou uma nova página `multiple-choice-cards.md` - depende se você quer manter tudo na página atual ou separar por tipo.
- [mkdocs.yml](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/mkdocs.yml>) - só é necessário se você criar uma página nova no nav.
- [docs/docs/zh/flashcards.md](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/docs/docs/zh/flashcards.md>) ou a página chinesa equivalente - se você mantiver a tradução sincronizada.
- `styles.css` - só como artefato gerado do build, se o repositório continuar versionando o CSS compilado; a fonte real é o CSS em `src/ui/...`.

**Testes**
- [tests/unit/parser.test.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/tests/unit/parser.test.ts>) - cobrir o `?mc`, o fim de card, comentários/codeblocks e números de linha.
- [tests/unit/card/questions/questions-type.test.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/tests/unit/card/questions/questions-type.test.ts>) - validar a geração do `front/back` do MultipleChoice e as regras de 4 opções / 1 correta.
- [tests/unit/note-question-parser.test.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/tests/unit/note-question-parser.test.ts>) - garantir que o novo tipo atravessa o pipeline até `Question` e `Card` sem mexer em scheduling.
- um novo teste de UI em `tests/unit/...` se você quiser automatizar o clique na opção errada e a exibição da dica; hoje o repositório não tem cobertura real para `CardContainer`.

**Condicionais**
- [src/ui/obsidian-ui-components/content-container/settings-page/flashcards-page.tsx](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/ui/obsidian-ui-components/content-container/settings-page/flashcards-page.tsx>) - só se você quiser mostrar/validar o conflito do `?mc` com o separador multiline configurável.
- [src/settings.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/src/settings.ts>) e [tests/unit/settings.test.ts](<C:/Users/Kevyn%20Lucas/Downloads/obsidian-spaced-repetition-main/tests/unit/settings.test.ts>) - só se você adicionar validação/migração para reservar `?mc` como token fixo.
- `src/ui/styles.css` - só se você optar por classes utilitárias compartilhadas em vez de manter os estilos localizados no `card-container.css`.

**Riscos técnicos**
- `?mc` começa com `?`, então ele conflita visualmente com o multiline atual; o parser precisa checar `?mc` antes do `?` genérico, e o editor precisa tratar isso explicitamente.
- O `CardContainer` hoje só ignora `INPUT` e `TEXTAREA` no atalho global; se as alternativas forem `button`, `Space/Enter` pode disparar `Show Answer` por engano. Radios/inputs são a opção mais segura.
- O pipeline atual não isola exceções por card; se o novo handler lançar erro, você pode quebrar o parse da nota inteira ou truncar dados de agendamento.
- Se você decidir guardar metadados além de `front/back`, talvez precise ampliar `Card`, `CardFrontBack` e a criação de cards; se mantiver tudo em HTML gerado, evita essa expansão.
- Texto de opção e dica pode conter markdown/HTML; você precisa definir se isso será escapado ou renderizado.

**Melhor estratégia**
- Reservar `CardType.MultipleChoice` no enum e reconhecer `?mc` no parser.
- Implementar o MultipleChoice como um handler puro em `question-type.ts`, gerando um único `CardFrontBack` com `front` interativo e `back` simples.
- Manter o algoritmo e `processReview` intactos; a escolha da alternativa não deve chamar `processReviewHandler`.
- Fazer a interação de clique no `card-container.tsx`, não no motor de agendamento.
- Preservar a edição via `edit-modal.tsx` para round-trip de `?mc`.
- Se quiser melhor organização, extrair a lógica nova para um helper próprio em `src/card/questions/` e um helper de DOM em `src/ui/.../card-container/`, deixando os arquivos grandes só com a integração.

**O que testar antes de escrever código**
- Parser aceita exatamente o formato `?mc` e não confunde com `?`.
- Parser rejeita ou trata de forma segura casos com mais de 4 opções e com mais de 1 correta.
- A renderização mostra as opções na frente, mantém os botões de revisão normais e revela a dica quando a opção errada é escolhida.
- A escolha da alternativa não agenda o cartão nem altera o fluxo de `Again/Hard/Good/Easy`.
- O modal de edição salva e reabre o mesmo `?mc` sem transformar o bloco em outro tipo de card.
- Um teste de integração em `note-question-parser.test.ts` para garantir que o novo tipo atravessa o pipeline inteiro.
- Um smoke test manual em Obsidian para teclado + mouse, porque a UI de revisão não tem boa cobertura automatizada hoje.

Se quiser, na próxima etapa eu posso marcar as funções exatas dentro desses arquivos e te passar uma ordem segura de implementação.