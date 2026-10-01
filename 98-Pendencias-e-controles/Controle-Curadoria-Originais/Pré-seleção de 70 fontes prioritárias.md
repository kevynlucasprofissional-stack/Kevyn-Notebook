---
id: preselecao-fontes-prioritarias
titulo: Pré-seleção de 70 fontes prioritárias
tipo: controle_curadoria
status: superado
profundidade: avancada
versao_schema: "1.0"
versao_conteudo: "1.1"
idioma: pt-BR
data_criacao: 2026-09-28
ultima_revisao: 2026-09-29
tags:
  - curadoria/fontes
  - fila/prioritaria
  - autobiografia
---

# Pré-seleção de 70 fontes prioritárias

> [!warning] Documento superado — uso apenas histórico
> Esta pré-seleção foi substituída por [[Preselecao-Fontes-Autobiograficas-Prioritarias]] (218 candidatos no Filtro 1; 83 fontes Tier A+B selecionadas; Tier B concluído). A fila viva de curadoria está no documento sucessor e em `Controle-Curadoria-Originais.csv`. As caixas não marcadas abaixo pertencem ao pré-processamento inicial e **não** representam pendências atuais.

## Estado

**Pré-processamento inicial concluído.**

Foram definidos **70 arquivos prioritários** para a primeira grande rodada de curadoria do Kevyn Notebook.

Esta lista **não substitui** a avaliação oficial de relevância 0–10 em `Controle-Curadoria-Originais.csv`. Ela serve para decidir **onde começar**.

Todos os 70 arquivos abaixo passaram por dois filtros:

1. **Filtro estrutural:** nome do arquivo, nome das pastas, tipo aparente de fonte, período e contexto;
2. **Filtro semântico:** leitura/amostragem direta do conteúdo no repositório GitHub para confirmar que o arquivo realmente contém material autobiográfico, contextual ou interpretativo útil.

> [!important]
> "Leitura/amostragem" neste pré-processamento significa leitura suficiente para validar a natureza e a prioridade do documento. **Não significa curadoria integral**, extração completa de claims ou atribuição definitiva de relevância 0–10.

---

## Filtro 1 — Estrutura, nomes e contexto

### Sinais positivos

Receberam prioridade estrutural arquivos/pastas associados a:

- diários e transcrições autobiográficas;
- sessões psicológicas e registros de conversa direta;
- cartas e textos escritos pelo próprio Kevyn;
- datas e registros contemporâneos;
- missão, identidade, valores, vontade e decisões;
- relações importantes;
- trabalho e vocação quando documentam a trajetória de Kevyn;
- autorregulação e revisões comportamentais;
- reconstruções biográficas e sínteses com proveniência recuperável.

### Sinais negativos

Foram rebaixados:

- livros e PDFs apenas consumidos;
- materiais de curso sem conteúdo autobiográfico;
- documentação técnica genérica;
- arquivos de plugin/cache/configuração;
- prompts sem resposta substancial;
- material vazio;
- cópias evidentemente derivadas quando existe fonte mais direta;
- análises que fazem afirmações fortes sem permitir recuperar a fonte primária.

---

## Filtro 2 — Conteúdo lido diretamente no GitHub

O segundo filtro alterou a seleção em vários casos.

### Exemplos confirmados

A leitura direta confirmou valor muito alto em grupos como:

- `Dados Kevyn/Diários/`;
- `DIARIO_EM_AUDIO/`;
- `Diário provisório do kevyn/`;
- transcrições das sessões com Psicóloga Suzana;
- cartas e reflexões autorais na raiz de `000-Originais/`;
- registros de missão, valores, ética, trabalho e relações;
- revisões de autorregulação que preservam datas e fatos observáveis.

### Exemplos rebaixados pelo conteúdo

Alguns nomes pareciam muito promissores, mas foram retirados da lista principal após leitura:

- `GOOGLE_AI_STUDIO/Análise Comportamental de Kevyn Lucas` — conteúdo predominantemente voltado à construção de prompt;
- `GOOGLE_AI_STUDIO/Análise de Lacunas Psicológicas de Kevyn` — predominantemente engenharia de prompt;
- `GOOGLE_AI_STUDIO/Análise Junguiana de Kevyn Lucas` — predominantemente engenharia de prompt;
- `GOOGLE_AI_STUDIO/Aline` — arquivo sem conteúdo útil no estado atual;
- materiais de estudo externos com pouca ou nenhuma informação sobre Kevyn.

Isso confirma por que **nome de arquivo sozinho não é suficiente**.

---

## Como interpretar P0, P1 e P2

Essas classes são **prioridade de processamento**, não nota de relevância.

- **P0 — núcleo autobiográfico:** começar por aqui; fontes diretas e temporalmente ricas;
- **P1 — alta prioridade:** amplia períodos, ideias, decisões, trabalho e relações;
- **P2 — contraste e síntese:** fontes derivadas ou mistas úteis para localizar hipóteses, conflitos e lacunas.

A nota oficial `relevancia = 0–10` só deve ser atribuída durante a curadoria real de cada arquivo.

---

## Lista prioritária

| # | Fila | Natureza | Caminho | Motivo da pré-seleção | Núcleo canônico provável |
|---:|---|---|---|---|---|
| 1 | P0 | primária | `000-Originais/COFRE_KEVYN_LUCAS/Dados brutos/Sessões com Psicóloga Suzana/120626 às 09h/120626 às 9h - Reunião com a Psicóloga Suzana - Transcrição.md` | registro biográfico e histórico pessoal em conversa direta | 01 Perfil; 02 Cronologia; 06 Autocuidado |
| 2 | P0 | primária | `000-Originais/COFRE_KEVYN_LUCAS/Dados brutos/Sessões com Psicóloga Suzana/260626 às 16h/260626 às 16h - Reunião com a Psicóloga Suzana - Transcrição.txt` | sessão direta com temas de vínculo, controle, história e objetivos terapêuticos | 01 Perfil; 02 Cronologia; 06 Autocuidado |
| 3 | P0 | primária | `000-Originais/COFRE_KEVYN_LUCAS/Dados brutos/Sessões com Psicóloga Suzana/100726 às 7h/100726 Sessão com a psicologa Suzanna.txt` | sessão direta com passado, rotina, relações e estado contemporâneo | 01 Perfil; 02 Cronologia; 06 Autocuidado |
| 4 | P0 | primária | `000-Originais/Dados Kevyn/Diários/Diário Negro 01 - 241225 até 130226.md` | diário longitudinal direto atravessando vida, trabalho, corpo, desejo e projetos | 02 Cronologia; 01 Perfil; 04 Trabalho |
| 5 | P0 | primária | `000-Originais/Dados Kevyn/Diários/Diário negro 02 - 130226 até 250426.md` | diário longitudinal direto com origem familiar, autointerpretação e transformação | 02 Cronologia; 01 Perfil; 06 Autocuidado |
| 6 | P0 | primária | `000-Originais/Dados Kevyn/Diários/00 Diário Parte 01 parte 02.txt` | registro histórico de 2023 com espiritualidade, missão, ações e formação de valores | 02 Cronologia; 01 Perfil; 08 Estudos |
| 7 | P0 | primária | `000-Originais/Dados Kevyn/Diários/00 Diário Parte 01 parte 03.txt` | registro histórico de 2024 com diálogo interior, metas e identidades aspiracionais | 02 Cronologia; 01 Perfil |
| 8 | P0 | primária | `000-Originais/Dados Kevyn/Diários/Diário em audio - Parte 01.txt` | transcrição autobiográfica direta sobre disciplina, rotina, estudo e trabalho | 02 Cronologia; 06 Autocuidado; 04 Trabalho |
| 9 | P0 | primária | `000-Originais/Dados Kevyn/Diários/Diário em audio - Parte 02.md` | transcrição direta sobre origem econômica, tempo, produtividade e construção de si | 02 Cronologia; 04 Trabalho; 01 Perfil |
| 10 | P0 | primária | `000-Originais/Dados Kevyn/Diários/Diário em audio - Parte 03.md` | transcrição direta sobre vida cotidiana, relações, aparência e valores | 02 Cronologia; 01 Perfil; 03 Relações |
| 11 | P0 | primária | `000-Originais/Diário provisório do kevyn/030826.md` | diário contemporâneo denso sobre relação, intensidade, autoconhecimento e escrita | 02 Cronologia; 03 Relações; 01 Perfil |
| 12 | P0 | primária | `000-Originais/Diário provisório do kevyn/090826.md` | registro direto de passagem de análise para ação e síntese de autoconhecimento | 01 Perfil; 02 Cronologia; 06 Autocuidado |
| 13 | P0 | primária | `000-Originais/Diário provisório do kevyn/290726 Impressões sobre o rolê de agora com a Aline.md` | registro contemporâneo imediato de necessidades e sentimentos após encontro | 03 Relações; 02 Cronologia; 01 Perfil |
| 14 | P0 | primária | `000-Originais/Diário provisório do kevyn/260726 Um tratado sobre ética do Kevyn.md` | formulação autoral extensa de ética, vontade, relações e direção de vida | 01 Perfil; 08 Estudos; 02 Cronologia |
| 15 | P0 | primária | `000-Originais/270926.md` | diário direto sobre comportamento, identidade, realidade e herói contemporâneo | 01 Perfil; 02 Cronologia; 08 Estudos |
| 16 | P0 | primária | `000-Originais/Um contrato comigo mesmo.md` | contrato de identidade e valores datado, com revisão no dia seguinte | 01 Perfil; 02 Cronologia; 06 Autocuidado |
| 17 | P0 | primária | `000-Originais/Carta a Aline (Talvez nunca será entregue).md` | carta autoral extensa com memória relacional, afetos e narrativa dos encontros | 03 Relações; 02 Cronologia; 01 Perfil |
| 18 | P0 | primária | `000-Originais/A lenda do Rei do Graal (Como contei para a Aline).md` | transcrição de conversa e história simbólica escrita por Kevyn em contexto relacional | 03 Relações; 01 Perfil; 02 Cronologia |
| 19 | P0 | primária | `000-Originais/Missão da minha vida.md` | formulação direta de missão, competências, estudo e direção profissional | 04 Trabalho; 08 Estudos; 01 Perfil |
| 20 | P0 | primária/mista | `000-Originais/Sobre a relação do Kevyn com a Caridade.md` | preserva pensamento atual e versão anterior, ideal para genealogia de ideias | 01 Perfil; 08 Estudos; 02 Cronologia |
| 21 | P0 | primária | `000-Originais/É uma história sobre uma criança que foi abandonado.md` | ficção explicitamente baseada na própria vida e em temas autobiográficos | 01 Perfil; 02 Cronologia; 10 Arquivo criativo |
| 22 | P0 | primária | `000-Originais/DIARIO_EM_AUDIO/080626 00h00.txt` | revisão autobiográfica direta sobre legado, desejo, dispersão, arquétipos e direção | 06 Autocuidado; 01 Perfil; 02 Cronologia |
| 23 | P0 | primária | `000-Originais/DIARIO_EM_AUDIO/220626 04h42.txt` | revisão semanal direta cruzando trabalho, terapia, relações, estudo e hábitos | 06 Autocuidado; 04 Trabalho; 02 Cronologia |
| 24 | P0 | primária | `000-Originais/DIARIO_EM_AUDIO/150626 05h25.txt` | revisão semanal direta com execução profissional, estudo e autorregulação | 06 Autocuidado; 04 Trabalho; 02 Cronologia |
| 25 | P0 | primária | `000-Originais/DIARIO_EM_AUDIO/050626 04h47.txt` | confissão/reflexão direta sobre autogestão, pensamento, verdade e virtudes | 06 Autocuidado; 01 Perfil; 08 Estudos |
| 26 | P1 | primária | `000-Originais/DIARIO_EM_AUDIO/060626 01h20.txt` | registro observável de trabalho, rotina, estudo e dispersão | 04 Trabalho; 06 Autocuidado; 02 Cronologia |
| 27 | P1 | primária | `000-Originais/DIARIO_EM_AUDIO/310526 23h43.txt` | inventário direto de projetos, corpo, estudo e decisões de execução | 04 Trabalho; 06 Autocuidado; 02 Cronologia |
| 28 | P1 | primária | `000-Originais/DIARIO_EM_AUDIO/310526 23h52 Framework.txt` | formulação direta do sistema de acompanhamento comportamental | 06 Autocuidado; 01 Perfil |
| 29 | P1 | primária | `000-Originais/Diário provisório do kevyn/020826.md` | diário direto sobre amor, tarot, controle, autocuidado e autoimagem | 03 Relações; 01 Perfil; 02 Cronologia |
| 30 | P1 | primária | `000-Originais/Diário provisório do kevyn/070626.md` | registro direto sobre Aline, intensidade, Jung e integração psíquica | 03 Relações; 01 Perfil; 02 Cronologia |
| 31 | P1 | mista | `000-Originais/Diário provisório do kevyn/050926 22h17 Plano de estudo dos próximos meses.md` | plano fundamentado em dados do próprio corpus, útil para vocação e estado atual | 04 Trabalho; 08 Estudos; 02 Cronologia |
| 32 | P1 | mista | `000-Originais/Diário provisório do kevyn/050926 Avaliação de áreas de conhecimento e competências.md` | snapshot recalibrado de competências com critérios e evidências | 04 Trabalho; 08 Estudos; 01 Perfil |
| 33 | P1 | primária | `000-Originais/Diário provisório do kevyn/010826.md` | registro contemporâneo de responsabilidade relacional e autorregulação | 03 Relações; 06 Autocuidado; 02 Cronologia |
| 34 | P1 | primária | `000-Originais/Diário provisório do kevyn/070926.md` | autodefinições profissionais/mitopoéticas e reflexão sobre influência relacional | 01 Perfil; 04 Trabalho; 02 Cronologia |
| 35 | P1 | primária | `000-Originais/Diário provisório do kevyn/110726.md` | registro granular de foco, disciplina, ACIRV, corpo e auto-observação | 06 Autocuidado; 04 Trabalho; 02 Cronologia |
| 36 | P1 | primária | `000-Originais/Diário provisório do kevyn/110826.md` | versão datada da carta e memória da relação, útil para historiografia relacional | 03 Relações; 02 Cronologia |
| 37 | P1 | primária | `000-Originais/Diário provisório do kevyn/160826.md` | síntese autoral de valores, força, integração e direção interior | 01 Perfil; 08 Estudos; 02 Cronologia |
| 38 | P1 | primária | `000-Originais/Diário provisório do kevyn/200726.md` | registro direto de trabalho, relação, responsabilidade e revisão de conduta | 03 Relações; 04 Trabalho; 02 Cronologia |
| 39 | P1 | primária | `000-Originais/Diário provisório do kevyn/250726.md` | registro direto sobre vínculo, impermanência e distribuição de necessidades | 03 Relações; 01 Perfil; 02 Cronologia |
| 40 | P1 | primária | `000-Originais/Diário provisório do kevyn/270826.md` | autodescrição direta de gostos, missão e linguagem de vontade | 01 Perfil; 04 Trabalho; 02 Cronologia |
| 41 | P1 | primária/mista | `000-Originais/Diário provisório do kevyn/300826.md` | framework autoral sobre observação, experimento e ajuste de comportamento | 06 Autocuidado; 01 Perfil |
| 42 | P1 | primária | `000-Originais/Dados Kevyn/Diários/00 diario parte final.m4a.txt` | registro histórico de 2024 sobre missão, carreira, disciplina e espiritualidade | 02 Cronologia; 04 Trabalho; 01 Perfil |
| 43 | P1 | primária | `000-Originais/Dados Kevyn/Diários/00 Diário gravity falls - 170625.m4a.txt` | registro poético histórico de 2024, útil para evolução de linguagem simbólica | 02 Cronologia; 01 Perfil; 08 Estudos |
| 44 | P1 | secundária | `000-Originais/arquetipos do Kevyn.md` | síntese simbólica baseada em sessões e registros; útil como mapa de hipóteses, não como fato | 01 Perfil; 03 Relações |
| 45 | P1 | secundária | `000-Originais/Por qual motivo Kevyn é como é.md` | síntese interpretativa de autonomia, potência, pertencimento e trabalho | 01 Perfil; 04 Trabalho; 03 Relações |
| 46 | P1 | secundária/mista | `000-Originais/Prosperidade do Kevyn.md` | síntese econômica/profissional ancorada em evidências de trabalho recente | 04 Trabalho; 02 Cronologia |
| 47 | P1 | mista | `000-Originais/Aline e Kevyn - Quando Kevyn profetizou.md` | preserva mensagem direta antiga e posterior interpretação da trajetória relacional | 03 Relações; 02 Cronologia |
| 48 | P1 | primária | `000-Originais/Carta a Aline.md` | versão mais condensada da carta; útil para comparar reescritas e narrativa relacional | 03 Relações; 02 Cronologia |
| 49 | P1 | mista | `000-Originais/Pensamento e experiência.md` | registro filosófico voltado ao self, experiência e silêncio; útil para genealogia de ideias | 01 Perfil; 08 Estudos |
| 50 | P1 | primária/mista | `000-Originais/Resumindo toda a Thelema ou como se tornar um Magus.md` | formulação pessoal de trabalho, sabedoria, transcendência e dever | 01 Perfil; 08 Estudos |
| 51 | P2 | secundária | `000-Originais/Vontade SMART/010626 - Revisão de Autorregulação.md` | síntese estruturada da própria transcrição, projetos e obstáculos comportamentais | 06 Autocuidado; 04 Trabalho |
| 52 | P2 | secundária | `000-Originais/Vontade SMART/050626 - Revisão de Autorregulação.md` | revisão datada com evidências comportamentais e execução | 06 Autocuidado; 04 Trabalho; 02 Cronologia |
| 53 | P2 | secundária | `000-Originais/Vontade SMART/060626 - Revisão de Autorregulação.md` | contraste entre execução profissional e regulação pessoal | 06 Autocuidado; 04 Trabalho; 02 Cronologia |
| 54 | P2 | secundária | `000-Originais/Vontade SMART/070626 - Revisão de Autorregulação.md` | revisão de continuidade, execução e dispersão | 06 Autocuidado; 04 Trabalho; 02 Cronologia |
| 55 | P2 | secundária | `000-Originais/Vontade SMART/150626 - Revisão de Autorregulação.md` | síntese semanal com fatos profissionais e pessoais | 06 Autocuidado; 04 Trabalho; 02 Cronologia |
| 56 | P2 | secundária | `000-Originais/Vontade SMART/220626 - Revisão de Autorregulação.md` | síntese semanal cruzando trabalho, vida doméstica, projetos e autocuidado | 06 Autocuidado; 04 Trabalho; 02 Cronologia |
| 57 | P2 | primária/simbólica | `000-Originais/Dados Kevyn/Outros/Não integrados/Conversa com minha alma.md` | texto autoral datado de 2024 com diálogo interior e projetos identitários | 01 Perfil; 02 Cronologia; 08 Estudos |
| 58 | P2 | secundária/mista | `000-Originais/Dados Kevyn/Outros/Integrados/Diário de Vitórias.md` | lista narrativa de marcos; útil como índice de eventos a verificar nas fontes | 02 Cronologia; 01 Perfil; 04 Trabalho |
| 59 | P2 | secundária | `000-Originais/Dados Kevyn/Outros/Integrados/Análise de Kevyn - 14.01.md` | análise de cognição/metacognição baseada em monólogo; boa pista para claims | 01 Perfil; 08 Estudos |
| 60 | P2 | secundária | `000-Originais/Dados Kevyn/Outros/Integrados/Autópsia do Kevyn.md` | síntese ampla alimentada por vários documentos; útil como mapa, requer retorno às fontes | 01 Perfil; 03 Relações; 04 Trabalho |
| 61 | P2 | secundária | `000-Originais/Dados Kevyn/Outros/Integrados/Contexto extra sobre Kevyn.md` | compilação ampla de materiais interpretativos; útil para localizar temas e fontes | 01 Perfil; 03 Relações |
| 62 | P2 | secundária | `000-Originais/Dados Kevyn/Outros/Integrados/Kevyn Lucas - Manual de Instruções.md` | autoimagem/síntese relacional derivada, útil como documento de narrativa sobre si | 01 Perfil; 03 Relações |
| 63 | P2 | secundária | `000-Originais/Dados Kevyn/Outros/Integrados/Sobre a Mari e ser vulnerável.md` | interpretação relacional centrada em vulnerabilidade; usar apenas como hipótese derivada | 03 Relações; 01 Perfil |
| 64 | P2 | secundária | `000-Originais/Dados Kevyn/Outros/Integrados/Sobre a simbiose romântica, minhas tribos e a Odisséia psicológica.md` | síntese extensa sobre relação/tribo/projeção; útil para identificar fontes e hipóteses | 03 Relações; 01 Perfil |
| 65 | P2 | secundária | `000-Originais/Dados Kevyn/Outros/Não integrados/Kevyn vs. Renata - Uma Mudança.md` | análise comparativa de trajetória profissional a partir de conversas operacionais | 04 Trabalho; 02 Cronologia |
| 66 | P2 | secundária | `000-Originais/Dados Kevyn/Outros/Não integrados/O discurso não substitui a história; ele é parte dela..md` | metanota útil para separar narrativa de evidência histórica | 01 Perfil; 02 Cronologia; 09 Evidências |
| 67 | P2 | mista | `000-Originais/Sobre o Kevyn/Contexto sobre Aline.md` | conversa exportada com texto direto de Kevyn e análise posterior | 03 Relações; 02 Cronologia |
| 68 | P2 | secundária | `000-Originais/Sobre o Kevyn/ChatGPT-Autoconhecimento sobre você-20260906-0238.md` | síntese cross-corpus recente que diferencia fato e hipótese; usar como índice, não como fonte final | 01 Perfil; 09 Evidências |
| 69 | P2 | secundária | `000-Originais/GOOGLE_AI_STUDIO/Biografia  Fatos Sobre Infância E Origem` | conversa JSON com tentativa de biografia e referências a arquivos anteriores | 02 Cronologia; 01 Perfil; 09 Evidências |
| 70 | P2 | secundária/mista | `000-Originais/CODEX_KEVYN/ACIRV/Notas/110326 - Insight completo sobre como estou usando meu tempo.md` | análise baseada em registro real de tempo; cobre funcionamento profissional cotidiano | 04 Trabalho; 06 Autocuidado; 02 Cronologia |

---

## Ordem recomendada de execução

### Lote A — P0

- [ ] ler integralmente os 25 arquivos P0;
- [ ] atribuir relevância 0–10;
- [ ] extrair eventos, datas, relações, decisões, projetos e autodescrições;
- [ ] registrar evidências e claims;
- [ ] enriquecer a camada canônica existente;
- [ ] atualizar `Controle-Curadoria-Originais.csv`.

### Lote B — P1

- [ ] repetir o processo para os 25 arquivos P1;
- [ ] comparar versões temporais da mesma narrativa;
- [ ] identificar alterações de valores, identidade, trabalho e relações.

### Lote C — P2

- [ ] usar os 20 arquivos P2 principalmente como **mapas de busca e contraste**;
- [ ] retornar às fontes primárias sempre que uma síntese fizer afirmação relevante;
- [ ] não promover interpretação de IA a fato apenas por repetição.

---

## Critério de sucesso deste pré-processamento

A tarefa **"definir os primeiros 50–100 arquivos mais importantes" está concluída** no nível de pré-seleção.

O que ainda não está concluído:

- leitura integral de todos os 70;
- relevância oficial 0–10;
- integração canônica de todos;
- extração exaustiva de evidências/claims;
- comparação de cada fonte com todo o conhecimento já existente.

A próxima tarefa é transformar esta lista de **prioridade presumida validada por amostragem** em **curadoria efetivamente concluída**.

---

## Observação sobre segurança

Durante a leitura do segundo filtro foi encontrado pelo menos um documento operacional original contendo **credenciais em texto claro**. Esse material não foi incluído nesta fila autobiográfica e **não deve ser copiado para a camada canônica**. O tratamento de credenciais deve ocorrer em fluxo de segurança separado, sem registrar valores secretos em documentação derivada.
