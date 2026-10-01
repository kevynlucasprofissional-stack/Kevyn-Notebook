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

---

### 🛠️ Próximo passo sugerido:
Quer que eu monte o **Schema da Edge Function** que orquestra essa chamada de API do IBGE dentro do fluxo de chat (Feature 2)? Isso garantirá que o agente receba o dado "mastigado" exatamente quando ele precisar validar o público-alvo.