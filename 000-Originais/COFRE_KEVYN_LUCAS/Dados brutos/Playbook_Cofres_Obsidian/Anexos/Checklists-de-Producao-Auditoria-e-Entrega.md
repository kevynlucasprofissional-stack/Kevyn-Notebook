---
titulo: "Checklists de produção, auditoria e entrega"
tipo: anexo_operacional
versao: "1.0"
data: 2026-06-17
---

# Checklists de produção, auditoria e entrega

## 1. Como aplicar os checklists

Cada etapa termina em um **gate**. A próxima etapa só começa quando:

- todos os itens bloqueantes foram cumpridos;
- exceções estão registradas como pendências qualificadas;
- métricas foram produzidas por inspeção real, não estimadas;
- a evidência da verificação foi salva.

### Severidades

| Severidade | Definição | Efeito no release |
|---|---|---|
| crítica | impede abertura, navegação ou confiabilidade básica | bloqueia entrega |
| alta | quebra parte importante do sistema ou produz afirmação enganosa | bloqueia até correção ou rebaixamento explícito |
| média | reduz qualidade, cobertura ou manutenção | pode ser aceita com pendência |
| baixa | melhoria editorial ou cosmética | não bloqueia |

## 2. Gate 0 — Capacidade e materiais

- [ ] Todos os anexos prometidos estão acessíveis.
- [ ] ZIPs foram extraídos em diretório de trabalho, preservando o original.
- [ ] PDFs, imagens, planilhas e bancos foram lidos com ferramenta apropriada.
- [ ] Limitações do ambiente foram registradas.
- [ ] A IA consegue criar arquivos reais e compactá-los.
- [ ] A IA consegue executar validações de YAML, links e JSON.
- [ ] O tema não exige especialista humano obrigatório antes da publicação.
- [ ] A pesquisa online está autorizada quando necessária.
- [ ] Não há conflito entre instruções dos anexos e o pedido do usuário.

**Gate:** nenhum material crítico está ilegível ou ausente sem registro explícito.

## 3. Gate 1 — Interpretação e escopo

### Pergunta central

- [ ] A pergunta central cabe em uma frase.
- [ ] O cofre tem um propósito principal: estudar, pesquisar, operar, decidir, documentar ou ensinar.
- [ ] O público está definido.
- [ ] O nível de profundidade está definido.
- [ ] O horizonte temporal está definido.
- [ ] A área geográfica ou institucional está definida quando aplicável.

### Inclusões e exclusões

- [ ] Há lista de entidades obrigatórias.
- [ ] Há lista de tipos de nota obrigatórios.
- [ ] Há exclusões explícitas.
- [ ] Termos ambíguos foram resolvidos.
- [ ] O que é “completo” foi transformado em critérios observáveis.
- [ ] O que pode permanecer pendente está descrito.

### Entregáveis

- [ ] Pasta raiz nomeada.
- [ ] Formatos de entrega definidos.
- [ ] Plugins permitidos definidos.
- [ ] Necessidade de `.obsidian` definida.
- [ ] Necessidade de ZIP definida.
- [ ] Relatórios e auditorias finais definidos.

**Gate:** ficha de escopo aprovada internamente e sem contradições.

## 4. Gate 2 — Pesquisa e autoridade

- [ ] Existe hierarquia de fontes por tipo de afirmação.
- [ ] Fontes primárias foram identificadas.
- [ ] Documentação oficial foi priorizada para aspectos técnicos.
- [ ] Fontes secundárias especializadas foram identificadas.
- [ ] Fontes comunitárias têm uso limitado e declarado.
- [ ] Informações temporalmente voláteis têm data de verificação.
- [ ] Cada afirmação central tem caminho de evidência planejado.
- [ ] Lacunas de fonte não foram preenchidas por invenção.
- [ ] Controvérsias possuem fontes de mais de uma posição.
- [ ] Referências têm dados mínimos para serem localizadas novamente.

**Gate:** matriz fonte → afirmação central está preenchida.

## 5. Gate 3 — Ontologia

- [ ] Cada tipo de nota tem definição em uma frase.
- [ ] Tipos não são meras pastas.
- [ ] Cada nota terá um tipo principal.
- [ ] Há regra para casos híbridos.
- [ ] Relações possuem vocabulário controlado.
- [ ] A direção das relações está definida.
- [ ] Relações simétricas e assimétricas estão distinguidas.
- [ ] Relações fortes que exigem nota própria estão definidas.
- [ ] Camadas de evidência/confiança estão definidas.
- [ ] Tipos e relações foram testados em pelo menos dez exemplos reais.
- [ ] Não existe categoria final `relacionado_a` sem refinamento.

**Gate:** diagrama ou tabela da ontologia validada com exemplos e contraexemplos.

## 6. Gate 4 — Convenções e schema

- [ ] Convenção de basename definida.
- [ ] Convenção de título legível definida.
- [ ] Política de acentos e caracteres proibidos definida.
- [ ] Política de aliases definida.
- [ ] Campos universais definidos.
- [ ] Campos específicos por tipo definidos.
- [ ] Valores controlados documentados.
- [ ] Datas usam padrão consistente.
- [ ] Versão e status estão separados.
- [ ] Campos de filtro não contêm prosa livre.
- [ ] Links em YAML usam formato consistente.
- [ ] Não há propriedades sinônimas.
- [ ] Compatibilidade com Properties/Bases/Dataview foi considerada.

**Gate:** schemas parseiam e são consultáveis em arquivos de teste.

## 7. Gate 5 — Inventário e cobertura

- [ ] Existe inventário antes da produção em massa.
- [ ] Cada item tem basename, título, tipo e pasta.
- [ ] Cada item tem prioridade e profundidade esperada.
- [ ] Cada item tem fontes ou estratégia de pesquisa.
- [ ] Cada item tem links candidatos justificados.
- [ ] Itens obrigatórios e opcionais estão separados.
- [ ] Duplicatas semânticas foram removidas.
- [ ] O inventário cabe no orçamento de qualidade disponível.
- [ ] O núcleo pode ser entregue sem depender de toda a periferia.
- [ ] O inventário contém MOCs, templates, auditorias e documentação.

**Gate:** nenhum arquivo é criado em escala sem estar no inventário ou em mudança registrada.

## 8. Gate 6 — Arquitetura física

- [ ] A raiz contém um ponto de entrada óbvio.
- [ ] Pastas refletem responsabilidade ou tipo, não apenas gosto visual.
- [ ] A profundidade de pastas é moderada.
- [ ] Templates estão separados do conteúdo.
- [ ] Anexos brutos e contexto de produção não poluem a raiz final.
- [ ] Auditorias e pendências estão visíveis.
- [ ] Configurações `.obsidian` são intencionais.
- [ ] Plugins comunitários são declarados.
- [ ] Caminhos foram congelados antes de consultas e Canvas.
- [ ] Não há versões antigas misturadas ao release.

**Gate:** árvore de pastas e exemplos de caminhos aprovados.

## 9. Gate 7 — Templates

- [ ] Existe template por tipo recorrente.
- [ ] O template contém YAML válido.
- [ ] O template explica o propósito da nota.
- [ ] Há perguntas-guia específicas.
- [ ] Há critérios de conclusão.
- [ ] Há campos de fontes e limites.
- [ ] Há checklist interno quando útil.
- [ ] O template não força seções irrelevantes.
- [ ] O template não produz texto genérico automaticamente.
- [ ] Foi testado com uma nota fácil, uma difícil e uma controversa.

**Gate:** templates ajudam a pensar sem homogeneizar o argumento.

## 10. Gate 8 — Produção de conteúdo

### Ordem

- [ ] Ponto de entrada e metodologia foram escritos.
- [ ] Fontes e notas núcleo foram escritas antes da periferia.
- [ ] Relações centrais foram documentadas.
- [ ] MOCs iniciais foram atualizados conforme o conteúdo nasceu.
- [ ] Periferia só foi produzida após estabilização do núcleo.

### Qualidade por nota

- [ ] A nota responde a uma pergunta específica.
- [ ] A abertura contém uma síntese útil.
- [ ] O texto não poderia ser aplicado a qualquer entidade apenas trocando o nome.
- [ ] Afirmações fortes têm fonte.
- [ ] Limites e incertezas estão visíveis.
- [ ] Exemplos são concretos.
- [ ] Links têm motivo semântico.
- [ ] A extensão corresponde à dificuldade e centralidade.
- [ ] Não há placeholder oculto.
- [ ] A nota possui próxima ação quando incompleta.

**Gate:** amostra estratificada aprovada antes da produção em massa.

## 11. Gate 9 — Links internos

### Validade

- [ ] Todo destino existe ou é pendência declarada.
- [ ] Links para cabeçalhos apontam a cabeçalhos reais.
- [ ] Links para blocos apontam a block IDs reais.
- [ ] Embeds apontam a arquivos existentes.
- [ ] Renomeações atualizaram destinos.

### Semântica

- [ ] Cada link importante responde “qual é a relação?”.
- [ ] Influência não foi inferida por mera semelhança.
- [ ] Contexto, exemplo, crítica e causalidade não foram confundidos.
- [ ] Relações controversas têm nota própria.
- [ ] Links recíprocos são usados apenas quando semanticamente adequados.
- [ ] Notas núcleo possuem entradas e saídas suficientes.
- [ ] Não há linkagem automática por todas as ocorrências de uma palavra.

### Densidade

- [ ] Isolamento foi medido por tipo.
- [ ] Hubs acidentais foram identificados.
- [ ] Links administrativos foram excluídos do grafo quando necessário.
- [ ] A densidade não foi inflada para melhorar aparência.

**Gate:** nenhum link quebrado no núcleo e relações críticas auditadas.

## 12. Gate 10 — MOCs, trilhas e navegação

- [ ] Existe MOC geral.
- [ ] MOCs temáticos existem onde há decisão de percurso.
- [ ] MOCs explicam os links, não apenas listam.
- [ ] Listagens automáticas estão separadas de curadoria.
- [ ] Há trilha para iniciante quando o domínio é complexo.
- [ ] Há trilha avançada ou por problema quando necessário.
- [ ] O usuário encontra o primeiro passo em menos de um minuto.
- [ ] MOCs não duplicam a árvore de pastas sem agregar sentido.
- [ ] Backlinks e grafo local foram considerados como navegação complementar.

**Gate:** teste de navegação com três tarefas típicas concluído.

## 13. Gate 11 — Bases, Dataview e automações

- [ ] Cada vista tem finalidade declarada.
- [ ] A fonte de dados está delimitada.
- [ ] Templates e infraestrutura estão excluídos quando necessário.
- [ ] Categorias ordinais não são ordenadas alfabeticamente.
- [ ] Campos usados no filtro são controlados.
- [ ] Há caso que deve aparecer e caso que não deve aparecer.
- [ ] A vista foi testada com campos ausentes.
- [ ] Recursos comunitários estão documentados.
- [ ] Funcionalidade essencial possui alternativa nativa.
- [ ] DataviewJS é usado apenas onde DQL/Bases não bastam.
- [ ] Scripts não escrevem dados sem política explícita.

**Gate:** consultas principais executam sem erro em release extraído.

## 14. Gate 12 — Graph View e Canvas

### Graph View

- [ ] Grupos usam filtros estáveis.
- [ ] Cores têm legenda e função.
- [ ] Arquivos administrativos foram excluídos quando poluem.
- [ ] Tags não criam hubs artificiais sem propósito.
- [ ] Grafo global e local têm funções distintas.
- [ ] Centralidade não é apresentada como prova.
- [ ] Hubs anômalos foram revisados.

### Canvas

- [ ] JSON é válido.
- [ ] IDs de nós e arestas são únicos.
- [ ] Todo nó de arquivo aponta a caminho real.
- [ ] Todo subpath existe.
- [ ] Toda aresta aponta a nós existentes.
- [ ] A direção da seta corresponde ao significado.
- [ ] Rótulos ou legenda explicam tipos de relação.
- [ ] O Canvas não é a única documentação da ligação.
- [ ] Canvas foi aberto visualmente no Obsidian quando possível.

**Gate:** validação estrutural e inspeção visual aprovadas.

## 15. Auditoria técnica

### Arquivos

- [ ] Contagem por extensão registrada.
- [ ] Arquivos vazios detectados.
- [ ] Arquivos gigantes inesperados detectados.
- [ ] Basenames duplicados detectados.
- [ ] Caracteres problemáticos detectados.
- [ ] Codificação UTF-8 confirmada.
- [ ] Nomes reservados do sistema operacional evitados.
- [ ] Symlinks e arquivos ocultos inesperados detectados.

### YAML

- [ ] 100% dos arquivos aplicáveis parseiam.
- [ ] Campos obrigatórios presentes.
- [ ] Tipos de dados coerentes.
- [ ] Vocabulários controlados respeitados.
- [ ] IDs únicos.
- [ ] Links em propriedades resolvem.
- [ ] Datas são válidas.

### Links

- [ ] Wikilinks resolvem.
- [ ] Markdown links internos resolvem.
- [ ] Cabeçalhos e blocos resolvem.
- [ ] Embeds resolvem.
- [ ] Canvas resolve.
- [ ] Ambiguidades de basename foram eliminadas.
- [ ] Links externos críticos respondem ou têm data de acesso.

### Configuração

- [ ] JSON de `.obsidian` é válido.
- [ ] Plugins comunitários necessários estão listados.
- [ ] Nenhum segredo, token ou dado pessoal foi empacotado.
- [ ] Configuração não contém caminhos absolutos locais.
- [ ] Preferências que afetam links foram registradas.

**Gate:** zero falha crítica ou alta não assumida.

## 16. Auditoria semântica e conceitual

- [ ] Tipos de nota foram aplicados corretamente.
- [ ] Relações seguem o vocabulário.
- [ ] Direções estão corretas.
- [ ] Relações fortes têm evidência.
- [ ] Hipóteses estão marcadas.
- [ ] Posições divergentes são representadas.
- [ ] Ausência de evidência não virou evidência de ausência sem justificativa.
- [ ] Termos homônimos foram desambiguados.
- [ ] Conceitos não foram tratados como idênticos entre contextos diferentes.
- [ ] Eventos e causas não foram confundidos.
- [ ] Correlação e causalidade não foram confundidas.
- [ ] A visualização não é usada como argumento.

**Gate:** revisão de todas as relações de alta centralidade ou alto risco.

## 17. Auditoria bibliográfica

- [ ] Cada nota central tem fontes adequadas.
- [ ] Referências permitem relocalização.
- [ ] Edições e páginas aparecem quando necessárias.
- [ ] Fonte primária e secundária estão distinguidas.
- [ ] Fontes comunitárias não sustentam afirmações de alta autoridade.
- [ ] Datas de acesso existem para páginas voláteis.
- [ ] Fontes conflitantes são apresentadas honestamente.
- [ ] Referências não foram inventadas.
- [ ] Links externos não substituem referência bibliográfica mínima.
- [ ] Há registro de fontes consultadas e não utilizadas quando relevante.

**Gate:** amostra de referências verificada diretamente.

## 18. Auditoria editorial e de densidade

- [ ] Notas núcleo têm profundidade suficiente.
- [ ] Notas periféricas não são artificialmente infladas.
- [ ] Distribuição de palavras por tipo foi medida.
- [ ] Outliers curtos e longos foram revisados.
- [ ] Similaridade entre notas foi medida ou amostrada.
- [ ] Boilerplate sem informação foi removido.
- [ ] Títulos e resumos são específicos.
- [ ] Repetições entre YAML e corpo foram reduzidas.
- [ ] Linguagem está consistente.
- [ ] Abreviações e termos técnicos estão definidos.

**Gate:** nenhuma família importante de notas é apenas template preenchido.

## 19. Auditoria de grafo

- [ ] Quantidade de nós e arestas registrada.
- [ ] Notas sem entrada registradas por tipo.
- [ ] Notas sem saída registradas por tipo.
- [ ] Notas totalmente isoladas registradas por tipo.
- [ ] Hubs principais revisados.
- [ ] Clusters esperados aparecem.
- [ ] Clusters espúrios foram explicados.
- [ ] Nós administrativos estão filtrados.
- [ ] MOCs não dominam o grafo apenas por listas automáticas.
- [ ] Arestas não foram multiplicadas sem significado.

**Gate:** todas as notas núcleo estão integradas ou justificadamente isoladas.

## 20. Auditoria de migração e versionamento

- [ ] Versão da pasta raiz está correta.
- [ ] README, changelog e metadados concordam.
- [ ] Não há referências proibidas a versões antigas.
- [ ] Caminhos antigos não permanecem em consultas.
- [ ] Canvas não aponta a nomes antigos.
- [ ] Tags históricas foram migradas ou removidas.
- [ ] Arquivos removidos estão registrados.
- [ ] Mudanças incompatíveis de schema estão no changelog.
- [ ] Migração foi testada sobre uma cópia.
- [ ] Conteúdo reaproveitado foi revisado, não copiado cegamente.

**Gate:** busca global por identificadores antigos retorna apenas changelog/histórico autorizado.

## 21. Auditoria de privacidade e segurança

- [ ] Nenhuma chave de API foi incluída.
- [ ] Nenhuma senha, cookie ou token foi incluído.
- [ ] Dados pessoais foram minimizados.
- [ ] Transcrições brutas têm autorização e necessidade.
- [ ] Caminhos locais não expõem nome de usuário ou estrutura privada.
- [ ] Metadados de arquivos foram revisados.
- [ ] Plugins e scripts são de origem conhecida.
- [ ] JavaScript não executa ações ocultas.
- [ ] Conteúdo remoto incorporado foi documentado.
- [ ] Licenças e direitos de redistribuição foram respeitados.

**Gate:** zero segredo ou dado indevido no pacote.

## 22. Gate de compactação

### Antes do ZIP

- [ ] Pasta de trabalho está limpa.
- [ ] Temporários, caches e relatórios internos indesejados foram removidos.
- [ ] Tamanho total é plausível.
- [ ] Nomes foram testados em UTF-8.
- [ ] O arquivo de entrada correto está sendo compactado.
- [ ] A raiz do ZIP terá exatamente um diretório principal, quando essa for a convenção.

### Depois do ZIP

- [ ] ZIP foi extraído em novo diretório.
- [ ] Nomes pré e pós-ZIP foram comparados.
- [ ] Quantidade e hashes foram comparados.
- [ ] YAML foi revalidado na cópia extraída.
- [ ] Links foram revalidados na cópia extraída.
- [ ] Canvas foi revalidado na cópia extraída.
- [ ] Consultas foram testadas na cópia extraída.
- [ ] O vault foi aberto no Obsidian quando possível.
- [ ] O ZIP recebeu checksum.
- [ ] O relatório final usa métricas da cópia extraída.

**Gate:** o artefato entregue, e não apenas a pasta de origem, foi aprovado.

## 23. Checklist de entrega

- [ ] ZIP do vault.
- [ ] README de abertura e instalação.
- [ ] Guia de navegação inicial.
- [ ] Lista de plugins nativos e comunitários.
- [ ] Instruções de instalação das dependências.
- [ ] Schema e ontologia.
- [ ] Changelog.
- [ ] Relatório de auditoria.
- [ ] Métricas verificadas.
- [ ] Pendências assumidas.
- [ ] Limitações conhecidas.
- [ ] Checksum do ZIP.
- [ ] Data e versão do release.
- [ ] Política de atualização.
- [ ] Licença ou termos de uso quando aplicável.

## 24. Testes de aceitação orientados a tarefas

Uma pessoa que não participou da construção deve conseguir:

1. abrir o cofre;
2. localizar o MOC geral;
3. entender os tipos de nota;
4. encontrar uma entidade pelo alias;
5. seguir uma relação até sua evidência;
6. localizar controvérsia e posições divergentes;
7. usar ao menos uma vista Base ou consulta;
8. abrir um Canvas e compreender sua legenda;
9. criar uma nova nota a partir de template;
10. saber onde registrar uma pendência.

Registre tempo, erros e dúvidas. Usabilidade não pode ser inferida apenas pela estrutura.

## 25. Definition of Done resumida

- [ ] Escopo cumprido.
- [ ] Ontologia estável.
- [ ] Conteúdo núcleo específico e fundamentado.
- [ ] Links semanticamente justificáveis.
- [ ] MOCs ensinam percursos.
- [ ] Metadados são consultáveis.
- [ ] Consultas funcionam.
- [ ] Graph/Canvas não fazem alegações silenciosas.
- [ ] Auditorias foram executadas.
- [ ] Falhas críticas e altas foram resolvidas.
- [ ] ZIP extraído foi revalidado.
- [ ] Estado real está documentado sem autoelogio.
