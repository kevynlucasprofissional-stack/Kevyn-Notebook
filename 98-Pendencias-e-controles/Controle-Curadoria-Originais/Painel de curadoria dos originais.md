---
id: painel-curadoria-originais
titulo: Painel de curadoria dos originais
tipo: consulta
status: ativo
profundidade: indice
versao_schema: "1.0"
versao_conteudo: "1.0"
idioma: pt-BR
data_criacao: 2026-09-28
ultima_revisao: 2026-09-28
tags:
  - curadoria/fontes
  - consulta
---

# Painel de curadoria dos originais

Fonte: `Controle-Curadoria-Originais.csv`.

> [!info]
> O CSV é a fonte de verdade. Este painel é apenas uma visualização dinâmica.
> Se DataviewJS não estiver disponível, filtre o CSV diretamente.

```dataviewjs
const path = "98-Pendencias-e-controles/Controle-Curadoria-Originais/Controle-Curadoria-Originais.csv";
const data = Array.from(await dv.io.csv(path));

const txt = v => String(v ?? "").trim();
const score = r => {
  const s = txt(r.relevancia);
  if (s === "") return null;
  const n = Number(s);
  return Number.isFinite(n) ? n : null;
};
const used = r => txt(r.utilizado_na_canonica).toLowerCase();
const analyzed = r => txt(r.analisado).toLowerCase();

const scored = data.filter(r => score(r) !== null);
const highUnused = data
  .filter(r => score(r) !== null && score(r) >= 7 && used(r) !== "sim")
  .sort((a,b) => score(b) - score(a) || txt(a.caminho).localeCompare(txt(b.caminho)));
const unanalysed = data.filter(r => analyzed(r) === "nao");
const revisit = data.filter(r => txt(r.revisitar).toLowerCase() === "sim");
const zero = data.filter(r => score(r) === 0);
const unscored = data.filter(r => score(r) === null);

dv.header(2, "Resumo");
dv.table(
  ["Indicador", "Quantidade"],
  [
    ["Arquivos no controle", data.length],
    ["Com nota 0–10", scored.length],
    ["Sem nota 0–10", unscored.length],
    ["Não analisados", unanalysed.length],
    ["Alta relevância (7–10) ainda não totalmente utilizada", highUnused.length],
    ["Marcados para revisitar", revisit.length],
    ["Nota 0 — apenas candidatos a decisão, nunca exclusão automática", zero.length],
  ]
);

dv.header(2, "Fila prioritária — alta relevância ainda não totalmente utilizada");
dv.table(
  ["Nota", "Arquivo", "Status", "Uso canônico", "Notas canônicas"],
  highUnused.slice(0, 100).map(r => [
    score(r),
    txt(r.caminho),
    txt(r.status),
    txt(r.utilizado_na_canonica),
    txt(r.notas_canonicas),
  ])
);
if (highUnused.length > 100) dv.paragraph(`Mostrando 100 de ${highUnused.length}. Filtre o CSV para a lista completa.`);

dv.header(2, "Arquivos marcados para revisitar");
dv.table(
  ["Arquivo", "Nota", "Status", "Observações"],
  revisit.slice(0, 50).map(r => [
    txt(r.caminho),
    score(r) ?? "",
    txt(r.status),
    txt(r.observacoes),
  ])
);

dv.header(2, "Próximos não analisados");
dv.table(
  ["Arquivo", "Tipo", "Relevância legada"],
  unanalysed.slice(0, 50).map(r => [
    txt(r.caminho),
    txt(r.tipo),
    txt(r.relevancia_legada),
  ])
);

dv.header(2, "Nota 0 — revisão de retenção");
dv.paragraph("Esta seção NÃO é uma fila de exclusão. Qualquer remoção exige decisão explícita separada.");
dv.table(
  ["Arquivo", "Decisão de remoção", "Observações"],
  zero.slice(0, 50).map(r => [
    txt(r.caminho),
    txt(r.decisao_remocao),
    txt(r.observacoes),
  ])
);
```

## Fallback sem Dataview

No CSV:

- alta prioridade: `relevancia >= 7` + `utilizado_na_canonica != sim`;
- pendentes: `analisado = nao`;
- revisão: `revisitar = sim`;
- retenção: `relevancia = 0`, lembrando que isso **não autoriza exclusão**.
