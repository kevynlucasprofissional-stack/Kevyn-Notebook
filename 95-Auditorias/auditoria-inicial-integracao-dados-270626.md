---
id: auditoria-inicial-integracao-dados-270626
titulo: Auditoria inicial da integracao de dados 270626
tipo: auditoria
status: rascunho
profundidade: avancada
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-06-27
ultima_revisao: 2026-06-27
grau_confianca: medio_alto
sensibilidade: alta
camada_evidencia: sintese_derivada
tags:
  - tipo/auditoria
  - processo/integracao
  - privacidade/restrita
---

# Auditoria inicial da integracao de dados 270626

## Escopo

Snapshot inicial do lote localizado em `C:\Users\Kevyn Lucas\Documents\Vault Neo\Dados Kevyn\270626 Dados novos`, antes da integracao curada no vault `Kevyn Neo`.

## Inventario da entrada

- Arquivos novos identificados: 4
- Duplicatas exatas preliminares no vault: 0
- Versoes atualizadas detectadas preliminarmente: 0
- Fontes complementares/derivadas: 3
- Fonte principal para integracao: 1

## Arquivos do lote

| Arquivo | Tamanho | SHA-256 | Data de modificacao UTC | Leitura preliminar | Destino preliminar |
|---|---:|---|---|---|---|
| `260626 às 16h - Reunião com a Psicóloga Suzana - Transcrição.txt` | 45127 | `B40A509AE3ECE6ACC96287B770AFCB5D8EF1339D0DB78F424D18338CA00BDED3` | 2026-06-27 01:21:54 | texto legivel | integrar como fonte principal |
| `260626 às 16h - Reunião com a Psicóloga Suzana - Análise do discurso.txt` | 225694 | `4E2DB2F484BA0FB55E3565A17DFFF5178E4A125B4DF1EE995F3C0C1F9AE7DB4F` | 2026-06-27 14:16:09 | texto legivel | preservar como fonte complementar |
| `260626 às 16h - Reunião com a Psicóloga Suzana - Análise da comunicação não verbal.txt` | 39568 | `95204DBE4327E24999315F9C97A1A73D6B58F3FCF781F2FA82E315472430665F` | 2026-06-27 18:00:22 | texto legivel | preservar como fonte complementar |
| `120626 às 9h - Reunião com a Psicóloga Suzana - Análise da comunicação não verbal.txt` | 35784 | `00199CA8D659D89ED0866D97755CC89D4A19C43975E587DFBC993A9AC091D02D` | 2026-06-27 17:41:48 | texto legivel | preservar como fonte complementar |

## Baseline de controle

- Total de fontes registradas no controle antes desta integracao: 2923
- Links quebrados no escopo ativo, segundo o estado estabilizado anterior: 0
- Links quebrados no escopo completo, segundo o estado estabilizado anterior: 2451
- YAML invalido conhecido no escopo ativo: 0
- JSON invalido conhecido no escopo ativo: 0
- Arquivos `.pyc` conhecidos no escopo ativo: 0
- Pastas `__pycache__` conhecidas no escopo ativo: 0
- Frontmatter ausente no escopo ativo: 0
- Duplicatas exatas no escopo ativo: 0

## Leitura inicial

O lote novo nao parece repetir byte a byte nenhuma fonte ja catalogada. O arquivo principal e a transcricao de 26/06/2026; os demais arquivos sao leituras derivadas e entram como apoio documental, nao como substitutos do registro bruto.

## Hipoteses de destino

- A transcricao deve gerar a nova nota-fonte curada.
- As analises derivadas devem permanecer como suporte complementar e registro de contexto, sem inflar a camada central.
- O acompanhamento psicologico, a cronologia e o estado atual precisam ser atualizados com a sessao de 26/06/2026.

## Limites

- Este snapshot nao substitui a auditoria final.
- A validacao completa de links, anexos e checksums finais acontece depois da integracao.
- A leitura epistemica continua cautelosa: sintese, interpretacao e fato bruto permanecem separados.
