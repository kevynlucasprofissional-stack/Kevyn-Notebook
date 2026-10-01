# 03 — Plano Mestre de Revisão

## Arquitetura de execução

Cada ciclo (R01-R08) segue o mesmo protocolo de 10 etapas:

1. **Checkpoint**: Checksums-Antes.txt + backup das notas afetadas
2. **Leitura**: Reler cada arquivo-fonte integralmente, registrando método e limitações
3. **Extração**: Identificar fatos, pessoas, datas, projetos, conceitos e contextos
4. **Comparação**: Contrastar com o conteúdo atual das notas do vault
5. **Lacunas**: Registrar ausências, superficialidades, contradições e erros
6. **Plano**: Produzir Plano-de-Mudancas.md antes de editar
7. **Edição**: Modificar notas com proveniência, calibração epistêmica e versionamento
8. **Registro**: Atualizar Matriz-Revisao-100.csv, Mudancas-Aplicadas.json e controles
9. **Auditoria**: Validar YAML, links, camadas, segredos, consistência
10. **Segunda passagem**: Verificar idempotência antes de avançar ao próximo ciclo

## Regras editoriais da revisão

### Proveniência obrigatória
Toda nova afirmação em nota temática deve ser rastreável:
```
afirmação → SRC → caminho relativo → hash SHA-256 → localizador → camada de evidência
```

### Calibração epistêmica
- `registro_direto`: "Kevyn registrou que..."
- `documento_operacional`: "As notas preservam..."
- `interpretacao_ia`: "Uma análise de IA sugere que..."
- `sintese_derivada`: "A partir das fontes, observa-se que..."
- `simbolico_espiritual`: "No registro simbólico..."

### Não presumir
- Autoria sem evidência
- Execução sem confirmação
- Contratação sem fonte
- Publicação sem prova
- Domínio técnico sem demonstração
- Metodologia própria sem contraste com fontes externas

### Minimização de dados sensíveis
- Nomes de terceiros: apenas quando indispensáveis ao contexto
- Empresas: generalizar quando possível
- Conflitos: descrever padrão, não detalhes
- Dados de saúde: síntese sem diagnóstico
- Relacionamentos: contexto sem intimidade

## Sequência lógica

A ordem R01→R08 não é arbitrária:
- **R01 (cronologia)** primeiro porque datas e períodos ancoram todo o resto
- **R02 (psique)** depende de R01 para contextualizar temporalmente as análises
- **R03 (relacionamentos)** depende de R01 e R02 para situar pessoas e dinâmicas
- **R04 (Salus/DS21)** depende de R01 para o período agosto-outubro 2025
- **R05 (startups/IA)** complementa R04 com a frente de inovação
- **R06 (espiritualidade)** conecta com R02 e R03 via simbolismo
- **R07 (método)** documenta a infraestrutura de autoconhecimento
- **R08 (consolidação)** audita e conecta tudo

## Gate de aprovação por ciclo

Um ciclo está aprovado quando:
1. Checksums antes e depois registrados e válidos
2. Backups preservados
3. Notas com proveniência adicionada
4. Nenhuma afirmação excede a evidência
5. `versao_conteudo` atualizado
6. Matriz-Revisao-100.csv atualizado
7. Segunda passagem idempotente
8. Nenhuma regressão detectada
