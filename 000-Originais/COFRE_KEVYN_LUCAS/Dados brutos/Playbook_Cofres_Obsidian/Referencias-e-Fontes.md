---
titulo: "Referências e fontes"
tipo: bibliografia
versao: "1.0"
data: 2026-06-17
---

# Referências e fontes

## 1. Materiais do estudo de caso

- `Cofre filosofia.zip` — artefato final auditado: Markdown, YAML, wikilinks, Canvas, consultas, configurações e empacotamento.
- `Contexto cofre filosofia.pdf` — exportação das conversas de construção, crítica, comparação de versões, prompts, tentativas e correções.

## 2. Documentação oficial do Obsidian

### Links internos

- Obsidian Help. **Internal links**. <https://help.obsidian.md/links>
- Usado para: Wikilinks, links Markdown, links para cabeçalhos, block links, display text e atualização de links.

### Embeds

- Obsidian Help. **Embed files**. <https://help.obsidian.md/embeds>
- Usado para: transclusão de notas, imagens, PDFs, áudio e seções.

### Properties

- Obsidian Help. **Properties**. <https://help.obsidian.md/properties>
- Usado para: tipos de propriedade, YAML, consistência global de tipos, limitações da interface e propriedades em links.

### Aliases

- Obsidian Help. **Aliases**. <https://help.obsidian.md/aliases>
- Usado para: nomes alternativos e lista `aliases`.

### Tags

- Obsidian Help. **Tags**. <https://help.obsidian.md/tags>
- Usado para: tags em propriedades, tags aninhadas e regras de nomenclatura.

### Backlinks

- Obsidian Help. **Backlinks**. <https://help.obsidian.md/plugins/backlinks>
- Usado para: referências ligadas e menções não ligadas.

### Graph View

- Obsidian Help. **Graph view**. <https://help.obsidian.md/plugins/graph>
- Usado para: nós, arestas, filtros, grupos, forças e grafo local.

### Templates

- Obsidian Help. **Templates**. <https://help.obsidian.md/plugins/templates>
- Usado para: plugin nativo, pasta de templates e variáveis básicas.

### Canvas

- Obsidian Help. **Canvas**. <https://help.obsidian.md/plugins/canvas>
- Usado para: organização visual de notas, mídias e páginas web.

### Bases

- Obsidian Help. **Bases**. <https://help.obsidian.md/bases>
- Usado para: vistas nativas semelhantes a bancos de dados sobre propriedades Markdown, filtros, fórmulas e edição.

### Core plugins

- Obsidian Help. **Core plugins**. <https://help.obsidian.md/plugins>
- Usado para: distinção entre recursos nativos e plugins comunitários.

### Command line interface

- Obsidian Help. **Obsidian CLI**. <https://help.obsidian.md/cli>
- Usado para: automação e testes em ambientes compatíveis com versões atuais do aplicativo.

## 3. Dataview

- Dataview Documentation. **Overview**. <https://blacksmithgu.github.io/obsidian-dataview/>
- Dataview Documentation. **Adding metadata**. <https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/>
- Dataview Documentation. **Data Query Language**. <https://blacksmithgu.github.io/obsidian-dataview/queries/structure/>
- Dataview Documentation. **Dataview JavaScript API**. <https://blacksmithgu.github.io/obsidian-dataview/api/intro/>
- Repositório oficial do plugin: <https://github.com/blacksmithgu/obsidian-dataview>

Uso no playbook:

- Dataview é tratado como índice e mecanismo de consulta sobre metadados;
- não como editor principal dos dados;
- DataviewJS é reservado a necessidades programáticas;
- consultas essenciais devem possuir documentação e alternativa quando possível.

## 4. Templater

- Templater Documentation. <https://silentvoid13.github.io/Templater/>
- Repositório oficial. <https://github.com/SilentVoid13/Templater>

Uso no playbook:

- plugin comunitário opcional para templates dinâmicos, funções, variáveis e JavaScript;
- não é requisito universal;
- Templates nativo deve ser suficiente para casos básicos.

## 5. JSON Canvas

- JSON Canvas. **Open file format for infinite canvas data**. <https://jsoncanvas.org/>
- Especificação e repositório: <https://github.com/obsidianmd/jsoncanvas>

Uso no playbook:

- validação de estrutura `nodes` e `edges`;
- tipos de nó;
- referências a arquivos e subpaths;
- direção, rótulo e cor de arestas.

## 6. Mapas de Conteúdo e notas atômicas

Estas fontes representam métodos de organização, não regras oficiais do Obsidian.

- Linking Your Thinking. **Maps of Content**. <https://www.linkingyourthinking.com/>
- Obsidian Forum. Discussões e exemplos de MOCs. <https://forum.obsidian.md/>
- Andy Matuschak. **Evergreen notes should be atomic**. <https://notes.andymatuschak.org/Evergreen_notes_should_be_atomic>
- Andy Matuschak. **Evergreen notes**. <https://notes.andymatuschak.org/Evergreen_notes>

Uso crítico no playbook:

- “atômica” significa focada em uma ideia ou função reutilizável, não obrigatoriamente curta;
- MOC é curadoria de percurso, não mera listagem automática;
- essas práticas devem ser adaptadas ao domínio e ao usuário.

## 7. Padrões técnicos complementares

- YAML 1.2 Specification. <https://yaml.org/spec/1.2.2/>
- CommonMark Specification. <https://spec.commonmark.org/>
- ISO 8601 — representação de datas e horas. <https://www.iso.org/iso-8601-date-and-time-format.html>

## 8. Critérios de uso das fontes

1. Documentação oficial governa comportamento do aplicativo e formatos.
2. Documentação do plugin governa sintaxe e limites do plugin.
3. Métodos de PKM são recomendações, não obrigações técnicas.
4. Fóruns e comunidades servem para descobrir problemas e padrões de uso, não para substituir documentação.
5. Recursos podem mudar; registre a data de acesso e teste na versão instalada.

## 9. Data de corte desta pesquisa

Pesquisa e verificação técnica realizadas em **17 de junho de 2026**. Recursos atuais, especialmente Bases, CLI, propriedades e plugins, devem ser revalidados em projetos futuros.
