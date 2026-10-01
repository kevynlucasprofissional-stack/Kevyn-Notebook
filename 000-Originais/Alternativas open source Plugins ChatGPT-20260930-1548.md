# Alternativas open source Plugins ChatGPT

**User:** Anonymous  
**Created:** 9/30/2026 15:33:43  
**Updated:** 9/30/2026 15:44:35  
**Exported:** 9/30/2026 15:48:42  
**Link:** [https://chatgpt.com/c/6abd5607-1158-83e9-ab54-8e8d7c51979e](https://chatgpt.com/c/6abd5607-1158-83e9-ab54-8e8d7c51979e)  

## Prompt:
30/09/2026, 15:34:25

Preciso de alternativas opensource que tenham essa funcionalidade de plugins/conectores do ChatGPT para eu poder estudar

## Response:
30/09/2026, 15:34:30 · gpt-5-6-thinking

Vou separar em duas categorias: **interfaces estilo ChatGPT com conectores/plugins prontos** e **plataformas para estudar como esses conectores são construídos por baixo**. Também vou priorizar projetos ativos e com arquitetura aberta o bastante para você inspecionar o código.

> **Mapeando alternativas abertas**
>
> Estou organizando opções por proximidade com a experiência do ChatGPT e pela abertura real das licenças. Também vou separar projetos compatíveis com OSI daqueles apenas “source-available”, destacando arquitetura, conectores, permissões e execução de ferramentas.
>
> **Mapeou alternativas abertas**
>
> 
>
> **Comparando opções locais**
>
> Estou incluindo Jan, LobeChat e Cherry Studio como clientes desktop, mas vou distinguir projetos realmente compatíveis com licenças abertas daqueles com restrições adicionais. Também vou posicionar MCP, OpenAPI, autenticação e lojas de extensões como critérios centrais.
>
> **Priorizando estudos práticos**
>
> Estou tratando a funcionalidade como a combinação de host de agentes, conectores MCP ou OpenAPI, autenticação, permissões, descoberta de extensões e execução de ferramentas. Para estudar, LibreChat e Open WebUI parecem os pontos de partida mais completos; Jan e Cherry Studio complementam o cenário desktop.
>
> **Comparou opções locais e priorizou estudos práticos**
>
> 
>
> **Pesquisou 13 sites**
>
> 
>
> Pensou por 1m 3s

Sim. Se o que você quer estudar é especificamente a arquitetura por trás de **“ChatGPT + Plugins/Connectors + OAuth + ferramentas externas + ações”**, hoje existe um ecossistema open-source bastante rico.

O ponto mais importante é este: em 2026, o equivalente aberto mais interessante ao sistema de conectores do ChatGPT é cada vez mais o **MCP - Model Context Protocol**. O MCP padroniza a conexão entre um host de IA e serviços externos, expondo **tools, resources e prompts**; a especificação atual também cobre OAuth, e o ecossistema já tem extensões para Skills. ([MCP TypeScript SDK](https://ts.sdk.modelcontextprotocol.io/v2/?utm_source=chatgpt.com))

### Os projetos que eu estudaria

| Projeto | Quão parecido com ChatGPT + Connectors | O que estudar nele | Licença |
|---|---:|---|---|
| **LibreChat** | ⭐⭐⭐⭐⭐ | MCP, OAuth, Agents, OpenAPI Actions, multiusuário, tool calling | MIT |
| **Open WebUI** | ⭐⭐⭐⭐⭐ | Tools, Functions, Pipes, Filters, Actions, Events, MCP, OpenAPI | licença própria/restrições |
| **AnythingLLM** | ⭐⭐⭐⭐½ | MCP, Agent Skills, seleção dinâmica de tools, agentes locais | MIT |
| **Dify** | ⭐⭐⭐⭐½ | Marketplace de plugins, providers, tools, agent strategies | Apache modificada |
| **Flowise** | ⭐⭐⭐⭐ | MCP, custom tools, workflows agentivos visuais | Apache 2.0 no core |
| **Jan** | ⭐⭐⭐½ | Host MCP desktop/local, routing de tools, permissões | Apache 2.0 |
| **Cherry Studio** | ⭐⭐⭐½ | Cliente desktop, agentes e ecossistema MCP | AGPL-3.0 |
| **LobeChat** | ⭐⭐⭐⭐ | Plugin Store, SDK de plugins, function calling | Apache modificada |

**LibreChat é provavelmente o melhor ponto de partida.** Ele se apresenta justamente como um clone avançado do ChatGPT e hoje combina Agents, MCP, OpenAPI Actions, Functions, Code Interpreter e autenticação multiusuário. O suporte a MCP contempla inclusive OAuth e isolamento em ambientes multiusuário. ([GitHub](https://github.com/danny-avila/LibreChat?utm_source=chatgpt.com))

[LibreChat no GitHub](https://github.com/danny-avila/LibreChat?utm_source=chatgpt.com)  
[Documentação MCP do LibreChat](https://www.librechat.ai/docs/features/mcp?utm_source=chatgpt.com)

**Open WebUI talvez seja o projeto mais interessante para estudar extensibilidade internamente.** Ele separa bem vários conceitos que no ChatGPT aparecem como uma coisa só: `Tools`, `Functions`, `Pipes`, `Filters`, `Actions` e `Events`. Além disso, suporta MCP HTTP nativamente, MCP stdio por proxy e serviços OpenAPI. ([Open WebUI](https://docs.openwebui.com/features/extensibility/plugin/tools/?utm_source=chatgpt.com))

Por exemplo, dá para enxergar conceitualmente algo assim:

```text
Open WebUI
│
├── Models
│
├── Native Tools
│
├── Workspace Tools
│   └── Python executado pelo modelo
│
├── Functions
│   ├── Pipes
│   ├── Filters
│   ├── Actions
│   └── Events
│
├── MCP
│   ├── HTTP
│   └── stdio → MCPO
│
└── OpenAPI
    └── REST APIs externas
```

Isso é excelente para entender como construir algo parecido com o sistema de Plugins do ChatGPT. Só existe uma ressalva: o Open WebUI atualmente usa uma licença própria com restrições de branding para determinados usos, então eu o trataria como **source-available/permissivo com restrições**, e não como o exemplo mais “puro” de open source OSI. ([GitHub](https://github.com/open-webui/open-webui/blob/main/LICENSE?utm_source=chatgpt.com))

[Open WebUI no GitHub](https://github.com/open-webui/open-webui?utm_source=chatgpt.com)

**AnythingLLM é particularmente interessante se o seu foco for agente + centenas de ferramentas.** Ele suporta servidores MCP e possui uma camada própria de `Agent Skills`. Mais interessante ainda: implementaram um sistema chamado **Intelligent Tool Selection**, que tenta selecionar apenas as ferramentas relevantes para uma interação, em vez de despejar todas as definições de tools no contexto do modelo. ([GitHub](https://github.com/Mintplex-Labs/anythingllm-docs/blob/main/pages/mcp-compatibility/overview.mdx?utm_source=chatgpt.com))

Esse problema é importantíssimo para estudar porque um agente com:

```text
GitHub    80 tools
Gmail     40 tools
Drive     60 tools
Calendar  25 tools
Trello    30 tools
Browser   20 tools
...
```

não deveria necessariamente enviar 255 schemas para o modelo a cada mensagem. AnythingLLM é MIT e seu core self-hosted permanece aberto. ([GitHub](https://github.com/mintplex-labs/anything-llm?utm_source=chatgpt.com))

[AnythingLLM no GitHub](https://github.com/Mintplex-Labs/anything-llm?utm_source=chatgpt.com)

**Dify vale muito a pena se sua pergunta for “como criar um verdadeiro ecossistema de plugins?”.** Desde o Dify 1.0, modelos e tools foram movidos para plugins. Existem diferentes tipos, incluindo **Model Providers, Tools e Agent Strategies**, além de Marketplace. ([GitHub](https://github.com/langgenius/dify-official-plugins?utm_source=chatgpt.com))

A estrutura conceitual é muito boa para estudar:

```text
Plugin
│
├── manifest
│
├── credentials
│
├── provider
│
├── tools
│   ├── search
│   ├── create
│   ├── update
│   └── delete
│
└── runtime
```

Eles têm inclusive scaffolding para desenvolvimento de novos Tool Plugins. ([GitHub](https://github.com/BenjaminX/dify-docs/blob/main/en/plugins/develop-plugins/tool-plugin.md?utm_source=chatgpt.com))

A ressalva novamente é licença: o Dify usa uma licença baseada na Apache 2.0, mas com condições adicionais, inclusive para determinados usos multi-tenant. ([GitHub](https://github.com/langgenius/dify?utm_source=chatgpt.com))

[Dify no GitHub](https://github.com/langgenius/dify?utm_source=chatgpt.com)

**Flowise é excelente para visualizar o problema.** Você consegue construir agentes visualmente, ligar tools, APIs e servidores MCP, e observar claramente onde termina o modelo e onde começa a ferramenta. O Custom MCP aceita servidores externos e descobre automaticamente as ações disponíveis. ([GitHub](https://github.com/FlowiseAI/FlowiseDocs/blob/main/en/tutorials/tools-and-mcp.md?utm_source=chatgpt.com)) O core é Apache 2.0, embora existam partes enterprise separadas. ([GitHub](https://github.com/FlowiseAI/Flowise/blob/main/LICENSE.md?utm_source=chatgpt.com))

[Flowise no GitHub](https://github.com/FlowiseAI/Flowise?utm_source=chatgpt.com)

**Jan é um ótimo projeto menor para entender um MCP Host.** Ele é um cliente desktop local e suporta servidores MCP, permissões para tool calls e até **Smart MCP Tool Routing** quando existem muitos servidores conectados. ([Jan](https://www.jan.ai/docs/desktop/integrations/mcp-servers?utm_source=chatgpt.com)) Isso o torna particularmente interessante se você quiser abrir o código e entender o caminho:

```text
mensagem
   ↓
modelo
   ↓
tool selection
   ↓
MCP client
   ↓
MCP server
   ↓
API / filesystem / banco / app
```

O projeto atual é Apache 2.0. ([GitHub](https://github.com/janhq/jan?lUBWSYbhbV7JF=ibdifvKV9&utm_source=chatgpt.com))

[Jan no GitHub](https://github.com/janhq/jan?utm_source=chatgpt.com)

### O projeto que eu estudaria antes de todos eles: MCP

Na realidade, eu não começaria copiando o sistema de plugins de nenhum desses projetos. Eu começaria estudando o **MCP SDK oficial**.

A arquitetura fundamental é muito pequena:

```text
┌──────────────────────────┐
│        AI HOST           │
│ LibreChat / Jan / etc.   │
└────────────┬─────────────┘
             │
         MCP Client
             │
   ┌─────────┴─────────┐
   │                   │
   ▼                   ▼
GitHub MCP          Gmail MCP
Server              Server
   │                   │
   ▼                   ▼
GitHub API          Gmail API
```

O servidor MCP declara coisas como:

```text
tools
resources
prompts
```

E um `tool` pode ser conceitualmente:

```json
{
  "name": "create_issue",
  "description": "Create a GitHub issue",
  "inputSchema": {
    "type": "object",
    "properties": {
      "repository": {
        "type": "string"
      },
      "title": {
        "type": "string"
      },
      "body": {
        "type": "string"
      }
    }
  }
}
```

O modelo recebe o schema, decide chamar:

```text
create_issue(
    repository="kevyn/hermes",
    title="Bug no router",
    body="..."
)
```

e o host encaminha aquilo para o MCP server.

O SDK TypeScript oficial atual é v2 e implementa a especificação MCP de julho de 2026. Há SDKs oficiais também para outras linguagens. ([MCP TypeScript SDK](https://ts.sdk.modelcontextprotocol.io/v2/?utm_source=chatgpt.com))

[MCP TypeScript SDK](https://ts.sdk.modelcontextprotocol.io/v2/?utm_source=chatgpt.com)  
[Registro oficial de servidores MCP](https://registry.modelcontextprotocol.io/?utm_source=chatgpt.com)

E agora a coisa ficou ainda mais interessante: o ecossistema MCP está indo além de simplesmente “funções”. Há **MCP Apps**, autorização OAuth e **Skills distribuídas via MCP**. ([Model Context Protocol](https://apps.extensions.modelcontextprotocol.io/api/documents/authorization.html?utm_source=chatgpt.com))

### Se seu objetivo for entender algo parecido com os Plugins atuais do ChatGPT

Eu faria esta sequência:

```text
1. MCP SDK
      ↓
 entender protocol / client / server

2. Jan
      ↓
 entender um MCP Host pequeno

3. LibreChat
      ↓
 entender host completo + OAuth + usuários

4. Open WebUI
      ↓
 entender extensibilidade profunda

5. AnythingLLM
      ↓
 entender tool routing / agent skills

6. Dify
      ↓
 entender marketplace + plugin lifecycle

7. Flowise
      ↓
 visualizar toda a orquestração
```

E existe uma distinção conceitual importante. Um sistema como o de Plugins/Connectors que você está vendo aqui não é simplesmente **“function calling”**. É mais próximo de:

```text
                    CONNECTOR PLATFORM

                         Registry
                            │
                            ▼
┌──────────┐          ┌─────────────┐
│   User   │─────────▶│   AI Host   │
└──────────┘          └──────┬──────┘
                             │
                    Tool discovery/router
                             │
              ┌──────────────┼──────────────┐
              ▼              ▼              ▼
           Gmail          GitHub          Drive
           Plugin         Plugin          Plugin
              │              │              │
           OAuth           OAuth           OAuth
              │              │              │
              ▼              ▼              ▼
          Gmail API       GitHub API      Drive API

                    + permission model
                    + secrets storage
                    + audit trail
                    + scopes
                    + user confirmation
                    + schemas
                    + retries
                    + citations
                    + UI components
                    + plugin lifecycle
```

É justamente essa camada intermediária que eu acho mais interessante estudar. **LibreChat + MCP SDK + AnythingLLM** formam, hoje, um trio especialmente bom para desmontar esse problema: LibreChat mostra a aplicação completa, o MCP mostra o protocolo e AnythingLLM mostra um problema de escala real - como selecionar ferramentas quando você possui dezenas ou centenas delas.

---

**Sources:**

- [MCP TypeScript SDK](https://ts.sdk.modelcontextprotocol.io/v2/?utm_source=chatgpt.com)
- [GitHub - danny-avila/LibreChat: Enhanced ChatGPT Clone: Features Agents, MCP, Skills, DeepSeek, Anthropic, AWS, OpenAI, Responses API, Azure, Groq, o1, GPT-5, Mistral, OpenRouter, Vertex AI, Gemini, Artifacts, AI model switching, message search, Code Interpreter, langchain, DALL-E-3, OpenAPI Actions, Functions, Secure Multi-User Auth, Presets, open-source for self-hosting. Active · GitHub](https://github.com/danny-avila/LibreChat?utm_source=chatgpt.com)
- [Tools / Open WebUI](https://docs.openwebui.com/features/extensibility/plugin/tools/?utm_source=chatgpt.com)
- [MCP Servers](https://www.jan.ai/docs/desktop/integrations/mcp-servers?utm_source=chatgpt.com)
- [Authorization | MCP Apps](https://apps.extensions.modelcontextprotocol.io/api/documents/authorization.html?utm_source=chatgpt.com)

## Prompt:
30/09/2026, 15:41:51

Coloca estes no matriz source do Hermes Work, está no [$github](app://connector_76869538009648d5b282a4bb21c3d157)&#x20;
Preciso estudar esses projetos

## Response:
30/09/2026, 15:41:57 · gpt-5-6-thinking

Vou localizar no repositório do Hermes Work o arquivo/trecho chamado **“matriz source”**, conferir o formato existente e adicionar os projetos como fontes de estudo — sem alterar a estrutura além do necessário.

Encontrei o arquivo canônico: `workstation/SOURCE_MATRIX.md`. Ele já separa “referência para estudo” de “decisão de adoção”, então vou inserir esses projetos numa seção própria de **plugins/connectors/MCP/tool routing**, mantendo-os como referências de pesquisa — não como dependências aprovadas.

Há dois detalhes relevantes para registrar na matriz: o antigo `lobehub/lobe-chat` hoje resolve para **`lobehub/lobehub`**, e o repositório **`FlowiseAI/Flowise` está marcado como arquivado** no GitHub. Vou preservar ambos como referências, mas deixar essas condições explícitas para evitar pesquisa em identidade/estado desatualizado.

> **Localizou e editou a matriz source no repositório Hermes Work**
>
> 
>
> **Organizando referências**
>
> Estou preparando uma atualização em `SOURCE_MAP.md`, adicionando a seção de conectores, hosts MCP e projetos relacionados. Vou preservar o formato existente e incluir notas de estudo, status dos repositórios e a ordem recomendada de leitura.
>
> **Organizou referências**
>
> 
>
> **Atualizou matriz com projetos de IA, repositórios GitHub e referências MCP**
>
> 
>
> **Atualizou a matriz de fontes do Hermes Work no GitHub**
>
> 
>
> Pensou por 2m 4s

Feito. Atualizei diretamente a `main` do `kevynlucasprofissional-stack/hermes-agent`.

No `workstation/SOURCE_MATRIX.md`, criei a seção **“Plugin / connector / MCP host references”** com:

- `modelcontextprotocol/typescript-sdk`
- `LibreChat-AI/LibreChat`
- `open-webui/open-webui`
- `Mintplex-Labs/anything-llm`
- `langgenius/dify`
- `janhq/jan`
- `CherryHQ/cherry-studio`
- `lobehub/lobehub` - identidade atual do antigo LobeChat
- `FlowiseAI/Flowise` - marcado explicitamente como **archived snapshot**

Também acrescentei uma **Wave D - plugins/connectors/MCP architecture**, priorizando o estudo nesta ordem aproximada:

**MCP SDK → LibreChat → AnythingLLM → Open WebUI → Dify → Jan → LobeHub → Cherry Studio → Flowise**

E incluí 9 perguntas de auditoria para cada projeto, cobrindo descoberta de tools, OAuth/credenciais, tool routing, confirmação de ações, schemas MCP/OpenAPI, retries/recovery, provenance, boundaries e o que realmente deveria pertencer ao Hermes Work.

Commit criado:

`a6a4d6d760618882739ecc0d23f6151b9951ec22`

Mensagem: `docs(workstation): add connector and MCP study references`

A matriz agora já está estruturada para transformar esse estudo em uma futura auditoria **código-a-código**, em vez de apenas uma lista de projetos.



---
Powered by [ChatGPT Exporter](https://www.chatgptexporter.com)