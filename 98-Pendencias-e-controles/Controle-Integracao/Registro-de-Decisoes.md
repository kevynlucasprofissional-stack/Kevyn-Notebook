# Registro de Decisoes

## RD-0001 - Localizacao do vault

- Data: 2026-06-17
- Ciclo: CICLO-0001
- Decisao: usar Kevyn Neo como cofre ativo, apesar de o caminho logico Kevyn Neo/Vault nao existir.
- Justificativa: a pasta contem .obsidian, 0-Inicio, MOCs, auditorias, templates e estrutura de vault ja entregue.
- Impacto: nenhum segundo cofre sera criado.

## RD-0002 - Checkpoint sem Git

- Data: 2026-06-17
- Ciclo: CICLO-0001
- Decisao: usar checksums antes/depois e, quando houver edicao de notas, copias de recuperacao no ciclo.
- Justificativa: a raiz de trabalho nao e um repositorio Git.
- Impacto: reversao sera feita por arquivo afetado, nao por git reset.

## RD-0003 - Conteudo indireto

- Data: 2026-06-17
- Ciclo: CICLO-0001
- Decisao: materiais estudados, produzidos ou usados por Kevyn nao serao copiados como conteudo tematico extenso.
- Justificativa: o escopo e compreender Kevyn; conteudos tecnicos, esotericos, comerciais ou teoricos entram apenas como evidencias de interesses, repertorio, praticas e dominio provavel.
- Impacto: reduz duplicacao e evita transformar o vault em enciclopedia de assuntos estudados.

## RD-0004 - Revisao corretiva do Ciclo 0006

- Data: 2026-06-18
- Ciclo: CICLO-0006 (revisao)
- Decisao: recalcular todos os hashes binarios com Get-FileHash -Algorithm SHA256, calibrar afirmacoes editoriais epistemicamente, minimizar dados sensiveis e adicionar proveniencia via nota-fonte.
- Justificativa: o ciclo original registrou hashes calculados sobre texto transformado (nao bytes reais), fez afirmacoes nao sustentadas pelas fontes isoladas, expos dados pessoais desnecessarios e usou relacao exemplifica nao autorizada pela ontologia.
- Impacto: 8 hashes corrigidos, 7 notas revisadas, 1 nota-fonte criada, Kanban corrigido de 7 para 8 etapas, dados sensiveis minimizados.

## RD-0005 - Nao enviar afirmacao sobre API externa

- Data: 2026-06-18
- Ciclo: CICLO-0006 (revisao)
- Decisao: remover do Auditoria.json qualquer afirmacao de que "nenhum dado foi enviado para API externa", pois a execucao ocorre em modelo remoto no OpenCode.
- Justificativa: a afirmacao e factualmente falsa no contexto atual.
- Impacto: formulacao substituida por transparencia sobre minimizacao de dados.

## RD-0006 - Nota-fonte unica para lote heterogeneo

- Data: 2026-06-18
- Ciclo: CICLO-0006 (revisao)
- Decisao: criar uma unica nota-fonte (Fonte - Notas profissionais e tecnicas 2025) para catalogar as 8 fontes do ciclo, em vez de multiplas notas-fonte individuais.
- Justificativa: as fontes sao diversas mas pertencem ao mesmo diretorio de origem e bloco de integracao.
- Impacto: proveniencia navegavel adicionada a todas as notas modificadas.

## RD-0007 - Invalidacao do estado global concluido

- Data: 2026-06-18
- Ciclo: CICLO-0010
- Decisao: descartar o estado global que declarava conclusao da segunda passagem e recalcular o progresso a partir do manifesto reconciliado e dos artefatos reais.
- Justificativa: o estado declarava `GATE_FINAL`, 0 pendencias e ultimo ciclo 36, mas os ciclos materiais comprovavam conteudo ate `CICLO-0010` e apenas 94 fontes analisadas.
- Impacto: `Estado-Integracao.json` passou a refletir progresso real, com `status_global = em_andamento` e `proximo_item = SRC-000079`.

## RD-0008 - Fronteira editorial entre 0009 e 0010

- Data: 2026-06-18
- Ciclo: CICLO-0010
- Decisao: registrar a normalizacao de proveniencia entre `CICLO-0009` e `CICLO-0010` como parte do fechamento de `00010`, sem reiniciar os ciclos anteriores.
- Justificativa: algumas notas apontavam para fontes de `0009` como se fossem de `0010`; os hashes atuais do vault ja incorporavam essa correcao.
- Impacto: os artefatos de `CICLO-0010` passam a explicar por que sete notas tiveram hash final diferente do fechamento anterior de `CICLO-0009`.

## RD-0009 - Triagem ampla como marcador de cobertura

- Data: 2026-06-18
- Ciclo: CICLO-0011
- Decisao: usar `ultimo_ciclo = CICLO-0011` no manifesto como marcador de cobertura do bloco `SRC-000079` a `SRC-000500`, sem converter cobertura em analise completa.
- Justificativa: o bloco foi triado integralmente por metadados, mas 406 fontes seguem sem analise substantiva.
- Impacto: o manifesto registra cobertura, o estado explicita a triagem e o próximo item avanca para `SRC-000501`.

## RD-0010 - Nenhuma edicao de notas neste ciclo

- Data: 2026-06-18
- Ciclo: CICLO-0011
- Decisao: manter o vault tematico sem novas edicoes de notas neste ciclo e concentrar a entrega em controle, proveniencia e auditoria.
- Justificativa: a cobertura do bloco foi ampla no nivel de metadados; nao havia fundamento suficiente para inflar edicoes tematicas.
- Impacto: `Checksums-Antes.txt` e `Checksums-Depois.txt` permanecem idênticos.

## RD-0011 - Revisao corretiva dos ciclos 0005 a 0010

- Data: 2026-06-19
- Ciclos: CICLO-0005 a CICLO-0010
- Decisao: normalizar os JSONs de mudancas dos ciclos 0005 e 0006 e separar estritamente as fontes dos ciclos 0009 e 0010.
- Justificativa: a auditoria encontrou encapsulamento auxiliar em JSON, intervalos textuais no lugar de listas e fontes de 0010 associadas a unidades de 0009.
- Impacto: 44 fontes foram reconferidas por tamanho e SHA-256; estudos indiretos, responsabilidades planejadas e credenciais passaram a ter classificacao epistemica separada, sem reproducao de segredos.

## RD-0012 - Reabertura dos lotes automaticos

- Data: 2026-06-19
- Ciclo: CICLO-0025
- Decisao: invalidar o encerramento automatico dos lotes `CICLO-0011`, `CICLO-0023` e `CICLO-0024`, rebaixar suas fontes para `parcialmente_integrado` e remover das notas centrais os blocos de auto-sintese ampla nao curados.
- Justificativa: `CICLO-0011` registrou triagem ampla sem leitura integral; `CICLO-0023` e `CICLO-0024` atualizaram manifesto e notas tematicas sem os artefatos contratuais completos do ciclo e passaram a misturar conteudo estudado com integracao biografica definitiva.
- Impacto: 23 notas foram limpas, 1168 fontes ficaram em revisao manual, 4 fontes (`SRC-000079` a `SRC-000082`) foram reincorporadas manualmente e o estado global voltou para `em_andamento`.

## RD-0013 - Criativos curtos do DS21 como evidencia de campanha

- Data: 2026-06-19
- Ciclo: CICLO-0026
- Decisao: integrar `SRC-000099` a `SRC-000102` apenas como evidencia de repertorio de criativos curtos, hooks e linguagem de topo de funil do DS21/Svelte.
- Justificativa: as quatro notas descrevem slogans, promessas de 21 dias, situacoes de identificacao do avatar e CTAs de acompanhamento do desafio, mas nao provam eficacia do produto nem autorizam reproduzir o conteudo bruto no nucleo.
- Impacto: 4 fontes sairam de `parcialmente_integrado`, o proximo item avancou para `SRC-000103` e as notas de Marketing e Salus ganharam precisao sobre linguagem de campanha.

## RD-0014 - Lote de lancamento semente do DS21 como evidencia de planejamento e copy

- Data: 2026-06-19
- Ciclo: CICLO-0027
- Decisao: integrar `SRC-000103` a `SRC-000107` apenas como evidencia de planejamento editorial, acessos operacionais redigidos e repertorio de copy de lancamento do DS21.
- Justificativa: o lote combina quadro kanban, CTA, VSL e prova social, mas inclui credenciais e promessas de produto que nao devem ser transplantadas para o nucleo biografico como fatos.
- Impacto: 5 fontes sairam de `parcialmente_integrado`, foi criada a nota `Fonte - Roteiros e lancamento semente DS21 2025` e o proximo item avancou para `SRC-000108`.

## RD-0015 - Reconstrucao do checkpoint pre-CICLO-0027

- Data: 2026-06-19
- Ciclo: CICLO-0027
- Decisao: reconstruir `Backups-Antes` e `Checksums-Antes.txt` usando as diferencas editoriais do proprio ciclo e os hashes autoritativos herdados do `CICLO-0026` e do `CHECKSUMS-INTEGRACAO` anterior.
- Justificativa: a primeira tentativa de materializar o checkpoint local falhou por caminho de saida incorreto, deixando os artefatos de pre-ciclo vazios.
- Impacto: a rastreabilidade de `hash_anterior` foi restaurada para notas e controles do ciclo; a validacao da reconstrucao ficou registrada em `Ciclos/Ciclo-0027/Backups-Antes/validacao-reconstrucao.txt`.

## RD-0016 - Estrategia de criacao e agentes IA como evidencia de direcao, nao de execucao

- Data: 2026-06-19
- Ciclo: CICLO-0028
- Decisao: integrar `SRC-000108` a `SRC-000110` apenas como evidencia de pesquisa de mercado em personality AI, estrategia de perfis/conteudo e desenho conceitual do agente `Esbelta`.
- Justificativa: o lote combina links externos, reflexao estrategica e conceito de produto, mas nao prova lancamento dos perfis, implantacao do agente nem seguranca clinica do fluxo proposto.
- Impacto: 3 fontes sairam de `parcialmente_integrado`, foi criada a nota `Fonte - Estrategia de criacao e agentes IA 2025` e o proximo item avancou para `SRC-000111`.

## RD-0017 - Curadoria de fronteira do bloco 111-115

- Data: 2026-06-21
- Ciclo: CICLO-0029
- Decisao: ajustar as notas de destino de `SRC-000111` e `SRC-000112` para explicitar escopo simbólico e monitoramento de mercado, sem inflar o bloco como cronologia ou espionagem literal.
- Justificativa: `SRC-000111` e `SRC-000112` sao materiais indiretos; a leitura util para Kevyn depende de reduzir o conteudo ao que eles realmente permitem concluir sobre repertorio, metodo e pratica.
- Impacto: 2 notas receberam proveniencia mais precisa, o estado de integracao foi atualizado e o proximo item avancou para `SRC-000116`.

## RD-0018 - Reavaliacao do bloco 116-120 como marketing aplicado

- Data: 2026-06-21
- Ciclo: CICLO-0030
- Decisao: integrar SRC-000116 a SRC-000120 apenas como evidencia de estudo de caso, criativo emocional, funil e gatilhos mentais ligados ao repertorio de Kevyn.
- Justificativa: o bloco e indireto e nao deve virar conteudo tematico bruto; o valor para o cofre esta no que ele permite concluir sobre repertorio, criterio e pratica de Kevyn.
- Impacto: 3 notas receberam ajuste de escopo/proveniencia, o proximo item avancou para SRC-000121 e o controle de integracao ficou pronto para o ciclo seguinte.

## RD-0019 - Restauracao de proveniencia do bloco 121-125

- Data: 2026-06-21
- Ciclo: CICLO-0031
- Decisao: restaurar em `Kevyn Lucas` e `Marketing comunicacao e processos` as proveniencias curtas de `SRC-000121` a `SRC-000125`, mantendo o conteudo em escopo biografico e operacional.
- Justificativa: os arquivos viviam no vault, mas a camada de proveniencia havia sido perdida no texto principal. O ciclo precisava recuperar a rastreabilidade sem copiar o material tematico bruto.
- Impacto: 2 notas foram atualizadas, 5 entradas de manifesto foram reclassificadas como integradas e o proximo item avancou para `SRC-000126`.

## RD-0020 - Restauracao de proveniencia do bloco 126-129

- Data: 2026-06-21
- Ciclo: CICLO-0032
- Decisao: restaurar em `Kevyn Lucas` e `Sustentabilidade financeira e trabalho` as proveniencias curtas de `SRC-000126` a `SRC-000129`.
- Justificativa: o bloco volta a ser util apenas como evidencia de sustentabilidade financeira, lancamento e refinamento editorial. O conteudo bruto segue fora do cofre.
- Impacto: 2 notas foram atualizadas, 4 entradas de manifesto foram reclassificadas como integradas e o proximo item avancou para `SRC-000130`.

## RD-0021 - Restauracao da proveniencia da linha editorial final de Salus

- Data: 2026-06-21
- Ciclo: CICLO-0033
- Decisao: registrar `SRC-000131` em `Salus e Capital Green` como evidencia de refinamento de copy e enquadramento da campanha Salus/DS21.
- Justificativa: o material e indireto e deve contribuir apenas com o que permite concluir sobre Kevyn: revisao editorial final, nao reproduzida em bruto.
- Impacto: 1 nota foi atualizada, 1 fonte foi reclassificada como integrada e o proximo item avancou para `SRC-000132`.

## RD-0022 - Unificacao de Silvanna

- Data: 2026-06-26
- Ciclo: estabilizacao-pos-v3
- Decisao: unificar as notas legadas `Silvana` e `Avo materna` na nota canonica `Silvanna`, preservando os nomes antigos apenas como aliases e referencias historicas.
- Justificativa: o usuario esclareceu que as duas entidades representam a mesma pessoa e indicou `Silvanna` como nome correto; manter duas notas separadas reintroduziria duplicidade sem ganho semantico.
- Impacto: a rede familiar, a historia parental, a cronologia da infancia, os MOCs relacionados e o inventario foram atualizados para apontar para `[[Silvanna]]`; as notas legadas foram removidas.

## RD-0023 - Fechamento da estabilizacao v4

- Data: 2026-06-26
- Ciclo: estabilizacao-pos-v4
- Decisao: considerar a estabilizacao tecnica deste ciclo como aprovada com ressalvas, com escopo ativo limpo e ruido herdado mantido apenas no escopo completo e no controle legado.
- Justificativa: a auditoria final do escopo ativo retornou 0 links quebrados, 0 YAML/frontmatter invalido, 0 frontmatter ausente, 0 basenames duplicados, 0 arquivos `.pyc` e 0 diretorios `__pycache__`; o escopo completo ainda preserva ruido historico nao bloqueante.
- Impacto: os relatórios finais foram gerados, o changelog foi fechado, as pendencias foram saneadas e os checksums finais foram regenerados.

## RD-0024 - Integracao curada do lote 270626

- Data: 2026-06-27
- Ciclo: CICLO-0035
- Decisao: integrar a transcricao de 26/06/2026 como fonte principal, preservar as analises derivadas como apoio documental e criar o estado atual de 27/06/2026.
- Justificativa: o lote novo nao trouxe duplicata exata, mas trouxe uma sessao terapeutica util e suas leituras derivadas; a separacao entre registro bruto e sintese reduz inflacao interpretativa.
- Impacto: `Fonte - Reuniao com psicologa Suzana 2026-06-26`, `Estado atual - 27 de junho de 2026`, `Matriz-Claims.csv`, `Manifesto-Fontes.csv` e `Matriz-Cobertura.csv` foram atualizados.

## RD-0025 - Reconciliacao da Matriz-Revisao-100

- Data: 2026-06-28
- Ciclo: controle-revisao-100
- Decisao: atualizar `Controle-Revisao-100/Matriz-Revisao-100.csv` para refletir `status_final = analisado_nao_integrado` em todos os 100 registros lidos integralmente.
- Justificativa: o arquivo ainda marcava `pendente_leitura` apesar de registrar leitura integral e extração concluídas; isso contradizia o estado real do lote.
- Impacto: a matriz deixou de conflitar com o criterio de fechamento e passou a distinguir revisao concluida de integracao efetiva.

## RD-0026 - Cobertura canonica e evidencias de manifesto

- Data: 2026-06-30
- Ciclo: CICLO-0036
- Decisao: separar `Manifesto-Fontes.csv` como trilha de inventario e analise direta, e `Matriz-Cobertura.csv` como trilha de cobertura semantica com representante canonico.
- Justificativa: varias linhas do manifesto sao duplicatas exatas e nao devem inflar a cobertura nem parecer analises independentes; `Hoor Digital` aparece como referencia de manifesto em `SRC-000726`, mas o arquivo nao esta materializado no recorte ativo.
- Impacto: a cobertura passou a registrar `coberto_por_duplicata` quando houver equivalente canonico, a matriz de evidencias explicita a dependencia de manifesto no caso Hoor Digital e a nota central pode ler a camada de marca sem confundir acesso ao bruto com existencia no root ativo.

