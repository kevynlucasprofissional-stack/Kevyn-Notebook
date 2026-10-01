# Revisão corretiva do Ciclo 0006

## Motivo da revisão

Ciclo 0006 executado com múltiplas falhas: hashes calculados sobre texto transformado em vez de bytes, afirmações editoriais epistemicamente descalibradas, proveniência ausente nas notas, versionamento não atualizado, relação não autorizada na ontologia, Kanban descrito com contagem errada, dados sensíveis expostos e artefatos de auditoria contraditórios.

## Problemas confirmados

1. **Hashes binários incorretos** — todos os 8 SHA-256 no Arquivos-Analisados.csv divergem dos bytes reais.
2. **Tamanhos incorretos** — todos os 8 tamanhos divergem.
3. **Kanban com 7 etapas** — a fonte SRC-000048 contém 8 colunas, não 7.
4. **"serviço prestado" sem evidência** — Portfolio de projetos.md afirma entrega sem comprovação.
5. **"Kevyn escrevendo SQL"** — formulação epistemicamente forte demais.
6. **"metodologia própria"** — AI First apresentado como autoral sem evidência.
7. **Relação `exemplifica`** — termo não pertence ao vocabulário controlado.
8. **Dados sensíveis expostos** — nomes de pessoas/organizações em Execucao sob pressao externa.md.
9. **Proveniência ausente** — as 7 notas não citam os novos SRCs nas fontes.
10. **Versionamento não atualizado** — versao_conteudo '1.0' em todas as notas modificadas.
11. **Declaração falsa sobre API** — Auditoria.json afirma que nenhum dado foi enviado para API externa.
12. **Contradição entre artefatos** — Auditoria diz "aprovado", Pendencias diz "validacao pendente".
13. **Duplicações mal contadas** — distinção temática não é duplicata tratada.
14. **Links contados como wikilinks** — 10 linhas em CSV contadas como relações alteradas.

## Problemas não confirmados

- Arquivos de Dados Kevyn estão preservados (confirmado por hash no manifesto).
- Backups correspondem aos hashes anteriores (verificados nos checksums).
- YAML frontmatter presente em todas as 7 notas (confirmado).
- Nenhum segredo real incorporado (falso positivo "senha" em "redesenhar").

## Arquivos corrigidos

1. Arquivos-Analisados.csv (8 hashes + tamanhos)
2. Marketing comunicacao e processos.md
3. Portfolio de projetos.md
4. Inteligencia artificial e automacao.md
5. Tecnologia IA e automacao.md
6. Negocios e marketing.md
7. Metodo de estudo e producao.md
8. Execucao sob pressao externa.md
9. Fonte - Notas profissionais e tecnicas 2025.md (criada)
10. Unidades-Informacionais.csv
11. Links-e-Relacoes.csv
12. Duplicacoes-e-Contradicoes.md
13. Pendencias.md
14. Auditoria.json
15. Mudancas-Aplicadas.json
16. Resumo-do-Ciclo.md
17. Manifesto-Fontes.csv (se necessário)
18. Matriz-Cobertura.csv (se necessário)
19. Estado-Integracao.json
20. Relatorio-Acumulado.md
21. Registro-de-Decisoes.md
22. Changelog do vault.md
