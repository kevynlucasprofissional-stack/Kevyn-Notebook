---
id: auditoria-inicial-v6-curadoria-semantica
titulo: Auditoria inicial v6 - curadoria semantica
tipo: auditoria
status: concluido
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-06-28
ultima_revisao: 2026-06-28
escopo: inicial
---

# Auditoria inicial v6 - curadoria semantica

## Contexto

Este arquivo registra a linha de base do Kevyn Neo antes da reconciliação principal de inventario, rastreabilidade e curadoria semantica.

Para evitar interferencia no proprio escopo ativo, a medicao foi feita com a mesma regua do auditor tecnico do cofre:

- excluindo `.obsidian`;
- excluindo a saida operacional de auditoria usada pelo proprio processo;
- mantendo arquivos historicos, backups e controle legado dentro do escopo completo.

## Panorama rapido

- A arvore bruta do vault tem 1.873 arquivos e 230 pastas.
- O escopo de auditoria completo tem 1.864 arquivos e 173 pastas.
- O escopo ativo esta limpo no momento deste snapshot: 0 links quebrados, 0 frontmatter ausente, 0 basenames duplicados.
- O escopo completo ainda carrega ruido historico relevante, principalmente em backups, ciclos e arquivos de controle.

## Diagnostico tecnico

| Medida | Escopo ativo | Escopo completo |
|---|---:|---:|
| Arquivos | 1.144 | 1.864 |
| Pastas | 22 | 173 |
| Markdown | 1.104 | 1.416 |
| Palavras aproximadas | 397.926 | 533.587 |
| Wikilinks | 4.659 | 6.307 |
| Links quebrados | 0 | 2.513 |
| Frontmatter ausente | 0 | 225 |
| YAML invalido | 0 | 0 |
| JSON invalido | 0 | 0 |
| CSV invalido | 0 | 0 |
| Basenames duplicados | 0 | 35 |
| Anexos ausentes | 0 | 0 |
| Arquivos `.pyc` | 0 | 0 |
| Pastas `__pycache__` | 0 | 0 |

## Inventario

- `Controle-Integracao/Manifesto-Fontes.csv`: 2.927 linhas.
- `Controle-Integracao/Matriz-Cobertura.csv`: 2.927 linhas.
- `Controle-Integracao/Matriz-Claims.csv`: 4 claims.
- `Controle-Integracao/Matriz-Evidencias.csv`: ausente.

### Manifesto x Matriz

O inventario ja cobre 100% das fontes catalogadas, mas a cobertura ainda esta semanticamente inconsistente:

- o manifesto distingue `nao_analisado` e `analisado`;
- a matriz atual uniformiza tudo como `analisado`;
- o manifesto registra 1.657 fontes como `nao_analisado` e 1.270 como `analisado`;
- a matriz registra 2.927 fontes como `analisado`.

Isso precisa ser reconciliado para que a matriz deixe de afirmar analise individual quando a fonte foi apenas coberta por duplicata.

### Hashes

- Hashes unicos no manifesto: 1.268.
- Hashes repetidos: 865.
- Linhas do manifesto associadas a hashes duplicados: 1.659.
- Linhas com `duplicata_exata_de` preenchido: 1.659.

## Claims e evidencias

- O vault ainda opera com apenas 4 claims registradas na matriz atual.
- A matriz de evidencias ainda nao existe.
- Isso significa que a rastreabilidade fonte -> evidencia -> claim ainda esta incompleta no nivel estrutural.

## Checksums

O arquivo `CHECKSUMS-FINAL.txt` atual apresenta 1 divergencia em relacao ao estado do vault:

- `Controle-Integracao/Estado-Integracao.json`

## Observacoes principais

1. O escopo ativo nao tem ruido estrutural no momento do snapshot.
2. O escopo completo ainda preserva 2.513 links quebrados e 225 arquivos Markdown sem frontmatter.
3. A divergencia principal do projeto segue sendo semantica e documental, nao de existencia de fontes.
4. A primeira prioridade de curadoria e alinhar manifesto, matriz e cobertura real das fontes.
5. A segunda prioridade e criar a matriz de evidencias para sustentar claims centrais.
6. A terceira prioridade e ampliar claims e notas curadas sem inflar volume.

## Proximo passo

Reconciliar `Manifesto-Fontes.csv` com `Matriz-Cobertura.csv`, registrar a regra de cobertura adotada e partir para a matriz de evidencias e claims.
