# Link Suggestions 15

- Gerado em: 2026-04-04
- Objetivo: Inserir blocos discretos de links sugeridos por IA em notas core estáveis, aumentando a densidade da rede sem poluir o conteúdo principal.

## Método

- Partida nos manifestos `_staging/07-link-repair-manifest.json` e `_staging/14-link-structure-refresh-manifest.json`, usando apenas candidatos de backlinks estratégicos com relação temática clara.
- O relatório `reports/14-link-structure-refresh.md` não estava presente no vault; usei como fallback a auditoria de links disponível em `reports/05-link-audit.md` para validar a navegação.
- Filtragem manual por classe `core`, estabilidade estrutural e ausência de fronteiras sensíveis, diários, dossiês longos e áreas `mirror`/`noise`/`_archive_review`.
- Inserção de um bloco padrão ao final de cada nota elegível, com no máximo 1 link por nota nesta rodada.

## Critérios

- Apenas notas core estáveis.
- Apenas notas com relação temática forte e alta confiança prática de navegação.
- Nenhuma nota de diário, dossiê longo ou sub-vault de fronteira.
- Sem repetição do mesmo link dentro da mesma nota.
- Sem aplicação quando o candidato não ficou suficientemente seguro.

## Arquivos afetados

- `HOME/O Professor/04_PERSONA 02 - O SOL/Como fazer amigos e influenciar pessoas/O Sorriso como Ação Deliberada.md`
- `HOME/O Professor/04_PERSONA 02 - O SOL/Como fazer amigos e influenciar pessoas/PRINCÍPIO 1 (Parte 2) - Torne-se verdadeiramente interessado na outra pessoa..md`
- `HOME/O Professor/04_PERSONA 02 - O SOL/Como fazer amigos e influenciar pessoas/PRINCÍPIO 2 - Aprecie honesta e sinceramente..md`
- `HOME/O Professor/04_PERSONA 02 - O SOL/Como fazer amigos e influenciar pessoas/A Oportunidade Perdida em Gettysburg.md`
- `HOME/O Professor/04_PERSONA 02 - O SOL/Como fazer amigos e influenciar pessoas/O Provérbio Chinês da Loja.md`
- `HOME/O Professor/04_PERSONA 02 - O SOL/Como fazer amigos e influenciar pessoas/O Volume da Prática de Dale Carnegie.md`
- `HOME/O Professor/04_PERSONA 02 - O SOL/Como fazer amigos e influenciar pessoas/PRINCÍPIO 1 - Não critique, não condene, não se queixe.md`
- `HOME/O Professor/04_PERSONA 02 - O SOL/Como fazer amigos e influenciar pessoas/PRINCÍPIO 3 - Desperte um forte desejo na outra pessoa.md`
- `HOME/O Professor/05_PERSONA 03 - O PENDURADO/Comunicação Não Violenta/O Custo da Punição na Educação.md`
- `HOME/O Professor/05_PERSONA 03 - O PENDURADO/Comunicação Não Violenta/O Foco no Positivo.md`
- `HOME/O Professor/01_SELF - O IMPERADOR/Meditações/Contemplação das Estrelas.md`
- `reports/15-ai-link-suggestions.md`
- `reports/15-ai-link-suggestions.json`
- `logs/15-ai-link-suggestions.md`

## Riscos

- As sugestões são heurísticas e podem ser úteis como navegação, mas não como verdade semântica final.
- Inserir links demais pode competir com o conteúdo principal; por isso o escopo foi mantido em 1 link por nota.
- Alguns candidatos foram mantidos fora da aplicação por estarem menos estáveis ou fora do recorte core.

## Próximos passos

- Revisar a percepção de ruído após alguns dias de uso.
- Se a navegação ficar útil, expandir para outro lote de notas core com a mesma regra de parcimônia.
- Se surgirem falsos positivos, reduzir o escopo apenas às notas hub/MOC mais centrais.

## Resumo

- Notas que receberam bloco de sugestão: 11
- Links inseridos: 11
- Candidatos rejeitados por baixa confiança: 0
- Candidatos não aplicados por escopo/estabilidade: 9
