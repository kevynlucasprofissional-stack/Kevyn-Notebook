---
titulo: "Relatório de auditoria — Kevyn Lucas Autoconhecimento"
tipo: relatorio_auditoria
versao: "1.0"
data: 2026-06-17
status: aprovado
---

# Relatório de auditoria

## Escopo

Auditoria estática, editorial, documental e de release do vault `Kevyn-Lucas-Autoconhecimento`, incluindo a cópia extraída do ZIP final.

## Auditorias executadas

1. inspeção de todos os arquivos do ZIP de entrada;
2. validação de formatos e codificação;
3. análise de duplicatas exatas e basenames;
4. parsing de frontmatter YAML;
5. validação de IDs e aliases;
6. resolução de wikilinks;
7. inspeção de links para cabeçalhos e blocos;
8. validação estrutural de Canvas;
9. validação de referências de arquivo em Canvas;
10. parsing de JSON e Bases;
11. validação de vocabulários controlados;
12. verificação de pastas usadas em consultas;
13. cobertura do briefing;
14. auditoria de privacidade e camadas de evidência;
15. preservação de fontes por SHA-256;
16. teste de integridade do ZIP final;
17. extração em diretório limpo;
18. comparação de árvore e hashes;
19. repetição das auditorias sobre a cópia extraída.

## Resultado estático final

| Verificação | Resultado |
|---|---:|
| arquivos auditados, excluído o próprio JSON de saída | 284 |
| Markdown | 252 |
| Canvas | 4 |
| frontmatter ausente | 0 |
| erros YAML/UTF-8 | 0 |
| IDs duplicados | 0 |
| basenames duplicados | 0 |
| aliases compartilhados | 0 |
| wikilinks | 948 |
| links quebrados | 0 |
| links ambíguos | 0 |
| notas isoladas | 0 |
| erros Canvas | 0 |
| referências Canvas quebradas | 0 |
| nomes com `#Uxxxx` | 0 |

## Auditoria complementar

| Verificação | Resultado |
|---|---:|
| campos universais ausentes | 0 |
| valores fora do vocabulário | 0 |
| JSON inválidos | 0 |
| Bases inválidas | 0 |
| arquivos vazios no vault final | 0 |
| nomes corrompidos | 0 |
| links para cabeçalho inválidos | 0 |
| links para bloco inválidos | 0 |
| consultas com pasta inexistente | 0 |
| bloqueantes | 0 |
| aprovado | sim |

## Preservação

| Material | SHA-256 |
|---|---|
| `Dados Kevyn.zip` recebido | `ffe8424369aad0631c85ab306e87b18bfd18ad49ba85fcec87c1900ce8f9ea10` |
| cópia preservada dentro do vault | `ffe8424369aad0631c85ab306e87b18bfd18ad49ba85fcec87c1900ce8f9ea10` |
| `00-BRIEFING.md` recebido | `f5ed55da1ce801711a9c2da98bfffed154b1785e393b8befa1cb34a76d363cf5` |
| cópia preservada dentro do vault | `f5ed55da1ce801711a9c2da98bfffed154b1785e393b8befa1cb34a76d363cf5` |

As duas comparações são idênticas byte a byte.

## Validação pós-ZIP

- integridade `testzip`: aprovada;
- única raiz no ZIP: `Kevyn-Lucas-Autoconhecimento`;
- arquivos produzidos: 285;
- arquivos extraídos: 285;
- ausentes: 0;
- extras: 0;
- divergências SHA-256: 0;
- retorno do auditor sobre a cópia: 0;
- links quebrados na cópia: 0;
- falhas bloqueantes na cópia: 0.

## Falhas corrigidas

- 199 wikilinks inicialmente quebrados por diferenças de acentuação, pontuação e nomes legíveis;
- variantes de nomes de fontes Vontade e Diário;
- notas de auditoria e governança ainda não existentes;
- falta de índices de fontes selecionadas;
- notas isoladas;
- artefatos intermediários de auditoria removidos do release.

## Achados não bloqueantes

- 65 notas sem links de saída são majoritariamente fontes brutas, templates ou registros preservados;
- quatro notas sem links de entrada são pontos de entrada ou infraestrutura especializada;
- três arquivos têm mais de 1 MB, incluindo o ZIP de origem preservado;
- a renderização de Bases, Dataview, Kanban e Canvas não foi testada dentro do aplicativo.

## Verificações complementares

- O nome antigo não apareceu em nenhuma nota ativa do vault; as ocorrências encontradas continuam restritas a fonte bruta, backups e histórico técnico.
- A deduplicação no conjunto ativo não encontrou duplicatas exatas por `basename`, `titulo` ou `sha256`.
- A checagem de formatação em fontes automatizadas não mostrou cabeçalhos ativos com indentação artificial; os casos restantes são sublistas ou estrutura normal de Markdown.

## Integração incremental 270626

O lote `270626 Dados novos` foi auditado antes da integração e curado sem duplicatas exatas. A transcrição de 26/06/2026 entrou como fonte principal; as leituras de discurso, comunicação não verbal e a análise complementar de 12/06/2026 foram mantidas como apoio documental. A integração gerou 4 claims, 2 notas novas e 5 notas atualizadas, com rastreabilidade em `Manifesto-Fontes.csv`, `Matriz-Cobertura.csv`, `Matriz-Claims.csv` e `Estado-Integracao.json`.

### Verificação adicional

- duplicatas exatas preliminares: 0;
- fonte principal integrada: 1;
- fontes complementares arquivadas sem integração: 3;
- bloqueantes: 0.
- a `Controle-Revisao-100/Matriz-Revisao-100.csv` foi reconciliada e deixou de usar `pendente_leitura` como estado final para registros já lidos integralmente.

## Conclusão

**Release aprovado.** Não há falha crítica ou alta conhecida que impeça abertura, navegação, rastreabilidade ou preservação do vault.

## Validacao adicional 2026-06-30

A camada semantica foi reforcada sem reabrir falhas estruturais do release:

- a cobertura passou a registrar duplicatas exatas sob representante canonico, sem inflar a contagem de analise;
- a matriz de evidencias passou a explicitar a diferenca entre fonte materializada, referencia de manifesto e sintese derivada;
- `Hoor Digital` continua como referencia de manifesto no recorte ativo, sem arquivo materializado no root ativo;
- `Kevyn Lucas`, `Claims principais`, `MOC Fontes e evidencias` e `MOC Perfil e autoconhecimento` foram alinhados a esse controle;
- a regeneracao dos checksums finais foi concluida no fechamento do ciclo.
