# 07 — Critérios de Aceite

## Por ciclo (R01-R08)

### Pré-execução
- [ ] Diretório do ciclo criado com Checksums-Antes.txt
- [ ] Backups das notas afetadas preservados
- [ ] Plano-de-Mudancas.md escrito antes da primeira edição

### Execução
- [ ] Todos os arquivos do ciclo relidos integralmente
- [ ] Hashes das fontes validados (não foram alteradas)
- [ ] Extração de entidades documentada nas fichas
- [ ] Comparação com vault documentada (presença, completude, profundidade)
- [ ] Operações executadas conforme plano (com registro de desvios)

### Pós-execução
- [ ] Notas modificadas com proveniência adicionada
- [ ] Nenhuma afirmação excede a evidência disponível
- [ ] `versao_conteudo` incrementado conforme convenção do vault
- [ ] `ultima_revisao` atualizado para a data real
- [ ] Dados sensíveis minimizados
- [ ] Nenhum segredo incorporado

### Auditoria
- [ ] YAML válido em todas as notas modificadas
- [ ] IDs sem duplicação
- [ ] Links resolvem (sem broken links)
- [ ] Camadas de evidência declaradas e coerentes
- [ ] Vocabulários controlados respeitados
- [ ] Checksums-Depois.txt corresponde ao estado real
- [ ] Segunda passagem não encontra correção material nova

## Por arquivo

- [ ] Ficha ARQ-XXX.md preenchida com todos os campos
- [ ] Linha na Matriz-Revisao-100.csv atualizada
- [ ] Relação com Kevyn classificada
- [ ] Cobertura atual avaliada
- [ ] Operações propostas priorizadas
- [ ] Decisão documentada (integrar / postergar / fora do escopo)

## Globais (pós R08)

- [ ] 100 arquivos cobertos pelo plano
- [ ] 100 fichas preenchidas
- [ ] 8 ciclos executados e aprovados
- [ ] Matriz-Revisao-100.csv completo e consistente
- [ ] Nenhuma regressão em notas não afetadas
- [ ] CHECKSUMS-PLANEJAMENTO.txt válido
- [ ] Auditoria final: 0 broken links, 0 YAML errors, 0 duplicate IDs
- [ ] Gate global: SIM
