# Plano de Mudancas - Ciclo 0002

## Lote

Fontes: `SRC-000002` a `SRC-000008`.

## Mudancas planejadas

| unidade | nota de destino | operacao | justificativa | impacto | frontmatter afetado | links e MOCs afetados | risco de duplicacao | risco interpretativo | validacao prevista |
|---|---|---|---|---|---|---|---|---|---|
| UNI-000008 | `09-Fontes-e-Evidencias/Fonte - Conversa com minha alma revisada.md` | criar | registrar versao revisada e hash proprio | melhora proveniencia | nova nota `tipo: fonte` | `Indice geral de fontes selecionadas` | medio: sobrepoe diario parte 03 | medio: imagens simbolicas nao sao fatos | auditoria de links/YAML |
| UNI-000008 | `05-Sonhos-Simbolos-e-Espiritualidade/Sonhos imaginacao ativa e registros simbolicos.md` | ampliar | indicar a versao revisada como evidencia de imaginacao ativa | melhora granularidade temporal | `fontes_primarias`, revisao | link para nova fonte | baixo | medio | manter camada simbolica |
| UNI-000009 | `09-Fontes-e-Evidencias/Fonte - Gerador de dossie.md` | criar | catalogar prompt operacional sem copiar conteudo | aumenta rastreabilidade | nova nota `tipo: fonte` | `Indice geral de fontes selecionadas` | baixo | baixo | auditoria |
| UNI-000010 | `09-Fontes-e-Evidencias/Fonte - Gerador de visao geral.md` | criar | catalogar protocolo operacional sem copiar conteudo | aumenta rastreabilidade | nova nota `tipo: fonte` | `Indice geral de fontes selecionadas` | baixo | baixo | auditoria |
| UNI-000009, UNI-000010 | `01-Perfil-e-Autoconhecimento/Organizacao do conhecimento.md` | ampliar | registrar uso de prompts como engenharia de memoria/autoconhecimento | melhora entendimento do metodo de Kevyn | `fontes_primarias`, revisao | links para fontes novas | baixo | medio: nao tomar prompts como fatos biograficos | auditoria |
| UNI-000009, UNI-000010 | `08-Estudos-e-Referencias/Metodo de estudo e producao.md` | ampliar | registrar criterio de auditoria e decomposicao por etapas | melhora modelo de estudo/producao | `fontes_primarias`, revisao | links para fontes novas | baixo | baixo | auditoria |
| UNI-000009 | `04-Trabalho-Vocacao-e-Projetos/Inteligencia artificial e automacao.md` | ampliar | evidenciar competencia de arquitetura de prompts aplicada a si | melhora nota de IA | `fontes_primarias`, revisao | link para fonte nova | baixo | medio: competencia de prompt nao vira engenharia software | auditoria |
| UNI-000007, UNI-000011 | controle apenas | classificar | fontes ja integradas por hash/proveniencia | nenhum no vault | nenhum | nenhum | baixo | medio: documentar diferenca de contagem do JSON | controles do ciclo |

## Exclusoes justificadas

- Conteudo integral dos prompts (`SRC-000004`, `SRC-000005`) nao sera incorporado como instrucoes do vault; entra apenas como evidencia sobre metodo, preferencias e uso de IA por Kevyn.
- `SRC-000006` a `SRC-000008` nao serao reprocessados semanticamente neste ciclo porque possuem notas de proveniencia auditadas com hashes identicos e sao sinteses derivadas de menor autoridade que registros diretos.

## Validacao prevista

- Backups antes das notas modificadas.
- Patch limitado.
- Atualizacao de manifesto, matriz e relatorios do ciclo.
- Auditoria complementar sem dependencias.
