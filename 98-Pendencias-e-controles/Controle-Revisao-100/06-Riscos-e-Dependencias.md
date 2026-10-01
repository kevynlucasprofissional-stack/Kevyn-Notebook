# 06 — Riscos e Dependências

## Riscos editoriais

| Risco | Prob | Impacto | Mitigação |
|---|---|---|---|
| Sobrecarga da nota Kevyn Lucas (14 fontes) | Alta | Alto | Monitorar tamanho; dividir em subnotas se >100 linhas |
| Exposição de dados sensíveis (Mari, Suzana) | Alta | Alto | Revisão dedicada de privacidade no fim de cada ciclo |
| Interpretação de IA tratada como fato | Média | Alto | Auditoria de camada de evidência em toda nova afirmação |
| Dados pessoais de terceiros expostos | Média | Alto | Minimização: generalizar nomes e detalhes |
| Regressão em notas estáveis | Baixa | Médio | Checksums antes/depois; backup por ciclo |
| Contradição entre diários (versões diferentes) | Média | Médio | Registrar ambas com datas; não forçar síntese |
| Perda de nuance simbólica ao "traduzir" para factual | Média | Médio | Preservar registro simbólico em seções rotuladas |

## Riscos técnicos

| Risco | Prob | Impacto | Mitigação |
|---|---|---|---|
| PyYAML ausente para auditoria completa | Alta | Médio | Scripts PowerShell complementares |
| Arquivos .obsidian alterando entre snapshots | Alta | Baixo | Fechar Obsidian antes do checksum final |
| Encoding problem em arquivos com acentos | Baixa | Médio | Ler sempre como UTF-8; validar caracteres |
| SHA-256 calculado sobre texto (não bytes) | Baixa | Alto | Get-FileHash obrigatório; proibir hash de string |

## Dependências entre ciclos

```
R01 (cronologia)
├── R02 (psique) ── depende de R01 para contexto temporal
├── R03 (relacionamentos) ── depende de R01 e R02
├── R04 (Salus/DS21) ── depende de R01 para período ago-out/2025
│   └── R05 (startups/IA) ── complementa R04
├── R06 (espiritualidade) ── depende de R02 para contexto psicológico
├── R07 (método) ── independente
└── R08 (consolidação) ── depende de todos os anteriores
```

## Riscos operacionais

| Risco | Mitigação |
|---|---|
| Sessão exceder limite de contexto | Fechar ciclo atual antes do limite; salvar estado |
| Arquivo-fonte corrompido ou ilegível | Registrar na ficha; classificar como bloqueado |
| SRC-000103 (credenciais) lido acidentalmente | Já redigido; manter classificação; não reler |
