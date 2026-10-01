# Quarantine Candidates 02

- Gerado em: 2026-04-04T11:42:50.2961019-03:00
- Objetivo: Identificar candidatos de baixo risco para quarentena sem mover nada, com base no inventario atual.

## Metodo

- Leitura de reports/01-inventory.json como base unica de inventario estrutural.
- Classificacao das areas pedidas: Google Drive (Not synced), Clones, .trash, importacao redundante e nomes genericos.
- Separacao entre candidatos de baixo risco e excecoes de risco maior quando ha conteudo nao vazio ou fronteira de sub-vault.

## Criterios

- Nenhum arquivo foi movido, apagado ou renomeado.
- Sub-vaults continuam tratados como fronteiras de risco.
- Arquivos genericos so entram como baixo risco quando sao vazios e estao em zonas de espelho/lixo/import ou equivalente muito proximo.

## Arquivos afetados

- reports/02-quarantine-candidates.md
- reports/02-quarantine-candidates.json
- logs/02-quarantine-candidates.md

## Riscos

- Google Drive (Not synced) mistura espelho/import com ao menos um sub-vault aninhado; qualquer acao futura deve ser fatiada por subarvore.
- Pastas nomeadas como importacao podem ainda conter anexos uteis; a recomendacao continua sendo manifesto revisavel, nao move direto.
- Nomes genericos fora dessas zonas foram excluidos do recorte de baixo risco para evitar quarentena indevida de rascunhos reais.

## Proximos passos

- Escolher quais pastas candidatas devem virar manifesto em _staging/.
- Validar amostras rapidas das pastas de importacao antes de qualquer move.
- Se aprovado, preparar manifestos por subarvore, respeitando fronteiras de sub-vault.

## Resumo

- Pastas candidatas: 14
- Arquivos candidatos de baixo risco: 58
- Total de candidatos nesta rodada: 72
- Candidatos de risco baixo: 71
- Candidatos de risco medio: 1
- Excecoes genericas mantidas fora do recorte de baixo risco: 7

## Pastas Candidatas

| Caminho | Arquivos | Parece | Risco | Motivo da classificacao | Recomendacao de acao |
| --- | ---: | --- | --- | --- | --- |
| Google Drive (Not synced) | 201 | espelho, import, sub-vault | medium | Raiz de espelho do Google Drive nao sincronizado. O inventario ja marcou a area como espelho/import e ha um sub-vault aninhado dentro dela. | Nao mover a raiz inteira de uma vez. Priorizar manifestos por subarvore e isolar qualquer trecho com sub-vault para revisao humana separada. |
| HOME\Clones | 232 | espelho, lixo | low | Pasta explicitamente nomeada como Clones, com alta chance de copias redundantes e baixa centralidade para navegacao do vault principal. | Preparar manifesto de quarentena por pasta e revisar apenas se algum clone ainda for ambiente ativo. |
| Google Drive (Not synced)\Meu Drive\HOME\Clones | 3 | espelho, import, lixo | low | Subarvore de clones dentro do espelho do Google Drive, reforcando o sinal de redundancia. | Candidato forte para manifesto de quarentena por pasta inteira. |
| Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash | 35 | lixo | low | Conteudo localizado em .trash, com indicio forte de descarte, sobra de importacao ou material ja removido do fluxo principal. | Candidato forte para quarentena por pasta inteira apos revisao humana rapida. |
| Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\TranscriÃ§Ã£o da reuniÃ£o de AnÃ¡lise do LanÃ§amento Semente - Ocorrida no dia 22\09 | 1 | lixo | low | Conteudo localizado em .trash, com indicio forte de descarte, sobra de importacao ou material ja removido do fluxo principal. | Candidato forte para quarentena por pasta inteira apos revisao humana rapida. |
| Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash | 18 | lixo | low | Conteudo localizado em .trash, com indicio forte de descarte, sobra de importacao ou material ja removido do fluxo principal. | Candidato forte para quarentena por pasta inteira apos revisao humana rapida. |
| Google Drive (Not synced)\Meu Drive\HOME\Nova AcrÃ³pole\.trash | 22 | lixo | low | Conteudo localizado em .trash, com indicio forte de descarte, sobra de importacao ou material ja removido do fluxo principal. | Candidato forte para quarentena por pasta inteira apos revisao humana rapida. |
| Google Drive (Not synced)\Meu Drive\HOME\Segundo CÃ©rebro\.trash | 41 | lixo | low | Conteudo localizado em .trash, com indicio forte de descarte, sobra de importacao ou material ja removido do fluxo principal. | Candidato forte para quarentena por pasta inteira apos revisao humana rapida. |
| HOME\SaaS com Kelvyn\TPM\Arquivos | 6 | import | low | Nome de pasta sugere deposito auxiliar de arquivos, separado da camada principal de notas. | Revisar amostra curta e, se confirmado o padrao, colocar a pasta inteira em manifesto de quarentena. |
| HOME\Neuron\ARQUIVOS | 5 | import | low | Pasta em caixa alta tipica de deposito bruto/importacao, com baixo volume e baixa probabilidade de ser estrutura principal de notas. | Candidato de baixo risco para manifesto por pasta. |
| Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos | 19 | espelho, import | low | Caminho explicito de dados brutos dentro de area espelho, sugerindo lote de captura ou importacao ainda nao integrado. | Quarentenar por pasta apos revisao humana curta do conteudo. |
| Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS | 19 | espelho, import | low | Subpasta explicitamente rotulada como lote total de notas, com forte sinal de dump de importacao. | Priorizar esta subpasta no manifesto antes da pasta mae, se quiser granularidade maior. |
| Google Drive (Not synced)\Meu Drive\HOME\TODAS AS NOTAS DA ACIRV | 2 | espelho, import | low | Nome de lote total de notas dentro do espelho do Google Drive, sugerindo agregacao redundante. | Candidato de baixo risco para manifesto por pasta. |
| Google Drive (Not synced)\Meu Drive\HOME\Obsidian Hormoziano-20250829T003213Z-1-001 | 4 | espelho, import | low | Nome com timestamp e sufixo de pacote indica snapshot/exportacao importada, nao uma area curada do vault principal. | Candidato forte para manifesto de quarentena por pasta inteira. |

## Arquivos Genericos de Baixo Risco

Agrupamento por pasta-matriz para revisao humana rapida. O JSON contem todos os 58 arquivos individualizados.

| Pasta matriz | Arquivos | Parece | Risco | Motivo da classificacao | Recomendacao de acao |
| --- | ---: | --- | --- | --- | --- |
| Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash | 22 | espelho, import, lixo, rascunho | low | Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | Priorizar quarentena por pasta-matriz. |
| Google Drive (Not synced)\Meu Drive\HOME\Nova AcrÃ³pole\.trash | 12 | espelho, import, lixo, rascunho | low | Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | Priorizar quarentena por pasta-matriz. |
| Google Drive (Not synced)\Meu Drive\HOME\Segundo CÃ©rebro\.trash | 11 | espelho, import, lixo, rascunho | low | Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | Priorizar quarentena por pasta-matriz. |
| Google Drive (Not synced)\Meu Drive\HOME\MESTRE\Mestre\.trash | 10 | espelho, import, lixo, rascunho | low | Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | Priorizar quarentena por pasta-matriz. |
| HOME\CÃ©rebro Profissional\Notas | 1 | rascunho | low | Nome generico e tamanho zero, sem identificacao semantica. Arquivo vazio em area de notas, com titulo genericamente criado. | Revisar rapidamente e incluir em manifesto individual ou por subpasta. |
| Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\Notas | 1 | espelho, import, rascunho | low | Arquivo em area espelho do Google Drive nao sincronizado. Nome generico e tamanho zero, sem identificacao semantica. | Revisar rapidamente e incluir em manifesto individual ou por subpasta. |
| Google Drive (Not synced)\Meu Drive\HOME\Kevyn Lucas\Dados brutos\TODAS AS NOTAS | 1 | espelho, import, rascunho | low | Arquivo em area espelho do Google Drive nao sincronizado. Nome generico e tamanho zero, sem identificacao semantica. | Revisar rapidamente e incluir em manifesto individual ou por subpasta. |

### Amostra de arquivos individualizados

- Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\novo.md | parece: espelho, import, lixo, rascunho | risco: low | motivo: Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | recomendacao: Incluir no manifesto individual ou por pasta-matriz de .trash; risco baixo por ser vazio e generico.
- Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\Sem tÃ­tulo 12.md | parece: espelho, import, lixo, rascunho | risco: low | motivo: Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | recomendacao: Incluir no manifesto individual ou por pasta-matriz de .trash; risco baixo por ser vazio e generico.
- Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\Sem tÃ­tulo 15.md | parece: espelho, import, lixo, rascunho | risco: low | motivo: Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | recomendacao: Incluir no manifesto individual ou por pasta-matriz de .trash; risco baixo por ser vazio e generico.
- Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\Sem tÃ­tulo 16.md | parece: espelho, import, lixo, rascunho | risco: low | motivo: Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | recomendacao: Incluir no manifesto individual ou por pasta-matriz de .trash; risco baixo por ser vazio e generico.
- Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\Sem tÃ­tulo 17.md | parece: espelho, import, lixo, rascunho | risco: low | motivo: Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | recomendacao: Incluir no manifesto individual ou por pasta-matriz de .trash; risco baixo por ser vazio e generico.
- Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\Sem tÃ­tulo 2.canvas | parece: espelho, import, lixo, rascunho | risco: low | motivo: Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | recomendacao: Incluir no manifesto individual ou por pasta-matriz de .trash; risco baixo por ser vazio e generico.
- Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\Sem tÃ­tulo 25.md | parece: espelho, import, lixo, rascunho | risco: low | motivo: Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | recomendacao: Incluir no manifesto individual ou por pasta-matriz de .trash; risco baixo por ser vazio e generico.
- Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\Sem tÃ­tulo 31.md | parece: espelho, import, lixo, rascunho | risco: low | motivo: Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | recomendacao: Incluir no manifesto individual ou por pasta-matriz de .trash; risco baixo por ser vazio e generico.
- Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\Sem tÃ­tulo 34.md | parece: espelho, import, lixo, rascunho | risco: low | motivo: Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | recomendacao: Incluir no manifesto individual ou por pasta-matriz de .trash; risco baixo por ser vazio e generico.
- Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\Sem tÃ­tulo 37.md | parece: espelho, import, lixo, rascunho | risco: low | motivo: Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | recomendacao: Incluir no manifesto individual ou por pasta-matriz de .trash; risco baixo por ser vazio e generico.
- Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\Sem tÃ­tulo 39.md | parece: espelho, import, lixo, rascunho | risco: low | motivo: Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | recomendacao: Incluir no manifesto individual ou por pasta-matriz de .trash; risco baixo por ser vazio e generico.
- Google Drive (Not synced)\Meu Drive\HOME\CÃ©rebro Profissional\.trash\Sem tÃ­tulo 40.md | parece: espelho, import, lixo, rascunho | risco: low | motivo: Arquivo em area espelho do Google Drive nao sincronizado. Arquivo dentro de .trash. Nome generico e tamanho zero, sem identificacao semantica. | recomendacao: Incluir no manifesto individual ou por pasta-matriz de .trash; risco baixo por ser vazio e generico.

## Excecoes Fora do Recorte de Baixo Risco

- ACIRV\Notas\00_rascunho.md | risco: medium | motivo da exclusao: arquivo nao vazio; fora das zonas mais seguras de espelho/lixo/import | recomendacao: Manter apenas como sugestao revisavel; nao tratar como candidato de baixo risco nesta rodada.
- Google Drive (Not synced)\Meu Drive\HOME\SaaS com Kelvyn\TPM\TPM Obsidian\00_rascunho.md | risco: medium | motivo da exclusao: arquivo nao vazio; dentro de sub-vault | recomendacao: Manter apenas como sugestao revisavel; nao tratar como candidato de baixo risco nesta rodada.
- HOME\Ãgora\Ãgora Obsidian\00_rascunho.md | risco: medium | motivo da exclusao: arquivo nao vazio; dentro de sub-vault; fora das zonas mais seguras de espelho/lixo/import | recomendacao: Manter apenas como sugestao revisavel; nao tratar como candidato de baixo risco nesta rodada.
- HOME\ACIRV\Notas\00_rascunho.md | risco: medium | motivo da exclusao: arquivo nao vazio; fora das zonas mais seguras de espelho/lixo/import | recomendacao: Manter apenas como sugestao revisavel; nao tratar como candidato de baixo risco nesta rodada.
- HOME\BioVision\Notas\00_rascunho.md | risco: medium | motivo da exclusao: arquivo nao vazio; fora das zonas mais seguras de espelho/lixo/import | recomendacao: Manter apenas como sugestao revisavel; nao tratar como candidato de baixo risco nesta rodada.
- HOME\GestÃ£o de Tempo\Untitled.sheet | risco: medium | motivo da exclusao: arquivo nao vazio; fora das zonas mais seguras de espelho/lixo/import | recomendacao: Manter apenas como sugestao revisavel; nao tratar como candidato de baixo risco nesta rodada.
- HOME\Kevyn Lucas\Outros\NÃ£o integrados\00_rascunho.md | risco: medium | motivo da exclusao: arquivo nao vazio; dentro de sub-vault; fora das zonas mais seguras de espelho/lixo/import | recomendacao: Manter apenas como sugestao revisavel; nao tratar como candidato de baixo risco nesta rodada.
