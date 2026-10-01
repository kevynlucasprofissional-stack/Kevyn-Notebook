# 04 — Plano de Ciclos

## Ciclo R01 — Fundação Cronológica

- **Prioridades atendidas**: P0, P1
- **Arquivos (17)**: SRC-000019, 000020, 000010, 000011, 000012, 000013, 000016, 000017, 000018, 000084, 000086, 000087, 000088, 000095, 000009, 002906, 002907, 002908, 002909, 002910
- **Objetivo**: Revisar cronologia completa — datas, períodos, eventos e a narrativa temporal do vault
- **Notas a revisar**: Linha do tempo mestre, Origens e infância 2003-2021, Crise e reorganização 2025, Incêndio 2025, Independência 2021-2024, Diários de 2026, Integração 2026
- **Operações prováveis**: ampliar_nota, adicionar_cronologia, adicionar_contexto, criar_relacao
- **Auditoria**: validação de datas, consistência temporal, ausência de anacronismo
- **Dependências**: Nenhuma
- **Resultado esperado**: Timeline detalhada com eventos, pessoas e contextos por período

## Ciclo R02 — Psique e Autoimagem

- **Prioridades atendidas**: P0, P1
- **Arquivos (13)**: SRC-000247, 000248, 000250, 000312, 000257, 000277, 000278, 000309, 000319, 000337, 000338, 000329, 000281
- **Objetivo**: Integrar análises psicológicas, mapeamento arquetípico e diagnósticos diferenciais
- **Notas a revisar**: Kevyn Lucas, Contradições centrais, Mapa de qualidades, Mapa de dificuldades, Hipóteses abertas, Narrativa de grandeza, Relação com complexidade
- **Operações prováveis**: ampliar_nota, criar_nota, adicionar_proveniencia, atualizar_yaml
- **Auditoria**: camada de evidência, grau de confiança, rótulo de interpretação de IA
- **Dependências**: R01 (cronologia como âncora temporal)
- **Resultado esperado**: Perfil cognitivo documentado, estrutura Self/Ego/Anima/Sombra mapeada

## Ciclo R03 — Relacionamentos e Rede

- **Prioridades atendidas**: P1
- **Arquivos (9)**: SRC-000252, 000258, 000291, 000292, 000322, 000251, 000259, 000293, 000266
- **Objetivo**: Aprofundar dinâmica relacional — história com Mari, Chá e Prosa, conceito de tribo
- **Notas a revisar**: Mari, Chá e Prosa, Tribo, Amor idealização, Amor intimidade, Rede de relações, Paulinho
- **Operações prováveis**: ampliar_nota, criar_relacao, adicionar_contexto, mover_conteudo
- **Risco**: Sensibilidade muito alta — aplicar minimização rigorosa de dados
- **Auditoria**: privacidade, exposição de terceiros, sensibilidade
- **Dependências**: R01 (cronologia), R02 (autoimagem para contexto relacional)
- **Resultado esperado**: Relações com contexto temporal e narrativo, sem exposição indevida

## Ciclo R04 — Trabalho — Salus/DS21

- **Prioridades atendidas**: P0, P1
- **Arquivos (6)**: SRC-000052, 000128, 000131, 000067, 000110, 000103
- **Objetivo**: Documentar o projeto mais extenso com métricas reais, linha editorial e planejamento técnico
- **Notas a revisar**: Salus e Desafio Svelte, Salus e Capital Green, Marketing, Portfolio, Inteligência artificial
- **Operações prováveis**: ampliar_nota, adicionar_proveniencia, adicionar_contexto, criar_relacao, atualizar_yaml
- **Auditoria**: métricas confirmadas vs estimadas, camada de evidência dos clones IA
- **Dependências**: R01 (cronologia do período Salus)
- **Resultado esperado**: DS21 com métricas, papéis da equipe, linha editorial e aprendizados

## Ciclo R05 — Trabalho — IA, Startups e Consultoria

- **Prioridades atendidas**: P1, P2
- **Arquivos (10)**: SRC-000050, 000039, 000040, 000051, 000059, 000079, 000200, 000204, 000212, 000453
- **Objetivo**: Documentar frente de IA, startups submetidas (Ágora, Poup App), contrato Midas, consultoria WSI
- **Notas a revisar**: Inteligência artificial, Portfolio, Negócios, Sustentabilidade financeira, Projeto Cosmo
- **Operações prováveis**: ampliar_nota, criar_nota, criar_relacao
- **Auditoria**: confirmação de submissão vs ideação para startups
- **Dependências**: R01 (cronologia), R04 (contexto Salus)
- **Resultado esperado**: Projetos documentados com status, evidência e contexto

## Ciclo R06 — Espiritualidade, Simbolismo e Estados Alterados

- **Prioridades atendidas**: P1, P2
- **Arquivos (11)**: SRC-000111, 000298, 000346, 000081, 000109, 000334, 000348, 000318, 000646, 000889, 000928
- **Objetivo**: Aprofundar dimensão espiritual, experiências enteogênicas e frameworks simbólicos
- **Notas a revisar**: Espiritualidade, Thelema, Santo Daime, Alquimia, Tarot, Experiências com substâncias, Sonhos
- **Operações prováveis**: ampliar_nota, adicionar_contexto, criar_relacao, atualizar_moc
- **Auditoria**: camada simbólico_espiritual, rótulo de interpretação, confiança
- **Dependências**: R02 (psique como contexto)
- **Resultado esperado**: Práticas espirituais documentadas com contexto e limitação epistêmica

## Ciclo R07 — Método, Estudo e Competências

- **Prioridades atendidas**: P2, P3
- **Arquivos (14)**: SRC-000004, 000005, 000272, 000273, 000152, 000215, 002912, 002913, 002916, 000186, 000003, 000006, 000007, 000008
- **Objetivo**: Documentar metodologia de autoconhecimento, frameworks e evolução de competências
- **Notas a revisar**: Método de estudo, Organização do conhecimento, Vontade SMART, Disciplina, Tecnologias de si, Estilo de aprendizagem, Formação em Data Science
- **Operações prováveis**: ampliar_nota, adicionar_proveniencia, criar_relacao
- **Dependências**: Nenhuma obrigatória
- **Resultado esperado**: Frameworks documentados com evolução temporal e aplicações

## Ciclo R08 — Consolidação, Conexões e Auditoria

- **Prioridades atendidas**: P2, P3
- **Arquivos**: Todos os 100 (segunda passagem)
- **Objetivo**: Verificar idempotência, consolidar duplicações, conectar temas transversais, auditar
- **Notas a revisar**: Todas as ~40 notas modificadas nos ciclos R01-R07
- **Operações prováveis**: consolidar_duplicacao, corrigir_relacao, atualizar_moc, atualizar_indice
- **Auditoria**: completa — UTF-8, YAML, links, IDs, basenames, Canvas, Bases, Dataview, proveniência, segredos
- **Dependências**: R01 a R07 concluídos
- **Resultado esperado**: Vault consistente, rastreável, com segunda passagem idempotente confirmada
