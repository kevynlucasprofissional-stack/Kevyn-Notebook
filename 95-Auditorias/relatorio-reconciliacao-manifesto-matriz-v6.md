---
id: relatorio-reconciliacao-manifesto-matriz-v6
titulo: Relatorio de reconciliacao manifesto-matriz v6
tipo: auditoria
status: concluido
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-06-30
ultima_revisao: 2026-06-30
escopo: reconciliacao_manifesto_matriz
---

# Relatorio de reconciliacao manifesto-matriz v6

## Contexto

Este relatorio fecha a reconciliacao entre `Manifesto-Fontes.csv`, `Matriz-Cobertura.csv`, `Matriz-Evidencias.csv` e `Matriz-Claims.csv`.

A regua adotada foi simples e explicita: duplicata exata nao vira nova analise individual; ela entra como `coberto_por_duplicata` sob o representante canonico.

## Numeros-base

| Item | Valor |
|---|---:|
| Linhas do manifesto | 2927 |
| Linhas da matriz de cobertura | 2927 |
| Hashes unicos | 1268 |
| Duplicatas exatas | 1659 |
| Claims | 19 |
| Evidencias | 31 |
| Notas curadas | 121 |

## O que foi reconciliado

- A cobertura passou a distinguir analise direta de cobertura por duplicata exata.
- O manifesto historico nao foi reescrito; a matriz e que passou a explicitar o estado real da fonte.
- `SRC-000726` ficou marcado como referencia de manifesto para `Hoor Digital`, sem arquivo materializado no recorte ativo.
- `Matriz-Evidencias.csv` cresceu ate 31 linhas e deu lastro para os claims centrais.
- `Matriz-Claims.csv` consolidou 19 claims, suficientes para o nucleo biografico atual.

## Decisoes editoriais

- `Kevyn Lucas` virou o centro narrativo e metodologico do vault.
- `MOC Geral`, `MOC Fontes e evidencias` e `Claims principais` agora apontam para a camada de controle.
- As notas de convergencia foram separadas em `Vinculo`, `Controle e incerteza` e `Autoconhecimento como projeto`.
- `Inteligencia artificial e automacao` passou a ser lida como extensao cognitiva e nao como prova automatica de senioridade tecnica.

## Risco residual

- A reconciliacao encerra a divergencia semantica principal, mas nao elimina ruido historico, backups e material bruto.
- O recorte ativo segue sendo o unico lugar onde a contagem deve ser tratada como prova de curadoria.
