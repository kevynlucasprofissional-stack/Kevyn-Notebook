# Frontmatter Minimum 07

- Gerado em: 2026-04-04T10:59:50.338907-03:00
- Objetivo: Planejar ou aplicar frontmatter mínimo com segurança e reversibilidade.

## Método

- Parser conservador de frontmatter simples.
- Inserção ou atualização apenas das chaves mínimas pedidas.
- Dry-run por padrão; escrita só com `--apply`.

## Critérios

- Campos mínimos: `title`, `created`, `updated`, `status`, `source_area`.
- Sub-vaults aninhados ficam fora por padrão.
- Frontmatter complexo é pulado para evitar dano estrutural.

## Arquivos afetados

- `reports/07-frontmatter-minimum.json`
- `reports/07-frontmatter-minimum.md`
- `logs/07-frontmatter-minimum.md`

## Riscos

- Timestamps de filesystem podem não refletir a data semântica real da nota.
- Frontmatter YAML avançado não é reescrito por este parser conservador.

## Próximos passos

- Executar primeiro em dry-run e revisar `changed_files`.
- Só depois aplicar com `--apply` nas áreas aprovadas.

## Resumo

- Dry-run: sim
- Notas Markdown consideradas: 3576
- Arquivos que receberiam mudança: 2000
- Arquivos pulados: 1576

## Mudanças Planejadas

- `.venv\Lib\site-packages\pip-25.3.dist-info\licenses\src\pip\_vendor\idna\LICENSE.md`: modo insert
- `.venv\Lib\site-packages\pip\_vendor\idna\LICENSE.md`: modo insert
- `ACIRV\Diário\2026\01 - janeiro\12 - segunda-feira.md`: modo insert
- `ACIRV\Notas\(Desatualizado) Padrão de qualidade do novo tom de voz.md`: modo insert
- `ACIRV\Notas\110326 - Insight completo sobre como estou usando meu tempo.md`: modo insert
- `ACIRV\Notas\300326 - Notas reunião com VCOM.md`: modo insert
- `ACIRV\Notas\BRIEFING COMPLETO – PASTA ENVELOPE INSTITUCIONAL ACIRV.md`: modo insert
- `ACIRV\Notas\cronograma otimizado para o dia 110326.md`: modo insert
- `ACIRV\Notas\Guia Estratégico para Gestão da Comunidade ACIRV.md`: modo insert
- `ACIRV\Notas\Ideia de criativos.md`: modo insert
- `ACIRV\Notas\JOBS - Picanha dos depoimentos do Fórum de IA.md`: modo insert
- `ACIRV\Notas\Kevyn vs. Renata - Uma Mudança.md`: modo insert
- `ACIRV\Notas\Melhorando a IA redatora.md`: modo insert
- `ACIRV\Notas\MVP SaaS - ACIRV MEET.md`: modo insert
- `ACIRV\Notas\Picanha dos depoimentos do Fórum de IA.md`: modo insert
- `ACIRV\Notas\Regulamento da postagem e captura de material de eventos da ACIRV.md`: modo insert
- `ACIRV\Notas\Releaser.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 01.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 02.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 04.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 05.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 06.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 07.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 08.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 10.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 11.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 12.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 13.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 14.md`: modo insert
- `ACIRV\Notas\Retrospectiva 2025 - Planejamento\Extrações\Extração 15.md`: modo insert

## Arquivos Pulados

- `ACIRV\Diário\2025\11 - novembro\11 - novembro.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\11 - novembro\11 - terça-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\11 - novembro\13 - quinta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\11 - novembro\14 - sexta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\11 - novembro\17 - segunda-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\11 - novembro\18 - terça-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\11 - novembro\19 - quarta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\11 - novembro\21 - sexta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\11 - novembro\24 - segunda-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\11 - novembro\25 - terça-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\11 - novembro\27 - quinta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\12 - dezembro\01 - segunda-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\12 - dezembro\02 - terça-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\12 - dezembro\03 - quarta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\12 - dezembro\04 - quinta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\12 - dezembro\05 - sexta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\12 - dezembro\08 - segunda-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\12 - dezembro\09 - terça-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\12 - dezembro\10 - quarta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\12 - dezembro\12 - dezembro.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\12 - dezembro\12 - sexta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\12 - dezembro\29 - segunda-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2025\2025.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2026\01 - janeiro\01 - janeiro.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2026\01 - janeiro\07 - quarta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2026\01 - janeiro\08 - quinta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2026\01 - janeiro\13 - terça-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2026\01 - janeiro\15 - quinta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2026\01 - janeiro\16 - sexta-feira.md`: Frontmatter complexo ou inválido para parser conservador.
- `ACIRV\Diário\2026\02 - fevereiro\02 - fevereiro.md`: Frontmatter complexo ou inválido para parser conservador.
