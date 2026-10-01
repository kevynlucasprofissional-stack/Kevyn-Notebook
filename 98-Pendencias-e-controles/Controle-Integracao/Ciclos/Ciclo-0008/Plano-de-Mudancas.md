# Plano de Mudancas - Ciclo 0008 - Revisao Corretiva

## Escopo

Revisar `SRC-000055` a `SRC-000062`, corrigir hashes/tamanhos, reconciliar classificacoes e adicionar proveniencia para ferramentas de IA, mentorias e planejamento de produtos.

## Mudancas previstas

- Criar `Fonte - Mentorias produtos e ferramentas IA 2025` com IDs, caminhos, hashes e segredos explicitamente redigidos.
- Adicionar a fonte agregada a `Tecnologia IA e automacao`, `Inteligencia artificial e automacao`, `Sustentabilidade financeira e trabalho`, `Negocios e marketing` e, se sustentado, notas de influencias/estudos.
- Incluir a nota-fonte no indice geral.
- Corrigir `Arquivos-Analisados.csv` com bytes e hashes reais, incluindo `SRC-000061` e `SRC-000062`.
- Classificar `SRC-000058` como `irrelevante_justificado`; revisar a relevancia de `SRC-000060`.
- Atualizar manifesto e matriz para `CICLO-0008`.
- Produzir os artefatos obrigatorios ausentes e executar auditoria complementar.

## Riscos

- `SRC-000061` e `SRC-000062` contem credenciais; nenhum valor sera copiado para o vault ou controles.
- Planos de produto e aceleracao nao provam implementacao, investimento recebido ou operacao.
- Referencias de podcast/livro so entram quando permitem concluir interesse ou estudo relevante de Kevyn.

## Validacao

- SHA-256 calculado sobre bytes reais.
- Busca de padroes de segredo no vault.
- Auditoria de YAML, links, IDs, basenames, JSON/Canvas/Base.
- Comparacao entre manifesto, matriz e arquivos do ciclo.
