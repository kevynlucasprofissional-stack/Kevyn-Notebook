# Link Audit 05

- Gerado em: 2026-04-04T16:21:14.188804-03:00
- Objetivo: Mapear links quebrados, alvos não resolvidos, órfãos prioritários e candidatos a hub/MOC.

## Método

- Resolução de wikilinks por caminho relativo e por nome normalizado de arquivo.
- Resolução de links Markdown locais com exclusão de URLs externas.
- Priorização de órfãos por atividade local e hubs por densidade de ligação.

## Critérios

- Nenhuma correção de link é aplicada automaticamente.
- Notas órfãs são triadas por prioridade estrutural, não por valor semântico.
- Hubs/MOCs são sugeridos quando concentram backlinks ou combinam alta entrada e alta saída.

## Arquivos afetados

- `reports/05-link-audit.json`
- `reports/05-link-audit.md`
- `logs/05-link-audit.md`

## Riscos

- Links implícitos dependentes de aliases não declarados podem aparecer como quebrados.
- Notas novas ou isoladas intencionalmente podem aparecer como órfãs prioritárias.

## Próximos passos

- Revisar alvos não resolvidos mais frequentes para criar aliases ou corrigir nomes.
- Usar os hubs sugeridos como ponto de partida para MOCs revisáveis.

## Resumo

- Notas Markdown: 3350
- Links quebrados: 3925
- Alvos não resolvidos distintos: 3210
- Órfãos prioritários: 1192
- Candidatos a hub/MOC: 61

## Alvos Não Resolvidos Frequentes

- `https://www.google.com/url?sa=E&q=https%3A%2F%2Fatoepotencia.com.br%2Fa-vida-so-comeca-depois-dos-30-carl-jung%2F`: 87 ocorrência(s)
- `https://www.google.com/url?sa=E&q=https%3A%2F%2Fvertexaisearch.cloud.google.com%2Fgrounding-api-redirect%2FAUZIYQHGqcsiw3cbU89fFqTVYrT5iso4yTdmr6X_Pe92najAp6VC3PD8RgGSS0Qp2PFi-VSTCUt8_FclyYG5fm4GgSjz6vuuXnOZSVS4c2KUvlcRf53-ooEFJOQeCGqNaXAKLop2pxGa-uI%3D`: 72 ocorrência(s)
- `https://www.instagram.com/explore/tags/acirv/`: 16 ocorrência(s)
- `A Regra 85/15 do Sucesso Profissional`: 15 ocorrência(s)
- ``: 14 ocorrência(s)
- `Invulnerabilidade do Sábio`: 14 ocorrência(s)
- `A Crítica como Gatilho para a Defensiva`: 13 ocorrência(s)
- `https://www.hadnu.org/publicacoes/liber-liberi-vel-lapidis-lazuli/ "Liber Liberi vel Lapidis Lazuli"`: 12 ocorrência(s)
- `https://www.youtube.com/watch?v=2IJibUIDx6I&t=0`: 11 ocorrência(s)
- `https://www.instagram.com/explore/tags/rioverde/`: 10 ocorrência(s)
- `https://agenciacoradenoticias.go.gov.br/171920-hub-goias-chega-a-rio-verde-para-impulsionar-inovacao-local?utm_source=chatgpt.com "Hub Goiás chega a Rio Verde para impulsionar inovação ..."`: 10 ocorrência(s)
- `Inexistência de Dano ao Sábio`: 10 ocorrência(s)
- `https://www.google.com/url?sa=E&q=https%3A%2F%2Fvertexaisearch.cloud.google.com%2Fgrounding-api-redirect%2FAUZIYQFXl2LwIzTV3-eaq8EUoOoW-1noLUmR6PBKTp1iZkIGtNCxVgYhhNjCmnTBtD8-JRHfs1kHPqYYM8y7hV9SYAkWMob1CY4BZwolysIWe3SiY-iHSFSEOESSKaqnotiY0F0_cttgemUVlGa7sceyuH4ly0GrqYRe36n039Bh1lpTJ5vGryYu7YF_iWY3-6B9i9Mit_0I0HbrYbDqDAP8ag%3D%3D`: 9 ocorrência(s)
- `https://www.google.com/url?sa=E&q=https%3A%2F%2Fvertexaisearch.cloud.google.com%2Fgrounding-api-redirect%2FAUZIYQFR-ySTc-XCTqP3Ix9aLjeU49SA3U1Z3X326xB2a5oxP-20kuciCIhrbVGbhNGFtcryA1goN9AVHZCmh-oexrGTSc0Gf62muZm21w5uoqXMKx4TjBcBaRMqTRt4zBtwGTOjMO69CsPAGTNI`: 9 ocorrência(s)
- `https://www.instagram.com/explore/tags/intelig%C3%AAnciaartificial/`: 6 ocorrência(s)
- `https://www.instagram.com/explore/tags/tecnologia/`: 6 ocorrência(s)
- `https://www.google.com/url?sa=E&q=https%3A%2F%2Fvertexaisearch.cloud.google.com%2Fgrounding-api-redirect%2FAUZIYQFlcuZKpxP6cGrNzarYMMpiwIj9fl8uEPE5-JI-WswE3O2SSb7YGcNHeKZ3DOpGjpxrhavHUTTl3nCY_F3GxQ5BHIFpjQO6w33QFE0Khcn9810XKrxzgr0_zafVVGR9NNEVhsm1koSTfmOrWjlUOQSZHw%3D%3D`: 6 ocorrência(s)
- `https://ai.google.dev/gemini-api/docs/grounding/search-suggestions`: 6 ocorrência(s)
- `https://www.google.com/url?sa=E&q=https%3A%2F%2Fvertexaisearch.cloud.google.com%2Fgrounding-api-redirect%2FAUZIYQEbQg4xPM4jRAMbMLV6Y-3l44KgOIrfAHI_krdHDZ9-52XISO3CMeO144ljuBd942RQHEMRAHR7yrWvP_bt6RbmLDFOMrjzXGwIRAaVPd-I4RZlfXtAdByVevSly0NEp2FcGnz3j4D2S1D1h-QxOCizftF7QEUcVWxCLVqfq9lxu3xhQRqUY-mraEOUTLKs8SSyIhJMZdmw`: 6 ocorrência(s)
- `https://www.google.com/url?sa=E&q=https%3A%2F%2Fvertexaisearch.cloud.google.com%2Fgrounding-api-redirect%2FAUZIYQFyyjXcOaiGYXSfC5-W6y54F6KESV1sHwVd1INwIpfLX9uzM0jaFp3utvatXqoQGnczzTibB3IApa6Etvq2cv9gkq4_tDx8W0sWpUn9PCT8yINztnMUlrEWH86VJhkxTLElWIVVL3zM71saSYRmFPC0XNlHNyrL8qumXTkrMJhzRxJMPvKMw2Yk2nLEHA%3D%3D`: 6 ocorrência(s)
- `https://www.google.com/url?sa=E&q=https%3A%2F%2Fvertexaisearch.cloud.google.com%2Fgrounding-api-redirect%2FAUZIYQFmphrbQjIw92eT9dwfqpT3BthIG8AfAlRVcEZF8puTL-0c6Y9XwrPvkuZnbebRDFBitwkzOwtAqfqw9GTYtOvZ2ArJRW5YbXEVmdB1xHx9YE_6fqVfh-fcf02TOYD4mJ7lazRBsCPH3826jfsBZvaN5dOFj5uvW5EXLLV_pJV1PI0NZch8ACzGVgMJdBXA1RIwPHuz`: 6 ocorrência(s)
- `https://www.google.com/url?sa=E&q=https%3A%2F%2Fvertexaisearch.cloud.google.com%2Fgrounding-api-redirect%2FAUZIYQGUy36J7NZWlgl1vjEt1uN_mMLgAfq5k8eeYWZZH-KJQ4xDG10_WcAth8OPI3WKgfthxTF5n5rG9kKxLO0yij2kilMPQGOPsAlXZzeCCvxYTxS7iCE2Uj4YOImbotUSf9SxgFGM6ksV`: 6 ocorrência(s)
- `https://www.google.com/url?sa=E&q=https%3A%2F%2Fvertexaisearch.cloud.google.com%2Fgrounding-api-redirect%2FAUZIYQHj0h35y8s0nOY1XaxQ7rd6jTBj7o_ImHyyE6Wm6hKxuWGaBHFhK0--ndPPLJHKBiOJiY64w-GUgyWJ5rXvls74WCVH0ck3R4nFdVMvI6c6P0ij-TIIrG4mxPT1wcKViQaCc4LyvtO_In-hi3A1_sKILvr7pZVA5JMpOuvt-lz-jxWL9HmhN3gy6Dc3KQ%3D%3D`: 6 ocorrência(s)
- `https://www.google.com/url?sa=E&q=https%3A%2F%2Fvertexaisearch.cloud.google.com%2Fgrounding-api-redirect%2FAUZIYQFdSdGs_jqimcsyBn6WXoYtlU-FtnI6985mguru968lbkpBlQRHzdIXpZGxNti7AYyFCguqR5xgDoTs0j7Y6hmZn3NKt9zfgWVJoSRwLR552s9EkB6SzDeJMSZkAX5P5So-uT7iK0yqna3VIL8utpvmt5-VBPRNkCgU`: 6 ocorrência(s)
- `https://www.google.com/url?sa=E&q=https%3A%2F%2Fvertexaisearch.cloud.google.com%2Fgrounding-api-redirect%2FAUZIYQHCxYLVn9Gvf45IHWFo5q9UUcxrfl-vxrdsKZZFg_wJbWbNL6se1fwYg810sb7wYPXi0BAi8xy4S5e_QmIi0bh4gwiSNow4zd_QY_c0E9mrHkQKAndqTK5vQUnWJFHVWyjhHPF0TEBjEruw8TMv1yHtsMJ8SOZxTxFGaTPSvuzPGIP5cA%3D%3D`: 6 ocorrência(s)

## Órfãos Prioritários

- `HOME\Clones\_ECO\ECO V3\input_data\kotler\Marketing 6.0.md`: score 632
- `HOME\Clones\_ECO\ECO V3\input_data\kotler\Marketing 4.0.md`: score 560
- `HOME\Cérebro Profissional\Notas\Masterclasse DISC.md`: score 220
- `HOME\Cérebro Profissional\Notas\Teorias da Personalidade em mapas mentais Freud 1.md`: score 121
- `HOME\Kevyn Lucas\Outros\Integrados\Ato e Potência.md`: score 75
- `ACIRV\Notas\Dados sobre o Fórum.md`: score 36
- `HOME\ACIRV\Notas\Dados sobre o Fórum.md`: score 36
- `HOME\Cérebro Profissional\Notas\Estamos ficando mais burros.md`: score 34
- `HOME\Kevyn Lucas\Outros\Integrados\Sobre a simbiose romântica, minhas tribos e a Odisséia psicológica.md`: score 31
- `HOME\Kevyn Lucas\Outros\Visão Geral\Passo 01 - Cronologia e fatos.md`: score 22
- `HOME\Segundo Cérebro\SC\Dominando o Adobe Premiere 2.0.md`: score 19
- `HOME\Cérebro Profissional\Diário\2025\10 - outubro\09 - quinta-feira.md`: score 16
- `HOME\Muad’Dib\00_Cérebro Operacional\00_PROMPT_SISTEMA.md`: score 13
- `HOME\O Professor\00_Cérebro Operacional\V1\00_prompt_do_sistema_semi_automático.md`: score 13
- `HOME\O Professor\00_Cérebro Operacional\V2\00_PROMPT_SISTEMA.md`: score 13
- `Google Drive (Not synced)\Meu Drive\HOME\Liber VII.md`: score 12
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Sorriso como Ação Deliberada.md`: score 11
- `ACIRV\Notas\Oficina VITRINE QUE VENDE.md`: score 10
- `HOME\ACIRV\Notas\Oficina VITRINE QUE VENDE.md`: score 10
- `HOME\Segundo Cérebro\Guia de tarefas.md`: score 8
- `HOME\Segundo Cérebro\SC\Guia de tarefas.md`: score 8
- `HOME\Ágora\Ágora Obsidian\Fluxo de análise do Agente Ágora - Rascunho.md`: score 8
- `ACIRV\Notas\Sintese - Tom de Voz ACIRV 2026.md`: score 7
- `HOME\O Professor\00_Cérebro Operacional\V1\00_prompt_do_sistema_automático.md`: score 7
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PRINCÍPIO 1 (Parte 2) - Torne-se verdadeiramente interessado na outra pessoa..md`: score 7

## Hubs/MOCs Sugeridos

- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Desejo de Ser Importante (John Dewey).md`: 22 entradas, 6 saídas
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico\Dicotomia do Controle.md`: 22 entradas, 4 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Chave da Influência - Falar sobre o que o Outro Quer.md`: 21 entradas, 5 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Fome Humana Insaciável por Apreciação.md`: 20 entradas, 6 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Universalidade da Autojustificativa.md`: 18 entradas, 8 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Raro Indivíduo Desinteressado.md`: 19 entradas, 6 saídas
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico\Princípio da Apreciação Sincera (Carnegie).md`: 21 entradas, 2 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Crítica como Bumerangue (Pombos-Correio).md`: 17 entradas, 5 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Diferença entre Elogio e Bajulação.md`: 16 entradas, 6 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Filosofia do Elogio Pródigo e Sincero.md`: 16 entradas, 6 saídas
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\A Raiz dos Sentimentos.md`: 16 entradas, 6 saídas
- `HOME\Cérebro Profissional\Notas\Desafio Svelte.md`: 18 entradas, 3 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Habilidade de Despertar Entusiasmo (Charles Schwab).md`: 16 entradas, 5 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Crítica como Assassina de Ambições.md`: 15 entradas, 5 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Segredo do Sucesso de Henry Ford.md`: 14 entradas, 6 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\Para ser Interessante, Seja Interessado.md`: 15 entradas, 5 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Autoconfiança Através da Ação.md`: 13 entradas, 6 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Regra dos Dois Meses vs. Dois Anos.md`: 14 entradas, 5 saídas
- `HOME\Cérebro Profissional\MOC - Cérebro Profissional.md`: 5 entradas, 13 saídas
- `HOME\O Professor\00_Aleatórios\Cérebro Atômico\Planejamento como Defesa Obsessiva.md`: 14 entradas, 4 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Crítica Deve Começar por Si Mesmo.md`: 12 entradas, 6 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\Crítica como Agressão ao Orgulho.md`: 13 entradas, 5 saídas
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Homem que só Pensa em Si é Irremediavelmente Ignorante.md`: 13 entradas, 5 saídas
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\Julgamentos Moralizadores.md`: 13 entradas, 5 saídas
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Transitoriedade Universal.md`: 12 entradas, 5 saídas
