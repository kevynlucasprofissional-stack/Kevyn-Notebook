# Plano de Mudancas - Ciclo 0010 - Reconstrucao Corretiva

## Escopo

Processar os caminhos reais de `SRC-000071` a `SRC-000078`, substituindo nomes normalizados/inventados por proveniencia fiel ao manifesto e a `Dados Kevyn`.

## Mudancas previstas

- Criar `Fonte - Operacao WSI Salus e acessos 2025` com hashes reais e redacao de segredos.
- Corrigir `Arquivos-Analisados.csv` para caminhos, tamanhos e hashes reais.
- Reescrever unidades para refletir: changelog SQL, experimento de busca/SEO-LEO, referencia breve, campanha DS21, infraestrutura RAG/N8N, estudo de conteudo, responsabilidades Salus e credenciais Google Cloud.
- Classificar `SRC-000073` como irrelevante justificado.
- Vincular a fonte a IA/tecnologia, marketing, Salus, portfolio e negocios.
- Atualizar manifesto, matriz e todos os artefatos obrigatorios.

## Riscos

- `SRC-000075` e `SRC-000078` contem senhas, IDs, secrets e chaves; nenhum valor sera reproduzido.
- `SRC-000072` e uma resposta de IA sobre busca/recomendacao e nao prova resultado de SEO.
- `SRC-000076` e material estudado; entra apenas como evidencia de repertorio de conteudo/comunidade.
- `SRC-000077` registra responsabilidades planejadas, nao entrega concluida.

## Validacao

- Caminhos devem existir exatamente em `Dados Kevyn`.
- SHA-256 calculado sobre bytes reais.
- Busca de segredos no vault e auditoria estrutural completa.
