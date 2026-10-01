# Link Repair Plan 07

- Gerado em: 2026-04-04T16:21:52.204199-03:00
- Objetivo: Planejar o reparo seguro de navegação quebrada, priorizando links internos quebrados, alvos não resolvidos, aliases candidatos e backlinks estratégicos faltantes.

## Método

- Auditoria dos wikilinks e links Markdown internos no vault visível, ignorando URLs externas e separando sub-vaults aninhados.
- Detecção de aliases candidatos por divergência de artigo inicial e por normalização de pontuação, exigindo alvo único e proximidade estrutural.
- Triagem de backlinks estratégicos faltantes a partir de órfãs com alta saída em áreas que já possuem hubs fortes.
- Sem Obsidian CLI disponível; app aberto detectado, mas o plano ficou restrito a aliases em frontmatter, manifesto revisável e sugestões semânticas não aplicadas.

## Critérios

- Não editar automaticamente conteúdo em sub-vaults aninhados.
- Aplicar apenas correções reversíveis e de baixo risco.
- Deixar para revisão humana os casos que exigem criação de nota, rename, move, asset ausente ou decisão semântica.

## Arquivos afetados

- `reports/07-link-repair-plan.md`
- `reports/07-link-repair-results.md`
- `logs/07-link-repair.md`
- `_staging/07-link-repair-manifest.json`

## Riscos

- Parte dos alvos quebrados remanescentes são placeholders, notas ainda inexistentes ou referências sensíveis.
- Backlinks estratégicos melhoram navegação, mas exigem julgamento editorial; não foram criados automaticamente.
- Sem Obsidian CLI, renames e moves preservando links foram evitados por segurança.

## Próximos passos

- Aplicar aliases de alta confiança fora de sub-vaults aninhados.
- Reauditar para medir a redução real de links quebrados.
- Revisar o manifesto remanescente antes de qualquer rename, move ou criação de nota.

## Resumo

- Links quebrados antes do reparo: 697
- Alvos não resolvidos distintos: 422
- Candidatos seguros de alias: 56
- Candidatos elegíveis para aplicação automática: 49
- Backlinks estratégicos faltantes sugeridos: 20

## Aliases Candidatos de Alta Confiança

- `[[A Regra 85/15 do Sucesso Profissional]]` -> `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Regra 8515 do Sucesso Profissional.md` (punctuation-normalization, 15 ocorrência(s))
- `[[Invulnerabilidade do Sábio]]` -> `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio\A Invulnerabilidade do Sábio.md` (article-prefix, 14 ocorrência(s))
- `[[Inexistência de Dano ao Sábio]]` -> `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio\A Inexistência de Dano ao Sábio.md` (article-prefix, 10 ocorrência(s))
- `[[Autossuficiência Absoluta]]` -> `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio\A Autossuficiência Absoluta.md` (article-prefix, 6 ocorrência(s))
- `[[Fraqueza do Mal]]` -> `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio\A Fraqueza do Mal.md` (article-prefix, 6 ocorrência(s))
- `[[Velhice Infantil]]` -> `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio\A Velhice Infantil.md` (article-prefix, 6 ocorrência(s))
- `[[Analogia do Médico e o Louco]]` -> `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio\A Analogia do Médico e o Louco.md` (article-prefix, 5 ocorrência(s))
- `[[Natureza dos Bens do Sábio]]` -> `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio\A Natureza dos Bens do Sábio.md` (article-prefix, 5 ocorrência(s))
- `[[PRINCÍPIO 1 (Parte 2) - Torne-se verdadeiramente interessado na outra pessoa]]` -> `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PRINCÍPIO 1 (Parte 2) - Torne-se verdadeiramente interessado na outra pessoa..md` (punctuation-normalization, 5 ocorrência(s))
- `[[Natureza da Contumélia (Insulto)]]` -> `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio\A Natureza da Contumélia (Insulto).md` (article-prefix, 4 ocorrência(s))
- `[[PRINCÍPIO 1 - Não critique, não condene, não se queixe]]` -> `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PRINCÍPIO 1 - Não critique, não condene, não se queixe..md` (punctuation-normalization, 4 ocorrência(s))
- `[[O 'Deveria' como Violência Interior]]` -> `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\O Deveria como Violência Interior.md` (punctuation-normalization, 4 ocorrência(s))

## Alvos Não Resolvidos Prioritários para Revisão

- `A Crítica como Gatilho para a Defensiva`: 13 ocorrência(s)
- `PRINCÍPIO 7: Deixe que a outra pessoa sinta que a ideia é dela`: 6 ocorrência(s)
- `O Incidente 'Chá e Prosa' (Análise da Sombra Luciferiana)`: 6 ocorrência(s)
- `Perfil Comportamental Alto S/C (Castro)`: 5 ocorrência(s)
- `O Ego e o Self`: 5 ocorrência(s)
- `03 - quinta-feira.md`: 4 ocorrência(s)
- `Compounding (Juros Compostos)`: 4 ocorrência(s)
- `Kevyn Lucas: Arquétipo Mago`: 4 ocorrência(s)
- `Menor Mercado Viável`: 4 ocorrência(s)
- `O Desastre do Svelte (200 vs. 22)`: 4 ocorrência(s)
- `Aragorn`: 3 ocorrência(s)
- `Numenor`: 3 ocorrência(s)

## Backlinks Estratégicos Faltantes

- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Sorriso como Ação Deliberada.md` deveria receber backlink via `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Chave da Influência - Falar sobre o que o Outro Quer.md` ou MOC local.
- `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\PRINCÍPIO 1 (Parte 2) - Torne-se verdadeiramente interessado na outra pessoa..md` deveria receber backlink via `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Chave da Influência - Falar sobre o que o Outro Quer.md` ou MOC local.
- `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\O Custo da Punição na Educação.md` deveria receber backlink via `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\A Raiz dos Sentimentos.md` ou MOC local.
- `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Contemplação das Estrelas.md` deveria receber backlink via `HOME\O Professor\01_SELF - O IMPERADOR\Meditações\Transitoriedade Universal.md` ou MOC local.
- `HOME\Cérebro Profissional\Notas\Masterclasse DISC.md` deveria receber backlink via `HOME\Cérebro Profissional\Notas\Desafio Svelte.md` ou MOC local.
