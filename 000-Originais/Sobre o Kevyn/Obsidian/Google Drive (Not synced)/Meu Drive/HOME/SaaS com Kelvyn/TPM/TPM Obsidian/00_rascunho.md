Você é um Engenheiro de Software Sênior especialista em React, TypeScript, Tailwind e shadcn/ui.

Quero que você faça 2 ajustes objetivos no projeto:

1) Corrigir duplicação de título na tela "/cliente"
Na seção "História das Heroínas", o título está aparecendo duplicado.
Quero que você:

localize a seção na tela /cliente
remova a duplicação
deixe apenas um único título
padronize o texto como "História das Heroínas"

Objetivo:
exibir somente um cabeçalho da seção
manter o restante do card funcionando normalmente
não duplicar título nem no componente pai nem no componente da própria seção

---

2) Trocar a barra tipo toggle por opções expansíveis nas telas de perfil da profissional
Hoje, nas telas de pesquisa/perfil da profissional, como por exemplo:

/cliente/profissional/[id-da-profissional]

existe uma barra horizontal com essas opções:

Serviços
Portfólio
Avaliações
Perguntas e respostas

Atualmente isso funciona como um toggle/tab selector.
Quero refatorar isso para virar uma lista de seções expansíveis em formato accordion, seguindo o padrão do código em anexo. :contentReferenceoaicite:0{index=0}

Requisitos da refatoração
substituir completamente o toggle atual por accordion
cada item deve ser expansível/colapsável
usar o padrão visual e estrutural do componente baseado em:
  @radix-ui/react-accordion
  @radix-ui/react-icons
  shadcn/ui
manter compatibilidade com React + TypeScript + Tailwind
preservar o conteúdo já existente dentro de cada seção
o usuário deve conseguir expandir:
  Serviços
  Portfólio
  Avaliações
  Perguntas e respostas

Comportamento esperado
preferencialmente usar type="single" e collapsible
ao clicar em uma seção, ela expande
ao clicar novamente, ela recolhe
animação suave de abrir/fechar
setinha/chevron rotacionando ao expandir
layout responsivo, principalmente no mobile
spacing, bordas e tipografia coerentes com o design atual do app

---

Instruções técnicas
Use como base o componente accordion enviado em anexo. :contentReferenceoaicite:1{index=1}

Faça o seguinte:
Verifique se o projeto já suporta:
   shadcn/ui
   Tailwind CSS
   TypeScript

Se necessário, ajuste a estrutura para suportar o componente corretamente.

Crie o componente em:
/components/ui/accordion.tsx

Instale as dependências:

npm install @radix-ui/react-accordion @radix-ui/react-icons


Estenda o tailwind.config.js com as animações de accordion do exemplo anexado.
    
Substitua a implementação atual da barra/toggle do perfil da profissional por esse novo accordion.
    

---

Estrutura desejada no perfil da profissional

Cada item do accordion deve representar uma seção real da página:

Serviços

mostrar lista de serviços, preços, descrições e o que já existir hoje nessa aba
    

Portfólio

mostrar imagens, trabalhos ou conteúdo já existente hoje nessa aba
    

Avaliações

mostrar notas, comentários e feedbacks já existentes
    

Perguntas e respostas

mostrar perguntas e respostas / FAQ / conteúdo correspondente atual
    

---

Cuidados importantes

não quebrar a navegação atual
    
não remover dados existentes
    
não criar conteúdo fake se já houver dados reais
    
não usar tabs/toggle depois da refatoração
    
manter o app consistente visualmente
    
garantir boa usabilidade no mobile
    

---

Entrega esperada

Quero que você:

localize os componentes/telas afetados
    
faça a refatoração completa
    
me mostre quais arquivos foram alterados
    
explique brevemente o que foi trocado
    
entregue o código final funcionando
    