# Plano de Mudancas - Ciclo 0025

## Escopo

Reabrir os lotes `CICLO-0011`, `CICLO-0023` e `CICLO-0024` como revisao corretiva, retirar do nucleo a auto-sintese ampla nao curada e reiniciar a curadoria manual pelo inicio real do bloco `0023`.

## Mudancas previstas

- `UNI-000055` -> `95-Auditorias/Estado da integracao.md`
  Operacao: criar.
  Justificativa: registrar no proprio vault que o encerramento automatico foi invalidado.
  Impacto: torna o estado legivel sem depender apenas do controle externo.
  Risco interpretativo: baixo.

- `UNI-000056` -> notas centrais afetadas e arquivos de controle.
  Operacao: corrigir e rebaixar.
  Justificativa: remover auto-sintese ampla de notas biograficas, cronologicas e tematicas.
  Impacto: reduz poluicao semantica e impede que conteudo estudado apareca como biografia consolidada.
  Risco interpretativo: medio.

- `UNI-000057` -> `04-Trabalho-Vocacao-e-Projetos/Marketing comunicacao e processos.md`
  Operacao: ampliar.
  Justificativa: reintroduzir apenas o que `SRC-000079` permite afirmar sobre Kevyn.
  Impacto: recupera evidencia valida de estudo aplicado em oferta.
  Risco interpretativo: medio; nao confundir blueprint com entrega executada.

- `UNI-000058` e `UNI-000060` -> `02-Cronologia-e-Memorias/Salus e Desafio Svelte.md`
  Operacao: ampliar.
  Justificativa: fixar o enquadramento inicial do DS21 e a calibragem comunicacional do Svelte.
  Impacto: melhora cronologia e contexto operacional sem transformar a nota em explicacao do produto.
  Risco interpretativo: medio; nao tratar transcricao como orientacao medica.

- `UNI-000059` -> `01-Perfil-e-Autoconhecimento/Narrativa de grandeza e vida comum.md`
  Operacao: ampliar.
  Justificativa: registrar autorrelato simbolico sobre vida comum versus grandeza.
  Impacto: melhora precisao do padrao sem diagnostico.
  Risco interpretativo: medio.

## Frontmatter afetado

- `ultima_revisao` em 9 notas manualmente ajustadas.
- nova nota com `tipo: estado` em `95-Auditorias`.

## Links e MOCs afetados

- Nenhum MOC estrutural alterado.
- Apenas relacoes semanticas locais nas notas de Marketing, Salus e Narrativa.

## Validacao prevista

- `auditar_vault.py` sem erros YAML/UTF-8.
- ausencia de `AUTO-SINTETIZACAO` nas notas centrais limpas.
- manifesto coerente com `status_global = em_andamento`.