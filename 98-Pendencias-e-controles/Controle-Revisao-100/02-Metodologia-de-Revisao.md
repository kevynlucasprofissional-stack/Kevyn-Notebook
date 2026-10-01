# 02 — Metodologia de Revisão

## Princípios

1. **Uma fonte por vez**: Cada arquivo é lido integralmente antes de qualquer comparação.
2. **Comparação semântica**: Não basta busca textual; é necessário compreender o que o arquivo diz sobre Kevyn e verificar se o vault captura essa informação com fidelidade.
3. **Evidência antes da integração**: Nenhuma afirmação entra no vault sem fonte, localizador e hash.
4. **Camada explícita**: Toda informação carrega rótulo de camada de evidência.
5. **Dúvida documentada**: Quando a evidência for insuficiente, registra-se a pendência; não se completa com inferência.

## Protocolo por arquivo

### Passo 1 — Identificação
- Localizar no manifesto (caminho, SHA-256, tamanho)
- Validar hash contra o arquivo real no filesystem
- Confirmar legibilidade

### Passo 2 — Leitura
- Ler o arquivo integralmente
- Registrar método (leitura direta, parse de JSON, etc.)
- Anotar limitações (formato, encoding, truncamento)

### Passo 3 — Classificação da relação
- `direta`: descreve Kevyn diretamente
- `indireta`: material estudado/produzido por Kevyn
- `contextual`: sobre pessoas, projetos ou ambientes de Kevyn
- `fora_do_escopo`: sem relação demonstrável

### Passo 4 — Extração de entidades
- Pessoas mencionadas (com contexto, não apenas nome)
- Projetos (com evidência de envolvimento de Kevyn)
- Acontecimentos (com data ou período)
- Conceitos (com indício de estudo ou aplicação)
- Datas e períodos (explícitos ou inferidos com cautela)
- Locais

### Passo 5 — Avaliação epistêmica
- Camada(s) de evidência presentes
- Grau de confiança para cada afirmação extraível
- Limites: o que o arquivo NÃO prova

### Passo 6 — Comparação com o vault
- A informação já existe? (presença)
- Está completa? (completude)
- Tem data, local, contexto? (especificidade)
- Foi desenvolvida ou apenas mencionada? (profundidade)
- Tem proveniência rastreável? (rastreabilidade)
- Diferencia fases temporais? (temporalidade)
- Está conectada a notas relacionadas? (conectividade)
- Conflita com outras notas? (coerência)

### Passo 7 — Classificação da cobertura
- `integrado_completo`: informação já presente com proveniência
- `integrado_parcial`: presente mas incompleta
- `presente_superficialmente`: mencionada sem desenvolvimento
- `presente_sem_proveniencia`: existe mas sem rastro até a fonte
- `ausente`: não consta no vault
- `contraditorio`: conflita com outra nota
- `fora_do_escopo`: não cabe no vault

### Passo 8 — Operações propostas
- Listar ações concretas (ampliar, corrigir, criar, relacionar...)
- Priorizar (P0-P4)
- Estimar complexidade e risco

### Passo 9 — Registro
- Atualizar a ficha ARQ-XXX.md
- Atualizar Matriz-Revisao-100.csv

## Auditoria pós-ciclo

Após cada ciclo, validar:
- Hashes das fontes (não foram alteradas)
- Hashes das notas (correspondem ao estado pós-edição)
- YAML (sintaxe, campos obrigatórios, vocabulários)
- Links (resolvem, não são ambíguos)
- Camadas de evidência (declaradas, coerentes com a fonte)
- Segredos (nenhum incorporado acidentalmente)
- Dados sensíveis (minimizados)
- Regressões (notas não afetadas permanecem idênticas)
