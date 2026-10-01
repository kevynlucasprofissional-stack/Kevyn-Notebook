---
id: changelog-do-vault
titulo: Changelog do vault
tipo: changelog
status: auditado
profundidade: indice
versao_schema: '1.0'
versao_conteudo: '1.7'
idioma: pt-BR
data_criacao: 2026-06-17
ultima_revisao: 2026-09-29
grau_confianca: alto
sensibilidade: baixa
camada_evidencia: documento_operacional
tags:
- tipo/changelog
- infraestrutura
---

# Changelog do vault

## 1.0 — 17 de junho de 2026

- inspecionado integralmente o ZIP recebido;
- preservado o arquivo original;
- criada ontologia de autobiografia, fontes, eventos, relações, projetos, temas, hipóteses e infraestrutura;
- produzidas notas temáticas com camadas de evidência e sensibilidade;
- criados MOCs, trilhas, Bases, consultas Dataview, Kanban, templates e Canvas;
- preparado protocolo de auditoria e release.

Correções técnicas finais são registradas também no arquivo externo `Changelog.md`.

## 1.1 — 30 de junho de 2026

- reconciliacao de `Manifesto-Fontes.csv` com `Matriz-Cobertura.csv` usando representante canonico para duplicatas exatas;
- criacao e ajuste de `Matriz-Evidencias.csv` e expansao de `Matriz-Claims.csv`;
- realinhamento de `Kevyn Lucas`, `Claims principais`, `MOC Fontes e evidencias` e `MOC Perfil e autoconhecimento` com a nova camada de controle;
- `Hoor Digital` mantido como referencia de manifesto no recorte ativo, sem arquivo materializado no root ativo;
- checksums finais foram regenerados no encerramento do ciclo.


## 1.2 — 28 de setembro de 2026

- adicionados `README.md` e `AGENTS.md` na raiz como documentação central do repositório;
- formalizada a separação entre `000-Originais/` como camada de fontes preservadas e a estrutura ativa como camada canônica de conhecimento;
- definido o princípio de memória cumulativa: novas fontes devem enriquecer estruturas canônicas existentes antes de gerar notas isoladas;
- incorporadas regras operacionais de compatibilidade Obsidian, proveniência, epistemologia, links semânticos, YAML e segurança;
- vinculado como referência metodológica o `Playbook-Construcao-de-Cofres-no-Obsidian.md`, preservando a prioridade das convenções específicas já consolidadas em `97-Infraestrutura/`.

## 1.3 — 28 de setembro de 2026

- criado `98-Pendencias-e-controles/Controle-Curadoria-Originais/` como controle central da camada `000-Originais/`;
- inventariados 12.475 arquivos atuais da camada original em `Controle-Curadoria-Originais.csv`;
- definida escala de relevância 0–10, estados de análise/integração e política explícita de que nota 0 não autoriza exclusão;
- criada fila dinâmica de alta relevância ainda não utilizada por meio de `Painel de curadoria dos originais.md`;
- reconciliados 2.827 caminhos com a `Matriz-Cobertura.csv` anterior, preservando 2.827 SHA-256 conhecidos sem converter arbitrariamente relevância legada em nota numérica;
- `README.md` e `AGENTS.md` atualizados para tornar o controle obrigatório durante a curadoria de fontes originais.

## 1.4 — 28 de setembro de 2026

- criado `roadmap.md` na raiz como plano central de evolução do Kevyn Notebook;
- formalizada como etapa obrigatória a classificação e curadoria progressiva de todos os arquivos de `000-Originais/`;
- definida priorização inicial de 50–100 fontes autobiográficas de maior valor antes da leitura sequencial do acervo;
- incorporados ao roadmap reconstrução autobiográfica verificável, análise longitudinal, recorrências, genealogia de ideias, memória de decisões, mapa de projetos/vocação, arquivo criativo e assistente fundamentado;
- adicionados como objetivos historiografia pessoal, snapshots temporais, diffs autobiográficos, comparação entre discurso e trajetória e sistema de perguntas;
- documentados princípios contra congelamento de identidade e contra uso de frequência documental como prova de essência;
- `README.md` e `AGENTS.md` passam a apontar para o roadmap como referência de prioridades de evolução.

## 1.5 — 28 de setembro de 2026

- concluído o pré-processamento inicial de fontes autobiográficas prioritárias;
- criada `98-Pendencias-e-controles/Controle-Curadoria-Originais/Pré-seleção de 70 fontes prioritárias.md`;
- aplicados dois filtros à seleção: sinais estruturais por nome/pasta e validação semântica por leitura direta no GitHub;
- definidos 25 arquivos P0, 25 P1 e 20 P2, sem converter prioridade em relevância oficial 0–10;
- documentados exemplos de falsos positivos de filename rebaixados após leitura de conteúdo;
- Fase 2 do `roadmap.md` atualizada para registrar como concluída a definição da primeira fila de 50–100 fontes;
- `AGENTS.md` e o README do controle passam a apontar para a pré-seleção antes de curadoria arbitrária do acervo;
- registrado alerta de segurança para materiais originais que contenham credenciais, mantendo-os fora da integração canônica.

## 1.6 — 29 de setembro de 2026

- registrada a curadoria Tier A de 28/09/2026 (notas-fonte + integração em `Kevyn Lucas`, `Linha do tempo mestre`, `Claims principais`, `Matriz-Claims.csv` e `Matriz-Evidencias.csv`);
- reconciliada a camada canônica: 97 notas ausentes foram restauradas a partir de `000-Originais/EXPORT_HTML/Kevyn Lucas/` (Vault canônico anterior preservado como original), mantendo sempre as versões ativas mais recentes (`Kevyn Lucas`, `Claims principais`, `MOC Geral`, `Linha do tempo mestre` etc.);
- links internos do Vault ativo reconciliados: de ~1.268 wikilinks quebrados para 0 (descontados falsos positivos em code spans e alvos legítimos que resolvem em `Processamento-Automatico` e `.json`);
- `README.md` atualizado para listar as áreas canônicas `05-Sonhos-Simbolos-e-Espiritualidade/` e `07-Planos-e-Decisoes/`;
- `MOC Geral` atualizado (v2.3) para referenciar o snapshot `Estado atual - setembro de 2026`;
- `roadmap.md` (v1.2) corrige a FASE 2 (Tier B concluído; Tier C restante referenciado na pré-seleção) e registra a contagem real de originais (12.433 em 29/09/2026);
- `Preselecao-Fontes-Autobiograficas-Prioritarias` corrigido (corpus real, 150 lidos, 68 Tier C pendentes);
- `Pré-seleção de 70 fontes prioritárias` marcado como superado e apontando para o documento sucessor;
- correção de segurança: removidas credenciais em texto claro das fontes originais, sem replicação para a camada canônica;
- retirados do índice do Obsidian os backups de notas canônicas do legado de integração: 13 pastas `Backups-Antes` passaram a `.Backups-Antes` (ignoradas por dot-folder) e `Controle-Integracao/` e `Controle-Revisao-100/` foram adicionados a `userIgnoreFilters`, eliminando ambiguidade de basenames no Obsidian sem remover o histórico do Git;
- `Controle-Curadoria-Originais.csv` passou a registrar a proveniência do Vault canônico anterior (`000-Originais/EXPORT_HTML/Kevyn Lucas/`): 123 notas marcadas, sendo 99 `utilizado_na_canonica = sim` (`integrado_legado`) e 24 `parcial` (`integrado_parcialmente_legado`);
- verificação de conteúdo concluiu que não há fato ou claim do export ausente da camada canônica: as diferenças remanescentes são formulações anteriores superadas pela estrutura CLM/EVD ou formatação de tabelas;
- documentado o modelo de três zonas — originais (`000-Originais/`), canônica (`00`–`08`) e operacional (`09`–`99`), com `80-MOCs-e-Trilhas/` híbrido — em `README.md` e `AGENTS.md`;
- verificado que nenhuma nota do legado de integração (`Controle-Integracao`, `Controle-Revisao-100`) precisa ser promovida à camada canônica: os arquivos com nome canônico são snapshots anteriores, e o único candidato aparente (`Sirio`) já foi resolvido como corruptela de transcrição de ACIRV na própria nota-fonte.

## 1.7 — 29 de setembro de 2026

- incorporadas novas fontes primárias de relações a partir dos originais:
  - `Fonte - Conversa do WhatsApp com Cha e Prosa` (grupo, 18/10–26/11/2025; criado por Mari que Cria em 17/10/2025);
  - `Fonte - Cha e Prosa transcricao de encontro` (roda temática "o que gosto em mim");
  - `Fonte - Conversa do WhatsApp com Iasmim` (19–22/06/2026);
  - `Fonte - Conversa do WhatsApp com Mari que Cria` (18/10–26/11/2025);
- criada a nota canônica `Iasmin Alencar` para a relação afetiva de jun–jul/2026 e registrada a **disambiguação** com `Yasmin` (prima de Kevyn, mãe de Hariel) em ambas as notas e na nota-fonte da sessão de 10/07/2026;
- `Linha do tempo mestre`, `Kevyn Lucas`, `Estado atual - setembro de 2026`, `Rede de relacoes`, `Claims principais` e `Matriz-Claims.csv` passam a referenciar `Iasmin Alencar`, eliminando a ambiguidade de nome;
- `Cha e Prosa` (v2.3) passa a datar a criação do grupo (17/10/2025) e a listar as novas fontes;
- `Mari e a experiencia de idealizacao` (v1.5) ganha afirmação sustentada por fonte primária sobre a parceria criativa (edital Centelha, "Muralistas do Futuro", Ateliê Ciranda);
- links internos permanecem em 0 quebrados;
- aprofundadas as fontes de relacionamento: `Cha e Prosa` (cronologia out–nov/2025, ação solidária, cozinha coletiva, votação de temas) e `Mari e a experiencia de idealizacao` (cronologia do edital Centelha, "Muralistas do Futuro", Ateliê Ciranda);
- criada `Auditoria de saude da camada canonica 2026-09-29` (`95-Auditorias/`): 130 notas canônicas, 0 links quebrados, 2 órfãos corrigidos, 8 MOCs com defasagem de revisão, lacunas temporais em 2022 e 2004–2017, sem duplicação semântica real;
- `MOC Relacionamentos e rede` (v1.8) atualizado com `Aline e o ciclo de reciprocidade e ritmo` e `Iasmin Alencar`.
