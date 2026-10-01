---
titulo: "Changelog"
tipo: changelog
versao: "1.0"
data: 2026-06-17
---

# Changelog

## 1.0 — 17 de junho de 2026

### Adicionado

- vault privado completo sobre Kevyn Lucas;
- ponto inicial, MOC geral, guia, escopo e metodologia;
- ontologia, schema e vocabulários controlados;
- notas sobre perfil, cronologia, relações, trabalho, projetos, espiritualidade, saúde, autocuidado, decisões e estudos;
- 14 MOCs e trilhas;
- 5 Bases;
- consultas Dataview e dashboard;
- 2 quadros Kanban;
- 9 templates;
- 4 Canvas;
- configuração do Graph View;
- manifesto de 2.697 fontes;
- índice de 388 conversas;
- 48 notas de proveniência;
- 53 registros brutos selecionados;
- 10 imagens únicas selecionadas;
- ZIP original e briefing preservados;
- auditorias técnicas, editoriais, de privacidade, fontes, versões e release.

### Corrigido

- 199 links internos quebrados identificados na primeira auditoria;
- variantes de acentuação e pontuação entre títulos e basenames;
- referências a fontes com nomes históricos;
- notas isoladas;
- ausência de índices de fontes e registros;
- resíduos de auditorias preliminares removidos.

### Validado

- YAML, UTF-8, IDs, basenames e aliases;
- wikilinks;
- JSON, Canvas e Bases;
- consultas e vocabulários;
- integridade do ZIP;
- comparação pós-extração por SHA-256;
- repetição das auditorias sobre a cópia extraída.

### Limitações

- Obsidian, Dataview e Kanban não foram executados no ambiente;
- o conteúdo é privado e não substitui avaliação clínica ou profissional.

## 1.1 — 18 de junho de 2026 (Auditoria e Correção)

### Corrigido

- `Estado-Integracao.json`: números falsamente declarados (36 ciclos, 155 integrados, revisão dos 100 concluída) reconciliados com a realidade;
- 101 fichas reduzidas a 100 (ARQ-101 excedente arquivada com justificativa);
- SRC mismatch em ARQ-012 corrigido (SRC-000014 → SRC-000003);
- 100 placeholders removidos das fichas (`a_classificar`, `A extrair durante a execucao`, `Pendente de revisao`);
- `Matriz-Revisao-100.csv` reconstruída de 8 para 100 registros válidos com validação programática;
- Ciclos vazios (0010-0022) documentados como sem conteúdo.

### Adicionado

- Diagnóstico inicial documentado em `95-Auditorias/diagnostico-inicial-2026-06-18.md`;
- Novo ciclo R03 documentado com resumo de execução;
- 100 fichas preenchidas com metadados verificados (hash, tamanho, caminho, camada de evidência);
- Diretório `Arquivo-Excedentes` com justificativa da ficha removida;
- Relatório final em `95-Auditorias/relatorio-final-2026-06-18.md`;
- Lista de pendências em `Pendencias-Assumidas.md`.

### Lido/Analisado

- 6 arquivos-fonte lidos integralmente (SRC-000003, SRC-000019, SRC-000020, SRC-001879, SRC-000049, SRC-000010);
- 13 arquivos-fonte analisados em profundidade via agentes (diários, dossiês, projetos);
- 2.923 arquivos indexados no Manifesto-Fontes.csv mantidos.

### Validado

- Auditoria técnica completa: 0 erros YAML, 0 erros JSON, 0 erros CSV, 0 links quebrados (não-imagem), 0 IDs duplicados reais;
- Hashes SHA-256 dos 100 arquivos canônicos verificados contra Manifesto-Fontes.csv;
- Matriz CSV com 100 registros lida e validada por parser.

### Pendências Honestas

- 78/100 arquivos ainda não lidos integralmente (marcados como "inspecionado" nas fichas);
- 97/100 fichas contêm metadados verificados mas aguardam análise aprofundada;
- Notas do vault não foram modificadas nesta sessão (foco foi correção do sistema de controle);
- Cronologia, trajetória profissional e notas temáticas aguardam integração dos achados;
- Auditoria de conteúdo, proveniência e privacidade requerem notas atualizadas.

## 1.2 - Estabilizacao pos-V3

### Corrigido

- unificacao de `Silvana` e `Avo materna` na entidade canonica `Silvanna`;
- correcao dos links internos relacionados a `Silvanna`;
- atualizacao de notas centrais, MOCs e inventario para remover a duplicidade semantica;
- remocao das notas legadas duplicadas do diretorio de relacionamentos;
- normalizacao de fontes automatizadas no bloco afetado.

### Validado

- auditoria de links internos no escopo ativo;
- auditoria de frontmatter YAML no escopo ativo;
- validacao de links quebrados no escopo completo;
- preservacao de aliases e rastreabilidade editorial em `[[Silvanna]]`;
- auditorias finais do escopo ativo e do escopo completo regeneradas;
- `CHECKSUMS-FINAL.md` e `CHECKSUMS-FINAL.txt` regenerados com o estado final.

### Pendencias

- o escopo completo ainda preserva ruido herdado em fontes brutas e controle operacional;
- futuras curadorias semanticas devem tratar esse ruido como quarentena, nao como conhecimento final.

## 1.3 - 27 de junho de 2026 (Integracao de dados novos 270626)

### Adicionado

- lote `270626 Dados novos` integrado no vault de trabalho `Kevyn Neo`;
- nota-fonte `Fonte - Reuniao com psicologa Suzana 2026-06-26`;
- estado atual datado de 27 de junho de 2026;
- matriz de claims, manifesto de fontes e matriz de cobertura atualizados para a sessao de 26/06/2026;
- auditoria inicial, auditoria final e relatorio de integracao do lote.

### Corrigido

- assuncao antiga do nome do vault, agora tratada como `Kevyn Neo` no trabalho corrente;
- fotografia temporal atualizada para 27 de junho de 2026;
- separacao entre transcricao bruta e analises derivadas mantida de forma explicita;
- pendencia da segunda sessao de 26/06/2026 substituida pelo registro real da continuidade.

### Validado

- 4 arquivos de entrada do lote;
- 1 fonte principal integrada;
- 3 analises derivadas arquivadas sem integracao central;
- checksums antes/depois do lote gerados;
- proxima sessao terapeutica registrada para 10/07/2026.

## 1.4 - 28 de junho de 2026 (Ajuste final da matriz de revisao 100)

### Corrigido

- `Controle-Revisao-100/Matriz-Revisao-100.csv`: `status_final` reconciliado de `pendente_leitura` para `analisado_nao_integrado` em todo o conjunto;
- a matriz passou a refletir que os 100 registros foram lidos integralmente e extraidos, mas nao integrados como notas curadas;
- a documentacao de controle passou a distinguir revisao concluida de integracao efetiva.

### Validado

- `status_leitura = lido_integralmente` e `status_extracao = extraido` agora combinam com `status_final = analisado_nao_integrado`;
- a contradicao de estado final deixou de existir no arquivo da revisao 100.

## 1.5 - 30 de junho de 2026 (Curadoria semantica e cobertura)

### Adicionado

- `Controle-Integracao/Matriz-Evidencias.csv` para separar evidencias, localizador e sensibilidade;
- expansao de `Controle-Integracao/Matriz-Claims.csv` com claims nucleares, de metodo e parciais;
- nota central `Kevyn Lucas` realinhada ao conjunto de claims e evidencias;
- `Claims principais`, `MOC Perfil e autoconhecimento`, `MOC Fontes e evidencias` e as trilhas principais atualizadas para a nova camada de controle.

### Corrigido

- `Manifesto-Fontes.csv` e `Matriz-Cobertura.csv` passaram a ser lidos com representacao canonica para duplicatas exatas;
- `Hoor Digital` permaneceu como referencia de manifesto no recorte ativo, sem arquivo materializado no root ativo;
- a leitura da cobertura deixou de confundir inventario, analise direta e cobertura semantica.

### Validado

- a camada de claims agora referencia IDs de claim e de evidencia de forma consistente;
- o estado de integracao e o acumulado registram a regra de cobertura canonica;
- a regeneracao dos checksums finais foi concluida no fechamento do ciclo.

