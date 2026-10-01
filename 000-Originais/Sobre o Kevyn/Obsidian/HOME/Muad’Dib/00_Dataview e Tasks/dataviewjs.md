```dataviewjs
// 1. Pega os dados
let pages = dv.pages().where(p => p.resumo);

let data = pages.map(p => {
    return {
        nota: p.file.name,
        // CORREÇÃO AQUI: Adicionei .values para limpar o lixo do Dataview
        tags: p.file.tags.values, 
        resumo: p.resumo
    };
});

// 2. Transforma em JSON (note que usamos data.values aqui também para limpar a lista principal)
let jsonString = JSON.stringify(data.values, null, 2);

// 3. Cria o botão de copiar
const btn = dv.el("button", "📋 Copiar JSON Limpo");

btn.onclick = () => {
    navigator.clipboard.writeText(jsonString);
    new Notice("JSON copiado com sucesso!");
}

// Opcional: Se quiser ver na tela (cuidado se tiver muitas notas), descomente a linha abaixo:
// dv.paragraph("```json\n" + jsonString + "\n```");
```
