# Metadata Enrichment 13

- Gerado em: 2026-04-04T17:27:43-03:00
- Objetivo: aumentar a consistência de tags e aliases nas notas `core`, usando apenas heurísticas de alta confiança.

## Método

- Leitura de `AGENTS.md`, da skill `obsidian-vault-ops` e da base anterior de normalização.
- Aplicação apenas em `HOME/Cérebro Profissional` e `ACIRV`.
- Exclusão de diários, sub-vaults com `.obsidian`, e áreas fora do escopo prioritário.
- Propagação de uma tag de domínio por área quando a taxonomia da pasta era dominante e estável.
- Inclusão de aliases somente em notas com alternativo editorial claro e sem ambiguidade forte.

## Critérios

- Não alterar corpo das notas.
- Não atuar em sub-vaults de fronteira.
- Não atuar em diários.
- Não aplicar alias quando o nome alternativo fosse genérico, ambíguo ou dependente de inferência externa.

## Arquivos afetados

- `_staging/manifests/13-metadata-enrichment.json`
- `reports/13-metadata-enrichment.md`
- `reports/13-metadata-enrichment.json`
- `logs/13-metadata-enrichment.md`
- `scripts/metadata_enrichment.py`

## Mudanças aplicadas

- `HOME/Cérebro Profissional` passou a carregar `#cerebro-profissional` nas notas do domínio.
- `ACIRV` passou a carregar `#acirv` nas notas do domínio.
- Foram registrados 316 diffs materiais no vault, a partir de 321 alvos avaliados.
- 17 notas receberam aliases novos ou complementares.
- O manifesto completo de alterações ficou em `_staging/manifests/13-metadata-enrichment.json`.

### Aliases aplicados

- `HOME/Cérebro Profissional/Notas/(Criativos) - Palestra sobre IA.md` -> `Palestra sobre IA - Criativos`
- `HOME/Cérebro Profissional/Notas/(Palestra IA) Pitch por Ligação.md` -> `Pitch por Ligação`
- `HOME/Cérebro Profissional/Notas/(Pitch Hormozi) Espaço Prema.md` -> `Pitch Hormozi - Espaço Prema`
- `HOME/Cérebro Profissional/Notas/(Pitch Kevyn) - Espaço Prema.md` -> `Pitch Kevyn - Espaço Prema`
- `HOME/Cérebro Profissional/Notas/(Pitch Érico) Espaço Prema.md` -> `Pitch Érico - Espaço Prema`
- `HOME/Cérebro Profissional/Notas/(Planejamento) - Palestra sobre IA - 25 de Outubro.md` -> `Palestra sobre IA - 25 de Outubro`
- `HOME/Cérebro Profissional/Notas/(Sugestão Alan) Palestra sobre IA - 25.md` -> `Palestra sobre IA - 25`
- `HOME/Cérebro Profissional/Notas/PROMPT - Comparação notas atômicas com conteúdo original.md` -> `Comparação notas atômicas com conteúdo original`
- `HOME/Cérebro Profissional/Notas/PROMPT - Criador de System Prompt para Agentes de IA.md` -> `Criador de System Prompt para Agentes de IA`
- `HOME/Cérebro Profissional/Notas/PROMPT - Notas atômicas.md` -> `Notas atômicas`
- `HOME/Cérebro Profissional/Notas/PROMPT - Resumo e tags.md` -> `Resumo e tags`
- `HOME/Cérebro Profissional/Notas/PROMPT - System message da ESBELTA (nutrição & comportamento).md` -> `System message da ESBELTA`
- `ACIRV/Notas/(Desatualizado) Padrão de qualidade do novo tom de voz.md` -> `Padrão de qualidade do novo tom de voz`
- `ACIRV/Notas/(PLANEJAMENTO ANUAL) CONECTA ACIRV 2026.md` -> `CONECTA ACIRV 2026`
- `ACIRV/Notas/(RELEASE) Seminário Multiplicadores de Sucesso.md` -> `Seminário Multiplicadores de Sucesso`
- `ACIRV/Notas/1º Fórum de IA da ACIRV - Planejamento Social Media.md` -> `Planejamento Social Media`
- `ACIRV/Notas/300326 - Notas reunião com VCOM.md` -> `Notas reunião com VCOM`

## Mudanças sugeridas, mas não aplicadas

- `ACIRV/Notas/(RELATÓRIO MÉTRICAS) - Janeiro.md`
- `ACIRV/Notas/(RELATÓRIO MÉTRICAS) - Fevereiro.md`
- `ACIRV/Notas/(RELATÓRIO MÉTRICAS) - Março.md`
- `ACIRV/Notas/(RELATÓRIO MÉTRICAS PARA DIRETORIA) - Janeiro.md`
- `ACIRV/Notas/(MÉTRICAS) - 2025.md`
- `HOME/Cérebro Profissional/Notas/(IMRIA) - V01.md` a `V10.md`
- Rejeitado por baixa confiança: `HOME/Cérebro Profissional/Notas/(PLANO 10K EM 15 DIAS) -.md`
- Rejeitado por baixa confiança: `ACIRV/Notas/(1º Conecta de 2026) Planejamento.md`

## Áreas ainda inconsistentes

- `HOME/O Professor` ficou fora desta rodada por prudência: é uma área core, mas com conteúdo mais sensível e alto risco de aliasing agressivo.
- `HOME/Segundo Cérebro` permanece com taxonomia mais heterogênea e exige uma leitura separada.
- `HOME/Kevyn Lucas` continua sendo fronteira sensível.
- `ACIRV/Diário` permanece fora por regra.

## Riscos

- A tag de domínio melhora navegabilidade, mas ainda pode coexistir com taxonomias locais mais específicas.
- Alguns títulos de série continuam sem alias porque a forma abreviada é ambígua.
- Alterações em massa em áreas grandes exigem validação humana em uso real, mesmo quando mecanicamente seguras.

## Próximos passos

1. Revisar em uso real se `#cerebro-profissional` e `#acirv` ajudam a busca sem poluir demais os filtros.
2. Reavaliar as séries de métricas e `IMRIA` em uma rodada específica, se houver expansão do acrônimo ou da taxonomia local.
3. Só então considerar um segundo passe em `HOME/O Professor`, separado e mais conservador.
