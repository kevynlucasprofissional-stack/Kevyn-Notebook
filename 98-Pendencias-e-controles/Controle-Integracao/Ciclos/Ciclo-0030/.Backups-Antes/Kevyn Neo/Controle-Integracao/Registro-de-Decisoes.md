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
