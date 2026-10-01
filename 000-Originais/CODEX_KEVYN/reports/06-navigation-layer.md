# Navigation Layer 06

- Gerado em: 2026-04-04T12:20:00-03:00
- Objetivo: aumentar a consultabilidade do vault com uma camada de navegação mínima, sem reorganizar o cofre inteiro e sem mover notas.

## Método

- Reuso do inventário já existente e do plano em `reports/05-navigation-plan.md`.
- Triagem manual dos cinco domínios pedidos: `Segundo Cérebro`, `O Professor`, `Cérebro Profissional`, `Kevyn Lucas` e `ACIRV`.
- Criação de um índice-raiz e de hubs/MOCs locais com poucos links de alta utilidade.
- Inclusão de aliases apenas nas notas novas; para notas antigas, os aliases ficaram como sugestão revisável dentro dos hubs.

## Critérios

- Não mover, renomear ou fundir notas.
- Priorizar notas centrais, contexto operacional e pontos de entrada curtos.
- Respeitar fronteiras de sub-vault, especialmente `HOME/Kevyn Lucas/`.
- Evitar promover áreas de espelho/import como navegação principal.

## Arquivos afetados

- `Índice do Vault.md`
- `HOME/Segundo Cérebro/MOC - Segundo Cérebro.md`
- `HOME/O Professor/MOC - O Professor.md`
- `HOME/Cérebro Profissional/MOC - Cérebro Profissional.md`
- `HOME/Kevyn Lucas/MOC - Kevyn Lucas.md`
- `ACIRV/MOC - ACIRV.md`
- `reports/06-navigation-layer.md`
- `logs/06-navigation-layer.md`

## Resultado

- 1 índice-raiz criado no vault.
- 5 hubs/MOCs criados para os domínios obrigatórios.
- 22 links de navegação principal adicionados entre notas centrais e hubs.
- 19 sugestões de aliases registradas sem alterar notas antigas.

## Decisões

- `ACIRV/` foi usado como domínio principal de navegação, evitando promover o espelho em `HOME/ACIRV/`.
- `HOME/Kevyn Lucas/` recebeu um hub deliberadamente curto por ser sub-vault e por conter material sensível.
- `O Professor` foi estruturado em torno de dois polos já fortes no relatório anterior: relações humanas e estoicismo.
- `Segundo Cérebro` foi tratado como domínio de arquitetura do sistema, conectando fundamentos e operação do cofre.

## Riscos

- Alguns links podem competir com notas duplicadas em áreas espelho se o resolvedor do Obsidian privilegiar títulos idênticos sem caminho.
- Os aliases sugeridos para notas antigas ainda dependem de revisão humana e aplicação posterior.
- A camada criada melhora entrada e descoberta, mas não resolve por si só links quebrados legados nem duplicação estrutural.

## Próximos passos

1. Validar na interface do Obsidian se os hubs aparecem bem no Quick Switcher e no grafo local.
2. Aplicar aliases de baixo risco nas notas antigas mais acessadas.
3. Rodar nova auditoria de links para medir se a camada de navegação reduziu orfandade percebida.
