---
titulo: "Biblioteca de Bases, Dataview e consultas"
tipo: anexo_operacional
versao: "1.0"
data: 2026-06-17
---

# Biblioteca de Bases, Dataview e consultas

## 1. Regra de escolha

### Use Bases quando

- a vista precisa ser nativa e editável;
- o usuário quer tabela, lista, cartões ou mapa sobre propriedades;
- filtros, ordenação e fórmulas simples resolvem o problema;
- o cofre deve degradar bem sem plugins comunitários;
- a equipe editará metadados diretamente na vista.

### Use Dataview quando

- o resultado é uma consulta ou relatório calculado;
- é necessário agregar, agrupar ou derivar dados;
- o usuário aceita uma dependência comunitária;
- o resultado pode ser somente leitura;
- a consulta precisa combinar propriedades e metadados implícitos de arquivos.

### Use DataviewJS quando

- DQL não consegue expressar o relatório;
- é necessário tratamento programático, hierarquia, validação ou renderização customizada;
- existe alguém capaz de manter JavaScript;
- o ganho compensa o aumento de risco e complexidade.

### Use busca nativa quando

- a pergunta é pontual;
- não há necessidade de salvar uma visão estruturada;
- a consulta pode ser expressa por caminho, tag, propriedade ou texto.

### Use MOC manual quando

- a ordem e a explicação importam;
- o mapa deve ensinar um percurso;
- cada link precisa de anotação editorial;
- a curadoria humana é o valor central.

## 2. Contrato de uma consulta

Toda consulta deve declarar:

```markdown
## Finalidade

## Fonte de dados

## Inclusões

## Exclusões

## Campos necessários

## Resultado esperado

## Teste conhecido

## Limitações
```

Não crie consultas antes de existirem dados reais suficientes para testá-las.

## 3. Regras de segurança de Dataview

1. Não consultar `FROM ""` sem exclusões explícitas.
2. Não ordenar categorias textuais como se fossem escala ordinal.
3. Não depender de texto livre para filtros críticos.
4. Não incluir templates, auditorias e infraestrutura por acidente.
5. Não presumir que `null`, campo ausente e lista vazia são equivalentes em todos os casos.
6. Não usar Dataview para editar o conteúdo-fonte.
7. Declarar que o plugin é dependência comunitária.
8. Manter uma alternativa nativa quando a consulta for essencial à navegação.
9. Testar em um cofre recém-extraído.
10. Comentar consultas complexas.

## 4. Estrutura recomendada de pastas

```text
11-Consultas/
├── README-Consultas.md
├── Autores/
├── Conceitos/
├── Relacoes/
├── Bibliografia/
├── Auditorias/
└── Operacao/
```

Ou manter consultas embutidas nos MOCs quando servirem diretamente àquele mapa. Evite uma pasta de dezenas de consultas sem contexto.

## 5. Consultas DQL reutilizáveis

### 5.1. Notas por tipo e status

```dataview
TABLE WITHOUT ID
  file.link AS "Nota",
  status AS "Status",
  ultima_revisao AS "Última revisão"
FROM "01-Conteudo"
WHERE tipo = "conceito"
SORT ultima_revisao DESC
```

### 5.2. Notas sem campo obrigatório

```dataview
TABLE WITHOUT ID
  file.link AS "Nota",
  tipo AS "Tipo",
  status AS "Status"
FROM "01-Conteudo"
WHERE tipo AND (!id OR !titulo OR !versao_schema)
SORT tipo ASC, file.name ASC
```

### 5.3. Notas sem fontes

```dataview
TABLE WITHOUT ID
  file.link AS "Nota",
  tipo AS "Tipo",
  grau_confianca AS "Confiança"
FROM "01-Conteudo"
WHERE contains(list("entidade", "conceito", "obra", "relacao", "controversia"), tipo)
  AND length(default(fontes_primarias, [])) = 0
  AND length(default(fontes_secundarias, [])) = 0
SORT tipo ASC, file.name ASC
```

### 5.4. Relações de risco alto

```dataview
TABLE WITHOUT ID
  file.link AS "Relação",
  sujeito AS "Sujeito",
  objeto AS "Objeto",
  tipo_relacao AS "Tipo",
  grau_confianca AS "Confiança"
FROM "06-Relacoes"
WHERE tipo = "relacao" AND risco_interpretativo = "alto"
SORT grau_confianca ASC, file.name ASC
```

### 5.5. Relações sem evidência suficiente

Adote campos booleanos ou listas controladas:

```yaml
evidencia_historica_presente: true
evidencia_conceitual_presente: true
```

```dataview
TABLE WITHOUT ID
  file.link AS "Relação",
  tipo_relacao AS "Tipo",
  grau_confianca AS "Confiança",
  evidencia_historica_presente AS "Histórica",
  evidencia_conceitual_presente AS "Conceitual"
FROM "06-Relacoes"
WHERE tipo = "relacao"
  AND grau_confianca != "baixo"
  AND (!evidencia_historica_presente AND !evidencia_conceitual_presente)
SORT file.name ASC
```

### 5.6. Pendências abertas por prioridade

```dataview
TABLE WITHOUT ID
  file.link AS "Pendência",
  prioridade AS "Prioridade",
  origem AS "Origem",
  responsavel AS "Responsável",
  prazo AS "Prazo"
FROM "99-Pendencias"
WHERE tipo = "pendencia" AND status != "concluida"
SORT prioridade ASC, prazo ASC
```

### 5.7. Notas vencidas para revisão

```dataview
TABLE WITHOUT ID
  file.link AS "Nota",
  proxima_revisao AS "Revisar em",
  responsavel AS "Responsável"
FROM "01-Conteudo"
WHERE proxima_revisao AND proxima_revisao <= date(today)
SORT proxima_revisao ASC
```

### 5.8. Conceitos por autor ou entidade

```dataview
TABLE WITHOUT ID
  file.link AS "Conceito",
  autores_associados AS "Autores",
  grau_confianca AS "Confiança"
FROM "04-Conceitos"
WHERE tipo = "conceito" AND contains(autores_associados, [[Michel Foucault]])
SORT file.name ASC
```

### 5.9. Obras sem edição consultada

```dataview
TABLE WITHOUT ID
  file.link AS "Obra",
  autores AS "Autores",
  ano_original AS "Ano"
FROM "05-Obras"
WHERE tipo = "obra" AND !edicao_consultada
SORT autores ASC, ano_original ASC
```

### 5.10. Controvérsias por participante

```dataview
TABLE WITHOUT ID
  file.link AS "Controvérsia",
  participantes AS "Participantes",
  risco_interpretativo AS "Risco"
FROM "07-Controversias"
WHERE tipo = "controversia" AND contains(participantes, [[Michel Foucault]])
SORT risco_interpretativo DESC
```

### 5.11. Notas com aliases duplicáveis

Dataview DQL não é a melhor ferramenta para detectar aliases globalmente duplicados. Use DataviewJS ou auditoria externa. Ainda assim, é possível listar:

```dataview
TABLE WITHOUT ID
  file.link AS "Nota",
  aliases AS "Aliases"
FROM ""
WHERE length(default(aliases, [])) > 0
SORT file.name ASC
```

### 5.12. Estatística por tipo

```dataview
TABLE WITHOUT ID
  tipo AS "Tipo",
  length(rows) AS "Quantidade"
FROM "01-Conteudo"
WHERE tipo
GROUP BY tipo
SORT length(rows) DESC
```

### 5.13. MOCs e trilhas sem descrição de propósito

Adote campo `proposito`:

```dataview
TABLE WITHOUT ID
  file.link AS "Mapa",
  tipo AS "Tipo"
FROM ""
WHERE contains(list("moc", "trilha"), tipo) AND !proposito
SORT tipo ASC, file.name ASC
```

### 5.14. Notas com status incompatível

```dataview
TABLE WITHOUT ID
  file.link AS "Nota",
  status AS "Status"
FROM ""
WHERE status AND !contains(
  list("rascunho", "em_pesquisa", "em_revisao", "revisado", "auditado", "arquivado"),
  status
)
SORT status ASC
```

### 5.15. Isolamento aproximado

Dataview consegue acessar `file.inlinks` e `file.outlinks`:

```dataview
TABLE WITHOUT ID
  file.link AS "Nota",
  length(file.inlinks) AS "Entradas",
  length(file.outlinks) AS "Saídas",
  tipo AS "Tipo"
FROM "01-Conteudo"
WHERE length(file.inlinks) = 0 OR length(file.outlinks) = 0
SORT length(file.inlinks) ASC, length(file.outlinks) ASC
```

Observação: links presentes apenas em Canvas não aparecem necessariamente como wikilinks Markdown. A auditoria final deve combinar formatos.

## 6. Ordenação semântica de escalas

Não faça:

```dataview
SORT grau_confianca DESC
```

Texto será ordenado alfabeticamente. Crie campo numérico derivado ou use `choice`:

```dataview
TABLE WITHOUT ID
  file.link AS "Nota",
  grau_confianca AS "Confiança",
  choice(grau_confianca = "alto", 5,
    choice(grau_confianca = "medio_alto", 4,
      choice(grau_confianca = "medio", 3,
        choice(grau_confianca = "medio_baixo", 2,
          choice(grau_confianca = "baixo", 1, 0))))) AS ordem
FROM "06-Relacoes"
WHERE tipo = "relacao"
SORT ordem DESC
```

Ou armazene explicitamente:

```yaml
grau_confianca: medio_alto
grau_confianca_ordem: 4
```

## 7. Exemplos de DataviewJS

### 7.1. Detectar IDs duplicados

```dataviewjs
const pages = dv.pages('""').where(p => p.id);
const groups = new Map();

for (const page of pages) {
  const id = String(page.id);
  if (!groups.has(id)) groups.set(id, []);
  groups.get(id).push(page.file.link);
}

const duplicates = [...groups.entries()]
  .filter(([, files]) => files.length > 1)
  .map(([id, files]) => [id, files]);

dv.table(["ID duplicado", "Arquivos"], duplicates);
```

### 7.2. Detectar aliases usados por múltiplas notas

```dataviewjs
const aliases = new Map();

for (const page of dv.pages('""')) {
  const values = Array.isArray(page.aliases)
    ? page.aliases
    : page.aliases ? [page.aliases] : [];

  for (const alias of values) {
    const key = String(alias).trim().toLowerCase();
    if (!key) continue;
    if (!aliases.has(key)) aliases.set(key, []);
    aliases.get(key).push(page.file.link);
  }
}

const conflicts = [...aliases.entries()]
  .filter(([, files]) => files.length > 1)
  .sort((a, b) => a[0].localeCompare(b[0]));

dv.table(["Alias", "Notas"], conflicts);
```

### 7.3. Relatório de completude por tipo

```dataviewjs
const requirements = {
  entidade: ["id", "titulo", "status"],
  conceito: ["id", "titulo", "status", "grau_confianca"],
  obra: ["id", "titulo", "autores"],
  relacao: ["id", "sujeito", "objeto", "tipo_relacao", "grau_confianca"],
  controversia: ["id", "participantes"]
};

const rows = [];
for (const page of dv.pages('"01-Conteudo"')) {
  const required = requirements[page.tipo] ?? [];
  const missing = required.filter(field => page[field] === undefined || page[field] === null || page[field] === "");
  if (missing.length > 0) rows.push([page.file.link, page.tipo, missing.join(", ")]);
}

dv.table(["Nota", "Tipo", "Campos ausentes"], rows);
```

### 7.4. Dashboard simples de release

```dataviewjs
const pages = dv.pages('""');
const content = pages.where(p => p.tipo && !["template", "auditoria", "infraestrutura"].includes(p.tipo));
const brokenEditorial = content.where(p => !p.id || !p.status || !p.versao_schema);
const risky = content.where(p => p.risco_interpretativo === "alto");
const drafts = content.where(p => p.status === "rascunho");

const rows = [
  ["Notas de conteúdo", content.length],
  ["Com campos obrigatórios ausentes", brokenEditorial.length],
  ["Risco interpretativo alto", risky.length],
  ["Rascunhos", drafts.length]
];

dv.table(["Indicador", "Valor"], rows);
```

## 8. Bases — projetos de vistas nativas

Bases são mais adequadas para vistas editáveis e para usuários que não desejam depender de Dataview. A sintaxe concreta do arquivo `.base` pode evoluir; crie e teste as vistas pela interface da versão instalada do Obsidian e documente a configuração lógica abaixo.

### 8.1. Base — Catálogo de notas

**Fonte:** todas as notas de conteúdo.

**Filtros:**

- `tipo` existe;
- excluir `template`, `auditoria`, `infraestrutura`;
- excluir pasta `.obsidian` e anexos técnicos.

**Colunas:**

- arquivo;
- título;
- tipo;
- status;
- profundidade;
- última revisão;
- responsável.

**Vistas:**

- tabela por tipo;
- cartões por status;
- lista de revisão recente.

### 8.2. Base — Relações

**Filtros:** `tipo = relacao`.

**Colunas:**

- sujeito;
- tipo de relação;
- objeto;
- confiança;
- risco;
- status;
- fontes.

**Vistas:**

- alto risco;
- alta confiança;
- sem fonte;
- por tipo de relação.

### 8.3. Base — Pipeline editorial

**Filtros:** notas de conteúdo não arquivadas.

**Agrupar por:** `status`.

**Colunas:**

- arquivo;
- responsável;
- prioridade;
- última revisão;
- pendências.

### 8.4. Base — Fontes e evidências

**Filtros:** `tipo = fonte`.

**Colunas:**

- subtipo;
- nível de autoridade;
- autor/organização;
- data;
- data de acesso;
- notas sustentadas;
- URL.

### 8.5. Base — Calendário de manutenção

**Filtros:** `proxima_revisao` existe.

**Vistas:** tabela ordenada por data e calendário, quando disponível.

## 9. MOC + Base ou Dataview

Uma solução robusta combina curadoria e dinamismo:

```markdown
# MOC — Relações centrais

## Como ler este mapa

Este MOC apresenta as relações necessárias para compreender a pergunta central. A tabela automática ao final serve para cobertura, não para substituir a explicação.

## Relações estruturantes

1. [[Relação — A transforma B]] — estabelece o vocabulário do problema.
2. [[Relação — C critica A]] — introduz a principal objeção.
3. [[Controvérsia — A versus C]] — mostra os limites da síntese.

## Todas as relações cadastradas

```dataview
TABLE WITHOUT ID file.link AS "Relação", tipo_relacao, grau_confianca
FROM "06-Relacoes"
WHERE tipo = "relacao"
SORT file.name ASC
```
```

## 10. Consultas que invalidam um release

Considere bloqueantes:

- IDs duplicados;
- notas de conteúdo sem `tipo`;
- relações sem sujeito ou objeto;
- status fora do vocabulário;
- referências a versões antigas proibidas;
- notas obrigatórias ausentes;
- fontes primárias inexistentes para relações declaradas como documentadas;
- consultas com erro de execução;
- Canvas apontando para arquivos inexistentes;
- notas núcleo completamente isoladas.

## 11. Teste de consultas

Para cada consulta:

1. preparar um caso que deve aparecer;
2. preparar um caso que não deve aparecer;
3. executar após extração limpa;
4. alterar uma propriedade e confirmar atualização;
5. testar campos ausentes e listas vazias;
6. confirmar que templates e infraestrutura estão excluídos;
7. registrar captura ou resultado no relatório de auditoria.

## 12. Checklist de seleção de ferramenta

- [ ] Preciso editar dados na própria vista? Use Bases.
- [ ] Preciso de agrupamento ou cálculo somente leitura? Considere Dataview.
- [ ] Preciso de algoritmo customizado? DataviewJS ou script externo.
- [ ] Preciso ensinar um percurso? MOC manual.
- [ ] Preciso apenas encontrar algo agora? Busca nativa.
- [ ] O recurso é essencial? Existe alternativa sem plugin.
- [ ] A dependência foi declarada no README.
- [ ] A vista foi testada no release extraído.
