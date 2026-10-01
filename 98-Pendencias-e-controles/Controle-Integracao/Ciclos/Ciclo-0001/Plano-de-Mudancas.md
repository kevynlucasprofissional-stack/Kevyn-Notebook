# Plano de Mudancas - Ciclo 0001

## Lote: diarios e aulas filosoficas de janeiro a abril de 2026

### Escopo

Fontes analisadas: `SRC-000009`, `SRC-000083` a `SRC-000098`.

### Mudancas planejadas

| unidade | nota de destino | operacao | justificativa | impacto | frontmatter afetado | links e MOCs afetados | risco de duplicacao | risco interpretativo | validacao prevista |
|---|---|---|---|---|---|---|---|---|---|
| UNI-000003, UNI-000004, UNI-000005 | `09-Fontes-e-Evidencias/Fonte - Diario FGV e aulas Nova Acropole 2026.md` | criar | registrar proveniencia do conjunto sem copiar blocos brutos | aumenta rastreabilidade | nova nota `tipo: fonte` | `Indice geral de fontes selecionadas`, `Diarios - catalogo` | baixo | baixo | wikilinks e YAML |
| UNI-000003, UNI-000004, UNI-000005 | `08-Estudos-e-Referencias/Estudos na Nova Acropole.md` | criar | sintetizar o que o conjunto permite concluir sobre Kevyn | adiciona estudo recorrente ao repertorio | nova nota `tipo: tema_pessoal` | `MOC Estudos e referencias`, `Filosofia e psicologia`, `Estilo de aprendizagem` | medio, por proximidade com filosofia/espiritualidade | medio: nao transformar aula em fato sobre Kevyn | auditoria e leitura de links |
| UNI-000004 | `08-Estudos-e-Referencias/Filosofia e psicologia.md` | ampliar | registrar evidencia direta de estudo filosofico aplicado | melhora cobertura de estudos | `ultima_revisao` | link para nova nota | baixo | medio | manter linguagem epistemica |
| UNI-000004 | `01-Perfil-e-Autoconhecimento/Estilo de aprendizagem.md` | ampliar | registrar padrao de anotacao e associacao interdisciplinar | atualiza perfil de aprendizagem | `ultima_revisao` | link para nova nota | baixo | baixo | nao afirmar dominio formal |
| UNI-000003 | `80-MOCs-e-Trilhas/MOC Estudos e referencias.md` | relacionar | tornar a nova nota navegavel | atualiza MOC | `ultima_revisao` | link novo | baixo | baixo | link resolvido |
| UNI-000003 | `06-Saude-Autocuidado-e-Autorregulacao/Diarios de 2026.md` | corrigir/ampliar | a nota falava apenas de registros de maio-junho; o lote mostra registros curtos de jan-abr | corrige cobertura temporal | `ultima_revisao` | link para nova fonte/nota | baixo | baixo | coerencia temporal |
| UNI-000003 | `02-Cronologia-e-Memorias/Linha do tempo mestre.md` | ampliar | registrar aulas/diarios filosoficos no periodo jan-abr/2026 | melhora cronologia | `ultima_revisao` | link para nova nota | baixo | baixo | sem duplicar linha existente |

### Exclusoes justificadas

- `UNI-000002`: indices Excalidraw e arquivo vazio nao descrevem Kevyn de modo substantivo.
- `UNI-000006`: conteudo doutrinario das aulas nao sera incorporado integralmente; somente o que evidencia repertorio, interesses e modo de aprendizagem de Kevyn.

### Validacao prevista

1. Criar backup dos arquivos existentes antes do patch.
2. Aplicar patch textual limitado.
3. Atualizar controles do ciclo e manifesto dos arquivos analisados.
4. Executar `auditar_vault.py`.
5. Recalcular checksums depois do ciclo.
