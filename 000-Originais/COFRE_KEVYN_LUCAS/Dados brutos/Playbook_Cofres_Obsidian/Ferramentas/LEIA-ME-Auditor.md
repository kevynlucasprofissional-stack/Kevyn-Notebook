---
titulo: "Ferramenta de auditoria estática"
tipo: documentacao_tecnica
versao: "1.0"
data: 2026-06-17
---

# Ferramenta de auditoria estática

## Arquivo

`auditar_vault.py`

## Objetivo

Executar uma primeira inspeção não destrutiva de um vault Obsidian:

- arquivos por extensão;
- frontmatter ausente;
- YAML inválido;
- IDs e basenames duplicados;
- aliases compartilhados;
- wikilinks quebrados ou ambíguos;
- notas sem entrada, sem saída ou isoladas;
- JSON Canvas inválido;
- referências de arquivo quebradas em Canvas;
- sequências suspeitas `#Uxxxx` em nomes;
- arquivos inesperadamente grandes;
- distribuição de palavras por tipo;
- hashes SHA-256.

## Requisito

```bash
pip install pyyaml
```

## Uso

```bash
python auditar_vault.py "/caminho/do/vault" --output relatorio.json
```

Exclusões podem ser repetidas:

```bash
python auditar_vault.py "/caminho/do/vault" \
  --exclude "Processo/**" \
  --exclude "*.bak" \
  --output relatorio.json
```

## Código de saída

- `0`: nenhuma falha bloqueante detectada pelo conjunto básico;
- `1`: existe YAML/UTF-8 inválido, ID duplicado, link quebrado ou falha Canvas;
- `2`: erro de execução ou caminho inválido.

## Limitações

- não abre o Obsidian;
- não executa Dataview, Bases ou Templater;
- aproxima a resolução de links por caminho e basename;
- ignora links em blocos de código e código inline;
- não valida semanticamente cabeçalhos e block IDs;
- não substitui revisão conceitual, editorial ou bibliográfica.

Use o script como camada de detecção. Um relatório de auditoria precisa interpretar cada achado por tipo, centralidade e severidade.
