---
Modificado:
  - terça-feira 83 24/03/2026
Criado: domingo 81 22/03/2026
---



Como especialista em Design de Produtos e Engenharia de Prompts, analisei o vídeo enviado. O site no vídeo pertence à **n8n** (uma plataforma de automação de workflows). Ele possui um design extremamente moderno, focado em **Dark Mode**, com uso intenso de **Glassmorphism (efeito de vidro)**, **bordas brilhantes (neon/glow)**, tipografia robusta sem serifa, gradientes de texto e layouts no estilo **Bento Grid** (cartões arredondados agrupados).

Para clonar essa estética e adaptá-la perfeitamente ao seu SaaS, o **BioVision AI** (conforme os dados do seu documento), criei um super-prompt otimizado para o **Lovable**. 

O Lovable funciona melhor quando você dá a direção de design clara e entrega o "copy" (textos) já estruturado seção por seção.

---

### 📋 Copie e cole o prompt abaixo no Lovable:

```text
Atue como um Engenheiro de Front-end e UX/UI Designer de nível Sênior. Quero que você crie a Landing Page de um SaaS chamado "BioVision AI". 

A inspiração de design é o site da "n8n". A estética deve ser estritamente "Dark Mode" (fundo quase preto, ex: bg-slate-950 ou bg-black), visual high-tech, moderno e voltado para times técnicos e laboratoriais. 

REGRAS DE DESIGN (ESTILO VISUAL):
1. Use a paleta de cores: Fundo escuro (Slate/Black), textos principais em branco puro ou cinza claro, e detalhes/botões em um gradiente neon (sugiro Azul Ciano para Roxo/Magenta, remetendo à biotecnologia e IA).
2. Utilize "Glassmorphism" nos cartões (fundos levemente translúcidos com blur e bordas finas com opacidade de 10% a 20%).
3. Textos de destaque (Headings) devem usar "gradient text" (bg-clip-text text-transparent bg-gradient-to-r).
4. Adicione brilhos sutis (glow) atrás de elementos importantes.
5. A tipografia deve ser limpa, sem serifa (como Inter, Roboto ou Geist), com pesos variados (Bold para títulos, Regular para corpo).
6. Use ícones modernos da biblioteca Lucide React.

ESTRUTURA E TEXTOS DA PÁGINA (Preencha os componentes exatamente com estes textos):

1. HEADER (Navegação):
- Logo: "BioVision AI" (com um ícone minimalista de uma placa de Petri ou nó de IA).
- Links: Produto, Casos de Uso, Tecnologia, Preços.
- Botões à direita: "Entrar" (texto simples) e "Começar Grátis" (botão primário com gradiente/brilho).

2. HERO SECTION (Seção Principal):
- Título principal (Gigante, centralizado ou alinhado à esquerda, usando texto gradiente em algumas palavras): "Automação Inteligente de IA para Microbiologia."
- Subtítulo (Cinza claro, tamanho médio): "Detecte, segmente e conte Unidades Formadoras de Colônia (UFC) com a precisão da visão computacional. Sem equipamentos caros, direto do seu navegador."
- Botões: "Começar Grátis" (Primário) e "Falar com Especialistas" (Secundário, outline).
- Imagem/Visual ao lado ou abaixo: Crie um mockup simulando uma interface flutuante mostrando uma placa de Petri escaneada com vários pontos/bounding boxes verdes/azuis indicando contagem de colônias.

3. SOCIAL PROOF (Prova Social - Faixa horizontal):
- Texto pequeno: "Transformando o controle de qualidade nos setores:"
- Adicione ícones fictícios (ou ícones Lucide) representando indústrias: Alimentos & Bebidas, Água e Saneamento, Aquicultura, Indústria Farmacêutica.

4. BENTO GRID DE FUNCIONALIDADES (Inspirado nos cartões do vídeo):
- Crie um grid assimétrico com 3 ou 4 cartões.
- Cartão 1 (Largo): "Processamento Automatizado em Nuvem." Texto: "Faça upload das imagens capturadas por smartphones ou câmeras convencionais. A IA processa e padroniza a iluminação automaticamente." (Ícone de Nuvem/IA).
- Cartão 2 (Quadrado): "Zero Subjetividade." Texto: "Elimine o erro humano e o cansaço visual. Padronize seus laudos com precisão matemática." (Ícone de Alvo/Precisão).
- Cartão 3 (Quadrado): "Rastreabilidade Total." Texto: "Armazenamento histórico de análises e geração automática de relatórios em PDF para auditorias." (Ícone de Documento/Escudo).

5. SEÇÃO DE COMPARAÇÃO (Estilo "Code vs UI" do vídeo, mas adaptado):
- Título: "Análise Tradicional vs BioVision AI"
- Crie dois painéis lado a lado.
- Painel Esquerdo (Tradicional): "Processo Manual: Lento, sujeito a erros, requer contadores de alto custo." (Mostre um ícone de prancheta e relógio).
- Painel Direito (BioVision): "Com IA: Resultados em segundos, relatórios digitais, escalável (SaaS)." (Mostre um gráfico de velocidade e ícone de IA brilhando).

6. MÉTRICAS E IMPACTO (Cartões escuros com bordas brilhantes):
- Cartão 1: "Reduz o tempo de análise em até 80%"
- Cartão 2: "Evita o descarte desnecessário de reagentes"
- Cartão 3: "Aumenta a segurança sanitária"

7. CALL TO ACTION FINAL (Rodapé superior):
- Título gigante: "Pronto para modernizar seu laboratório?"
- Subtítulo: "A democratização do acesso à análise microbiológica automatizada começou. Experimente na prática."
- Botão: "Criar Conta Gratuita"

8. FOOTER:
- Logo BioVision AI.
- Colunas simples para Produto, Suporte, Termos de Privacidade e Redes Sociais.

Por favor, gere o código completo focando em animações suaves de entrada (fade-in, slide-up) e design responsivo perfeito para mobile e desktop.
```

---

### 💡 Ideias Extras para você implementar no Lovable (Dicas de Ouro)

Como Engenheiro de Produto, lendo o escopo do seu projeto, sugiro algumas interações que você pode pedir para o Lovable adicionar depois que a estrutura inicial for gerada:

1. **Slider de Antes e Depois (Image Comparison Slider):**
   * *O que é:* No lugar de uma imagem estática na "Hero Section", peça para o Lovable criar um componente de arrastar (slider).
   * *Impacto:* O usuário arrasta a barra para a direita e vê a foto real da placa de Petri; arrasta para a esquerda e vê a imagem processada pelo BioVision, com as colônias contadas, marcadas e segmentadas. Isso vende a solução instantaneamente.

2. **Calculadora de ROI interativa:**
   * *O que é:* Uma pequena seção onde o usuário desliza uma barra dizendo *"Quantas placas você analisa por mês?"* (Ex: 1000). E embaixo o sistema calcula dinamicamente: *"Horas economizadas com IA: 80 horas/mês"*. 
   * *Impacto:* Justifica na hora o modelo de assinatura SaaS (B2B) frente ao custo do analista.

3. **Efeito "Scanner" no Hover:**
   * *O que é:* Nas imagens das placas de Petri do site, pedir para adicionar uma animação CSS onde, ao passar o mouse por cima, uma linha neon verde/azul desce pela imagem, simulando a IA escaneando as bactérias/colônias.

4. **Micro-interações de "Loading" de IA:**
   * Para dar o "feeling" de tecnologia profunda, adicione um terminal falso ou pequenos logs de texto animado na hero section: `> Carregando imagem... > Padronizando iluminação... > IA detectou 142 UFC... > Laudo gerado.`

**Como usar o Lovable de forma eficiente:** Não peça alterações drásticas de uma vez. Primeiro, cole o prompt acima. Espere ele gerar a página. Depois, vá pedindo os refinamentos (ex: *"Ficou ótimo! Agora troque a imagem principal por um componente interativo de slider antes/depois..."*).