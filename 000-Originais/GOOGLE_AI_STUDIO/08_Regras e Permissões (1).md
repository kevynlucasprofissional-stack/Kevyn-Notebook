Com base na análise técnica de toda a documentação fornecida (Arquitetura de Agentes, Fluxos, Funcionalidades e Requisitos de Negócio), aqui estão as Regras do Sistema e a Matriz de Permissões estruturadas para o Ágora:

---

# Regras do Sistema

```text
- usuários possuem um plano de assinatura associado (Freemium, Standard, Pro ou Enterprise)
- o plano determina o limite diário de uploads de arquivos e o acesso a funcionalidades exclusivas
- cada interação de análise do usuário é registrada como uma nova "requisição" (UserRequest)
- o sistema utiliza uma arquitetura de multi-agentes para processar as análises, onde cada agente é especializado em um domínio (Sociocomportamental, Oferta, Performance)
- uploads de arquivos (UserUpload) devem ser transcritos/processados para alimentar o contexto do Agente Orquestrador
- o sistema gera uma resposta estruturada (AgentResponse) para cada etapa da análise, armazenada em JSONB para permitir reconstrução do fluxo
- o Agente Sintetizador (Estrategista-Chefe) é o responsável por consolidar todas as respostas dos especialistas em um único relatório executivo e campanha otimizada
- usuários podem avaliar o resultado gerado pela IA (Like/Deslike) após a entrega do relatório
- integrações com API da Meta são exclusivas para o plano Enterprise
- usuários podem baixar materiais gerados (PDF, PPT, PNG, etc.) conforme os limites do plano
- o sistema deve validar a disponibilidade de recursos (limite de uploads) no banco de dados antes de processar novas análises
```

---

# Permissões

Aqui estão as permissões divididas pelos perfis de usuário do sistema:

```text
visitante (não autenticado)
- visualizar landing page
- visualizar tabela de planos
- iniciar fluxo de chat (limitado ao onboarding de avaliação gratuita)

usuário freemium
- realizar até 2 uploads por dia
- solicitar análise de campanha (core engine)
- visualizar relatório executivo básico
- avaliar resultados da IA

usuário standard
- realizar até 5 uploads por dia
- acessar funcionalidades de audiência sintética
- solicitar análise de campanha (core engine)
- visualizar relatório executivo completo
- avaliar resultados da IA

usuário pro
- realizar uploads ilimitados
- solicitar análise de campanha (core engine)
- acessar funcionalidades de audiência sintética
- acessar templates avançados para redes sociais
- avaliar resultados da IA

usuário enterprise
- realizar uploads ilimitados
- solicitar análise de campanha (core engine)
- acessar funcionalidades de audiência sintética
- acessar histórico de feedbacks e contextos personalizados por empresa
- realizar vinculação com APIs externas (Meta Ads/Pixel/Conversions API)
- visualizar dashboard com métricas de negócio e previsibilidade
```