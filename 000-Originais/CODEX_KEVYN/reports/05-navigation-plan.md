# Navigation Plan 05

- Gerado em: 2026-04-04T11:45:00-03:00
- Objetivo: melhorar a consultabilidade do vault sem reestruturar o cofre inteiro, priorizando hubs/MOCs mínimos, aliases prováveis e reparos de links em ordem de risco.

## Método

- Reuso dos relatórios já gerados em `reports/02-inventory.*`, `reports/05-link-audit.*`, `reports/06-quarantine-candidates.*` e `reports/07-frontmatter-minimum.*`.
- Triagem de notas centrais por densidade de backlinks e conectividade local.
- Triagem de áreas valiosas porém órfãs por soma de `priority_score`, volume de notas órfãs e exclusão de áreas espelho/import evidentes.
- Busca manual pontual por títulos já existentes para distinguir "link quebrado por falta de alias" de "link quebrado por ausência real de nota".
- Nenhum rename, move, merge ou correção automática foi executado.

## Critérios

- Priorizar notas que já funcionam como polos naturais de navegação.
- Tratar `Google Drive (Not synced)/`, `HOME/Clones/` e `.venv/` como áreas de baixo valor estrutural para navegação principal.
- Não cruzar fronteiras de sub-vault em propostas de batch refactor.
- Reservar áreas pessoais densas e dossiês para intervenção mínima e revisável.

## Arquivos afetados

- `reports/05-navigation-plan.md`
- `reports/05-navigation-plan.json`
- `logs/05-navigation-plan.md`

## Resumo Executivo

- Notas centrais confirmadas: 8
- Áreas com alta orfandade e alto valor: 5
- Hubs/MOCs mínimos propostos: 5
- Aliases prioritários propostos: 10
- Frentes de reparo de links priorizadas: 5

## Notas Centrais

Estas notas já concentram backlinks suficientes para servir como ponto de entrada local, mesmo antes de qualquer reestruturação:

1. `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\O Desejo de Ser Importante (John Dewey).md`
   - 22 links de entrada, 6 de saída.
   - Bom candidato a hub conceitual da área de influência e apreciação.
2. `HOME\O Professor\00_Aleatórios\Cérebro Atômico\Dicotomia do Controle.md`
   - 22 entradas, 4 saídas.
   - Conceito transversal e já conectado a outras áreas.
3. `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Fome Humana Insaciável por Apreciação.md`
   - 20 entradas, 6 saídas.
   - Forte centralidade temática.
4. `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Universalidade da Autojustificativa.md`
   - 18 entradas, 8 saídas.
   - Boa capacidade de costurar subtemas.
5. `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\A Chave da Influência - Falar sobre o que o Outro Quer.md`
   - 20 entradas, 5 saídas.
   - Candidato natural a link de entrada da coleção.
6. `HOME\O Professor\05_PERSONA 03 - O PENDURADO\Comunicação Não Violenta\A Raiz dos Sentimentos.md`
   - 16 entradas, 6 saídas.
   - Nota forte para ancorar CNV.
7. `HOME\Cérebro Profissional\Notas\Desafio Svelte.md`
   - 17 entradas, 3 saídas.
   - Já funciona como nó operacional/projeto.
8. `HOME\Cérebro Profissional\Notas\Modelos Mentais.md`
   - Não aparece como hub por backlinks, mas tem `priority_score` 222 e volume alto de links de saída.
   - Melhor candidato a índice leve para a área profissional.

## Áreas com Alta Orfandade mas Alto Valor

Foram priorizadas áreas fora de espelhos/clones óbvios:

1. `HOME\Cérebro Profissional\Notas`
   - 79 órfãs prioritárias, score agregado 643.
   - Mistura de estratégia, marketing, IA, projetos e playbooks.
   - Melhor ganho marginal para um MOC curto e pragmático.
2. `HOME\O Professor\04_PERSONA 02 - O SOL`
   - 32 órfãs prioritárias, score 183.
   - Área já rica em conexões locais, mas ainda sem uma página-mãe explícita.
3. `HOME\O Professor\01_SELF - O IMPERADOR`
   - 39 órfãs prioritárias, score 166.
   - Coleção conceitualmente coesa e com vários alvos quebrados que na prática já existem.
4. `HOME\Kevyn Lucas\Outros`
   - 91 órfãs prioritárias, score 148.
   - Alto valor pessoal, mas alta sensibilidade semântica; demanda navegação mínima, não reorganização.
5. `HOME\ACIRV\Notas`
   - 130 órfãs prioritárias, score 89.
   - Área operacional viva, com boa chance de benefício imediato via índice funcional por tema/processo.

## Hubs/MOCs Mínimos Propostos

Propostas deliberadamente pequenas, focadas em navegação e não em taxonomia:

1. `HOME\Cérebro Profissional\Notas\MOC - Operações, IA e Projetos.md`
   - Função: apontar para `Modelos Mentais`, `Masterclasse DISC`, `Desafio Svelte` e 8-12 notas operacionais recorrentes.
   - Estrutura mínima: Estratégia, Oferta, IA, Projetos ativos, Referências de execução.
2. `HOME\O Professor\04_PERSONA 02 - O SOL\Como fazer amigos e influenciar pessoas\MOC - Influência e Relações Humanas.md`
   - Função: abrir a coleção por temas como apreciação, crítica, interesse genuíno e persuasão.
   - Deve linkar primeiro para as 5 notas mais centrais já medidas.
3. `HOME\O Professor\01_SELF - O IMPERADOR\Sobre a brevidade da vida e a firmeza do sábio\MOC - Firmeza do Sábio.md`
   - Função: reduzir a fricção de navegação estoica e absorver aliases de títulos com artigo ausente.
   - Deve usar subgrupos: injúria/ofensa, tempo/vida, autonomia/fortuna.
4. `HOME\ACIRV\Notas\MOC - Operação ACIRV.md`
   - Função: separar planejamento, métricas, eventos, cerimonial, conteúdo e SaaS.
   - Melhor rota para reduzir orfandade sem mexer em nomenclatura.
5. `HOME\Kevyn Lucas\MOC - Contexto Operacional do Kevyn.md`
   - Função: servir só como porta de entrada segura para `Kevyn Lucas - Contexto completo`, `Kevyn Lucas - Contexto extra`, `Manual de Instruções` e poucos documentos de referência.
   - Deve ser mantido curto para não amplificar ruminação nem virar dossiê novo.

## Aliases Propostos

Os casos abaixo têm boa chance de resolver links quebrados sem rename:

1. Adicionar alias `Invulnerabilidade do Sábio` em `A Invulnerabilidade do Sábio.md`.
2. Adicionar alias `Inexistência de Dano ao Sábio` em `A Inexistência de Dano ao Sábio.md`.
3. Adicionar alias `Fome Emocional vs. Fisiológica` em `Fome Emocional vs. Fisiológica.md` se o parser estiver falhando por acentuação/local de busca; antes validar se o problema é alias ou resolução entre pastas.
4. Adicionar alias `Velhice Infantil` em `A Velhice Infantil.md`.
5. Adicionar alias `Autossuficiência Absoluta` em `A Autossuficiência Absoluta.md`.
6. Adicionar alias `Fraqueza do Mal` em `A Fraqueza do Mal.md`.
7. Adicionar alias `Analogia do Médico e o Louco` em `A Analogia do Médico e o Louco.md`.
8. Adicionar alias `Natureza dos Bens do Sábio` em `A Natureza dos Bens do Sábio.md`.
9. Adicionar alias `Perfil Comportamental Alto S/C (Castro)` em `Perfil Comportamental Alto SC (Castro).md`.
10. Avaliar alias curto/sanitizado para títulos longos de princípios Carnegie, preservando o título original como canônico.

## Reparos de Links em Ordem de Risco

### Faixa 1: baixo risco, alta confiança

- Corrigir links quebrados que já apontam para notas existentes com divergência simples de artigo inicial (`A`, `O`) ou abreviação leve.
- Foco inicial:
  - `Invulnerabilidade do Sábio` -> `A Invulnerabilidade do Sábio.md`
  - `Inexistência de Dano ao Sábio` -> `A Inexistência de Dano ao Sábio.md`
  - `Velhice Infantil` -> `A Velhice Infantil.md`
  - `Autossuficiência Absoluta` -> `A Autossuficiência Absoluta.md`
  - `Fraqueza do Mal` -> `A Fraqueza do Mal.md`
  - `Analogia do Médico e o Louco` -> `A Analogia do Médico e o Louco.md`
  - `Natureza dos Bens do Sábio` -> `A Natureza dos Bens do Sábio.md`
  - `Perfil Comportamental Alto S/C (Castro)` -> `Perfil Comportamental Alto SC (Castro).md`

### Faixa 2: baixo para médio risco

- Corrigir links vazios e targets tecnicamente inválidos.
- Casos já visíveis:
  - target vazio `""`
  - links com sufixo embutido no alvo, como `Funnel do Alan.canvas|Funnel do Alan`
- Esse grupo tende a ser correção mecânica segura, mas precisa de validação do formato real em cada nota.

### Faixa 3: médio risco, mas alto retorno

- Corrigir links para notas que já existem no mesmo domínio temático e aparecem muitas vezes no relatório.
- Casos fortes:
  - `A Regra dos Dois Meses vs. Dois Anos`
  - `A Futilidade da Crítica Pública (Roosevelt vs. Taft)`
  - `O Trabalho Sob Aprovação vs. Sob Crítica`
  - `Superação Através da Comunicação (Patrick J. O'Haire)`
  - `Reforço Positivo vs. Punição (B. F. Skinner)`
  - `Existir vs. Viver`
  - `Avareza Temporal vs. Avareza Pecuniária`
- Antes de editar em lote, validar por que o resolvedor atual não encontrou arquivos que aparentemente existem; pode ser efeito de encoding, normalização ou resolução por pasta.

### Faixa 4: médio para alto risco

- Corrigir links para imagens/canvas faltantes em notas operacionais de projeto.
- Casos observados:
  - `Sprint 01.canvas`
  - `Pasted Image 20250826202725_931.png`
  - `Pasted Image 20250828195454_871.png`
- Esses reparos exigem decidir entre restaurar asset, remover link ou apontar para outro artefato.

### Faixa 5: alto risco semântico

- Links em notas pessoais densas e dossiês (`HOME\Kevyn Lucas\...`) e contextos operacionais muito sensíveis.
- Casos como `Aragorn`, `Numenor`, `Projeto de Transformação da Psique`, `O Ego e o Self` e similares devem ser resolvidos só após revisão humana, porque podem exigir criação de nota, alias deliberado ou poda semântica.

## Sequência Recomendada

1. Criar 2 MOCs mínimos primeiro:
   - `MOC - Influência e Relações Humanas`
   - `MOC - Operações, IA e Projetos`
2. Aplicar aliases de Faixa 1.
3. Revisar o resolvedor/heurística de Faixa 3 antes de editar links que já deveriam resolver.
4. Criar `MOC - Firmeza do Sábio`.
5. Só então entrar em `ACIRV` e `Kevyn Lucas` com intervenção mínima e revisável.

## Riscos

- Parte dos links quebrados pode ser falso positivo de normalização, encoding ou diferença entre basename e título canônico.
- Áreas pessoais densas podem ganhar "mais estrutura" sem realmente ganhar melhor navegação se o MOC ficar prolixo.
- `HOME\ACIRV\Notas` e `HOME\Kevyn Lucas` têm valor alto, mas também maior chance de depender de contexto humano.
- `HOME\Segundo Cérebro\SC` e espelhos correlatos parecem volumosos, mas não são prioridade de navegabilidade principal neste momento.

## Próximos Passos

1. Validar manualmente uma amostra de 10 links da Faixa 1 e 10 da Faixa 3.
2. Se a amostra confirmar o padrão, aplicar aliases mínimos nas notas-alvo.
3. Criar no máximo 3 MOCs curtos, sem mover nem renomear notas.
4. Rodar nova auditoria de links para medir redução real de orfandade e links quebrados.
