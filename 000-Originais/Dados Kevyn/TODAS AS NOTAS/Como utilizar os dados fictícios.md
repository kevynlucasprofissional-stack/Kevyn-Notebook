Com certeza. Para um Hackathon, você não quer perder tempo tentando conectar em APIs reais do governo que podem cair ou ser complexas demais agora. **Você precisa de um Mock (dados falsos) sólido.**

Aqui está um JSON pronto para copiar e colar. Ele cobre os dois lados do seu app: o **Feed de Leis (Tinder)** e a **Lógica do Bot**.

### 1. `feed_legislativo.json` (Para o "Tinder")
Este arquivo simula o que o seu Backend devolveria para o Frontend. Note o contraste entre `texto_original` (chato) e `resumo_ia` (simples).

```json
[
  {
    "id": 101,
    "projeto": "PL 45/2024",
    "autor": "Vereador Cláudio Papelada",
    "categoria": "Urbanismo",
    "texto_original": "Dispõe sobre a alteração de zoneamento da área central, permitindo a instalação de comércios ambulantes fixos na Praça da Matriz e revoga o inciso II do artigo 4º da Lei de Posturas.",
    "resumo_ia": "🌮 Food Trucks na Praça: Esse projeto libera barracas de comida fixa na Praça da Matriz. Vai trazer mais vida noturna, mas pode reduzir o espaço para caminhar.",
    "impacto": "Alto",
    "imagem_url": "https://source.unsplash.com/random/400x300/?foodtruck",
    "termometro_votos": { "apoio": 65, "rejeicao": 35 }
  },
  {
    "id": 102,
    "projeto": "PL 12/2024",
    "autor": "Vereadora Maria Escola",
    "categoria": "Educação",
    "texto_original": "Institui a obrigatoriedade de instalação de detectores de metais nas entradas de todas as escolas da rede municipal de ensino e dispõe sobre a contratação de segurança privada.",
    "resumo_ia": "🛡️ Segurança nas Escolas: Quer obrigar todas as escolas municipais a terem detector de metais e guarda. Aumenta a segurança, mas vai custar R$ 2 milhões por ano do orçamento.",
    "impacto": "Muito Alto",
    "imagem_url": "https://source.unsplash.com/random/400x300/?school",
    "termometro_votos": { "apoio": 80, "rejeicao": 20 }
  },
  {
    "id": 103,
    "projeto": "PL 88/2024",
    "autor": "Prefeitura Municipal",
    "categoria": "Trânsito",
    "texto_original": "Altera o sentido de circulação da Rua das Acácias para mão única no sentido Bairro-Centro e proíbe estacionamento no lado par da via.",
    "resumo_ia": "🚗 Mudança na Rua das Acácias: A rua vai virar mão única (indo para o centro) e não vai mais poder estacionar do lado par. O objetivo é diminuir o trânsito na hora do rush.",
    "impacto": "Médio",
    "imagem_url": "https://source.unsplash.com/random/400x300/?traffic",
    "termometro_votos": { "apoio": 40, "rejeicao": 60 }
  }
]
```

---

### 2. `cerebro_bot.json` (Para a "Triagem e Formalização")
Use isso para treinar ou simular as respostas do seu Chatbot. Aqui está a mágica da "tradução" de reclamação informal para documento oficial.

```json
[
  {
    "intent": "iluminacao_publica",
    "palavras_chave": ["escuro", "luz", "poste", "lampada", "queimada", "perigo"],
    "responsavel": "Prefeitura (Executivo)",
    "educacao_invisivel": "Entendi. Manutenção de luz é responsabilidade da Prefeitura (Secretaria de Obras), e não diretamente dos vereadores. Mas eu vou formalizar seu pedido agora.",
    "template_formal": "À Secretaria de Obras,\n\nSolicito reparo urgente na iluminação pública localizada na [ENDERECO_USUARIO]. A ausência de iluminação viola o princípio da eficiência na prestação de serviços públicos e compromete a segurança dos munícipes, conforme o Art. 144 da Constituição.\n\nAguardo protocolo de atendimento."
  },
  {
    "intent": "buraco_rua",
    "palavras_chave": ["buraco", "asfalto", "cratera", "pneu", "rua quebrada"],
    "responsavel": "Prefeitura (Executivo)",
    "educacao_invisivel": "Buraco na rua é zeladoria urbana, função da Prefeitura. O vereador pode fiscalizar, mas quem arruma é o executivo. Deixa comigo, vou criar a solicitação técnica.",
    "template_formal": "À Secretaria de Infraestrutura,\n\nComunico a existência de avaria severa na pavimentação asfáltica (buraco) na altura do número [NUMERO] da [ENDERECO_USUARIO]. O defeito oferece risco de acidentes e danos materiais aos veículos, sendo responsabilidade do município a manutenção da via pública.\n\nSolicito cronograma de reparo."
  },
  {
    "intent": "barulho_vizinho",
    "palavras_chave": ["barulho", "som alto", "festa", "gritaria", "musica"],
    "responsavel": "Fiscalização Urbana / Guarda Municipal",
    "educacao_invisivel": "Perturbação do sossego é infração. Existe uma 'Lei do Silêncio' na cidade. Vou gerar uma denúncia baseada no Código de Posturas.",
    "template_formal": "Ao Departamento de Fiscalização de Posturas,\n\nDenuncio a ocorrência reiterada de poluição sonora acima dos decibéis permitidos em lei na localidade [ENDERECO_ALVO]. Solicito visita de fiscalização e medição de ruído, com base no Código de Posturas Municipal, visando garantir o sossego público."
  }
]
```

### Como usar isso no Código (Dica Rápida):

1.  **No Frontend (React/Vue/Flutter):**
    *   Crie um arquivo `data.js` e cole o **JSON 1**.
    *   No componente de Cards (Tinder), faça um `.map()` nesse array.
    *   Use o campo `resumo_ia` para o texto grande e `texto_original` apenas no "Ver mais".

2.  **No Bot (Python/Node):**
    *   Quando o usuário digitar: "Minha rua tá cheia de buraco", seu código procura a palavra "buraco" no **JSON 2**.
    *   Se encontrar, ele devolve o texto do campo `educacao_invisivel`.
    *   Depois de 2 segundos, ele exibe o `template_formal` preenchendo o `[ENDERECO_USUARIO]` com a localização do GPS do celular.

Isso vai dar a impressão de uma inteligência artificial super avançada, mesmo sendo apenas um JSON estático bem feito. Boa sorte!