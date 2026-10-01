Essa parte é meio complexa e não dá para resumir, então vou colocar todos os dados aqui.

# Mapa de Integrações do Ágora

#### 1. Infraestrutura e Core (O "Motor" do SaaS)

*   **Supabase (Database, Auth & Storage):**
    *   **Função:** Servirá como o banco de dados principal (PostgreSQL), gerenciador de autenticação de usuários (e-mail/senha e OAuth Social) e sistema de *storage* para os `UserUploads` e `AgentUploads` (PDFs/PPTs gerados).
    *   **Como integrar:** Conectar via cliente `@supabase/supabase-js`. Utilizar *Row Level Security (RLS)* para garantir que usuários só acessem seus dados.
*   **Stripe (Pagamentos e Assinaturas):**
    *   **Função:** Gestão dos 4 planos (Freemium, Standard, Pro, Enterprise). Controle de renovação mensal/anual e mudança de *tier*.
    *   **Como integrar:** Implementar via *Stripe Billing* e *Stripe Checkout*. Criar *Webhooks* no backend para atualizar a tabela `plan_id` do usuário no banco assim que o pagamento for confirmado.
*   **Vercel (Hospedagem e Edge Functions):**
    *   **Função:** *Host* para o frontend (Next.js/React) e execução das *Edge Functions* que rodam a lógica dos Agentes (Orquestrador e Especialistas), garantindo baixa latência na resposta da IA.

---

#### 2. Inteligência e IA (O "Cérebro" do Ágora)

*   **OpenAI API (GPT-4o) ou Anthropic API (Claude 3.5 Sonnet):**
    *   **Função:** Motor de raciocínio de todos os Sub-Agentes (Orquestrador, Sociocomportamental, Estrategista, etc.).
    *   **Como integrar:** Via SDKs (`openai` ou `anthropic`). É obrigatório o uso de *Structured Outputs* (JSON mode) para garantir que a saída dos agentes siga o schema definido na arquitetura.
*   **Serper.dev (Google Search API):**
    *   **Função:** Para que o Agente de *Timing & Trends* acesse notícias de última hora, tendências do momento e dados de benchmarking sem alucinar.
    *   **Como integrar:** Chamada API simples enviando o query do agente e recebendo os snippets de texto para o *Context Shock*.

---

#### 3. Dados e Benchmarking (A "Reality Layer")

*   **IBGE API (Sidra/Localidades):**
    *   **Função:** Base de dados para o Analista Sociocomportamental validar o público-alvo (demografia, renda, região).
    *   **Como integrar:** REST API via requisições `fetch` nas *Edge Functions*. Implementar *cache* (Redis) para evitar *rate limiting* e tornar a análise rápida.
*   **Google Analytics Data API (GA4) & Meta Marketing API:**
    *   **Função:** Extração de métricas reais para usuários `Enterprise` (ROI, CTR, CPA) e obtenção de benchmarks de mercado para os demais usuários.
    *   **Como integrar:** OAuth2. O fluxo exige que o usuário autorize o acesso à sua conta de anúncios (Google Ads/Meta Ads). Utilizar o `google-ads-api` e `facebook-nodejs-business-sdk`.

---

#### 4. Ferramentas de Saída e Visualização (Feature 3)

*   **Canva API:**
    *   **Função:** Transformar a "Campanha Otimizada" em apresentações visuais editáveis pelo usuário.
    *   **Como integrar:** Via *Canva Design API*. A IA do Ágora envia os dados (json) para o template do Canva e retorna um link de edição para o usuário.
*   **Gamma API (ou SDK):**
    *   **Função:** Alternativa para geração automática de *decks* de apresentação com design inteligente.
    *   **Como integrar:** Via requisições HTTP enviando a estrutura do relatório gerado pelo Agente Sintetizador.
*   **Puppeteer/Playwright (PDF Generation):**
    *   **Função:** Para exportação local de relatórios em PDF.
    *   **Como integrar:** Rodar em *Edge Function* para "imprimir" a versão HTML/Markdown do relatório final em um arquivo PDF para download.

# Integração com o IBGE
### 1. Estrutura do Serviço (`services/ibgeService.js`)

Este serviço lida com a busca de localização e dados demográficos.

```javascript
import axios from 'axios';

const IBGE_BASE_URL = 'https://servicodados.ibge.gov.br/api/v1';
const SIDRA_BASE_URL = 'https://api.sidra.ibge.gov.br';

export const IbgeService = {
  /**
   * Busca códigos de municípios pelo nome ou UF
   */
  async getMunicipios(uf = 'SP') {
    const response = await axios.get(`${IBGE_BASE_URL}/localidades/estados/${uf}/municipios`);
    return response.data.map(m => ({ id: m.id, nome: m.nome }));
  },

  /**
   * Busca dados demográficos (Ex: População de um município)
   * Utiliza a tabela 6579 (Censo) como exemplo
   */
  async getDemografiaMunicipio(municipioId) {
    // Tabela 6579: População residente
    const url = `${SIDRA_BASE_URL}/values/t/6579/n6/${municipioId}`;
    const response = await axios.get(url);
    
    // Formatação amigável para a IA
    return {
      municipio_id: municipioId,
      populacao_estimada: response.data[1]?.V || 'Não informado',
      fonte: 'IBGE SIDRA'
    };
  }
};
```

---

### 2. Integração com o Agente (O "Pulo do Gato")

Não envie o JSON bruto do IBGE para o Agente. Ele não precisa de código de tabela ou nomenclaturas complexas. **Trate o dado antes**.

No seu *workflow* de análise, a chamada seria assim:

```javascript
// Exemplo no controlador de análise (ex: Agent Orquestrador)
async function enriquecerDadosAnalise(dadosUsuario) {
  const { cidade, uf } = dadosUsuario;
  
  // 1. Busca dados no IBGE
  const demografia = await IbgeService.getDemografiaMunicipio(cidade.id);
  
  // 2. Constrói o payload para o Agente Sociocomportamental
  const payloadParaAgente = {
    produto: dadosUsuario.produto,
    contexto_regional: {
      cidade: cidade.nome,
      populacao: demografia.populacao_estimada,
      perfil: "O mercado local possui alta densidade populacional, ideal para..." // IA interpreta o valor
    }
  };
  
  return payloadParaAgente;
}
```

---

### 3. Regras Críticas para o Lovable (Implementação)

Para garantir que o Ágora não trave com essa integração, instrua o Lovable a seguir estas 3 regras:

1.  **Cache com TTL:** A API do IBGE é pública, mas não abuse. Configure um cache no seu backend (ex: `node-cache` ou Redis) com `TTL: 86400` (24 horas). Dados demográficos de cidades não mudam minuto a minuto.
2.  **Fallback de Segurança:** Se a API do IBGE estiver fora do ar (comum em picos de demanda), o serviço **deve** retornar um objeto vazio `{}` ou uma flag `dados_temporariamente_indisponiveis: true`. O Agente de IA foi instruído a lidar com isso e não "quebrar".
3.  **Normalização (Clean Data):** O IBGE retorna campos como `V` (valor) ou `D1N` (nome). **O Lovable deve criar um mapper** que renomeie esses campos para nomes legíveis (`populacao_total`, `nome_municipio`) *antes* de enviar para o LLM. Isso economiza tokens e aumenta a precisão da resposta da IA.

### 4. Estrutura do Serviço (`services/ibgeService.js`)

Este serviço lida com a busca de localização e dados demográficos.

```javascript
import axios from 'axios';

const IBGE_BASE_URL = 'https://servicodados.ibge.gov.br/api/v1';
const SIDRA_BASE_URL = 'https://api.sidra.ibge.gov.br';

export const IbgeService = {
  /**
   * Busca códigos de municípios pelo nome ou UF
   */
  async getMunicipios(uf = 'SP') {
    const response = await axios.get(`${IBGE_BASE_URL}/localidades/estados/${uf}/municipios`);
    return response.data.map(m => ({ id: m.id, nome: m.nome }));
  },

  /**
   * Busca dados demográficos (Ex: População de um município)
   * Utiliza a tabela 6579 (Censo) como exemplo
   */
  async getDemografiaMunicipio(municipioId) {
    // Tabela 6579: População residente
    const url = `${SIDRA_BASE_URL}/values/t/6579/n6/${municipioId}`;
    const response = await axios.get(url);
    
    // Formatação amigável para a IA
    return {
      municipio_id: municipioId,
      populacao_estimada: response.data[1]?.V || 'Não informado',
      fonte: 'IBGE SIDRA'
    };
  }
};
```

---

### 5. Integração com o Agente (O "Pulo do Gato")

Não envie o JSON bruto do IBGE para o Agente. Ele não precisa de código de tabela ou nomenclaturas complexas. **Trate o dado antes**.

No seu *workflow* de análise, a chamada seria assim:

```javascript
// Exemplo no controlador de análise (ex: Agent Orquestrador)
async function enriquecerDadosAnalise(dadosUsuario) {
  const { cidade, uf } = dadosUsuario;
  
  // 1. Busca dados no IBGE
  const demografia = await IbgeService.getDemografiaMunicipio(cidade.id);
  
  // 2. Constrói o payload para o Agente Sociocomportamental
  const payloadParaAgente = {
    produto: dadosUsuario.produto,
    contexto_regional: {
      cidade: cidade.nome,
      populacao: demografia.populacao_estimada,
      perfil: "O mercado local possui alta densidade populacional, ideal para..." // IA interpreta o valor
    }
  };
  
  return payloadParaAgente;
}
```

---

### 6. Regras Críticas para o Lovable (Implementação)

Para garantir que o Ágora não trave com essa integração, instrua o Lovable a seguir estas 3 regras:

1.  **Cache com TTL:** A API do IBGE é pública, mas não abuse. Configure um cache no seu backend (ex: `node-cache` ou Redis) com `TTL: 86400` (24 horas). Dados demográficos de cidades não mudam minuto a minuto.
2.  **Fallback de Segurança:** Se a API do IBGE estiver fora do ar (comum em picos de demanda), o serviço **deve** retornar um objeto vazio `{}` ou uma flag `dados_temporariamente_indisponiveis: true`. O Agente de IA foi instruído a lidar com isso e não "quebrar".
3.  **Normalização (Clean Data):** O IBGE retorna campos como `V` (valor) ou `D1N` (nome). **O Lovable deve criar um mapper** que renomeie esses campos para nomes legíveis (`populacao_total`, `nome_municipio`) *antes* de enviar para o LLM. Isso economiza tokens e aumenta a precisão da resposta da IA.

### 7. O Fluxo de Automação (Backend)
O seu backend deve funcionar como o "Maestro" que prepara o ambiente para o Agente.

1.  **Usuário envia o prompt:** "Quero vender consórcio de imóveis em São Paulo".
2.  **Orquestrador (Backend):** Identifica a intenção e extrai a localização ("São Paulo").
3.  **Middleware de Enriquecimento:**
    *   Faz a chamada automática para a API do IBGE/SIDRA.
    *   Recebe o JSON bruto: `{ "populacao": 12396372, "renda_domiciliar": 4500 }`.
4.  **Injeção no Prompt:** O backend monta o prompt final **já com os dados inseridos** antes de enviar para o `Analista Sociocomportamental`.

### 5. O Prompt Dinâmico (Template)
No seu código (Node.js/TypeScript), o seu prompt não deve ser uma string estática, mas uma função que recebe os dados do IBGE. Veja o exemplo de como isso é construído:

```javascript
// Exemplo de como você montaria isso no backend (Node.js)
async function criarPromptAnalista(userInput, dadosIbge) {
  return `
    # PREAMBLE
    Atue como Analista Sênior...
    
    # DADOS TÉCNICOS (AUTOMATICAMENTE PUXADOS DO IBGE)
    - Região: ${dadosIbge.nome}
    - População: ${dadosIbge.populacao}
    - Renda Média: ${dadosIbge.renda}
    - Densidade Demográfica: ${dadosIbge.densidade}
    
    # INSTRUÇÃO
    Considere esses dados reais do IBGE na sua análise. Se a renda for baixa para o produto, aponte a falha na estratégia.
    
    # JSON SCHEMA
    ... (o resto do seu prompt)
  `;
}
```
