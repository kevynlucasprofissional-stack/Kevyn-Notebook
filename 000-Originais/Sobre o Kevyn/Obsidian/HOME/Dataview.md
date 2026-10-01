


Aqui está o código pronto para você colar no seu Obsidian. 

Ele cria apenas o botão e, quando clicado, levanta todas as notas do cofre, formata os nomes em um formato JSON e joga direto na área de transferência. Também adicionei um aviso (`Notice` nativo do Obsidian) que aparece no canto da tela confirmando a cópia e a quantidade de notas copiadas.
### ⚠️ Importante:
Para que esse código funcione, certifique-se de que a opção **Enable JavaScript Queries** (Habilitar Consultas JavaScript) esteja ativada.
Você pode verificar isso indo em:
**Configurações do Obsidian** > **Dataview** > Ativar a chavinha de **Enable JavaScript Queries**.

```dataviewjs
// Criação do botão
const btn = document.createElement('button');
btn.textContent = 'Copiar lista';

// Adiciona uma classe nativa do Obsidian para deixar o botão com estilo de ação
btn.classList.add('mod-cta');
btn.style.margin = '5px 0';

// Configura o que acontece quando o botão é clicado
btn.onclick = async () => {
    // 1. Busca todas as páginas do cofre ("" indica o cofre inteiro)
    const paginas = dv.pages('""');
    
    // 2. Extrai apenas os nomes dos arquivos e converte em um Array JavaScript padrão
    const nomes = Array.from(paginas.map(p => p.file.name));
    
    // 3. Converte o array para o formato JSON (os parâmetros 'null, 2' deixam o JSON bem formatado e legível)
    const listaJson = JSON.stringify(nomes, null, 2);
    
    // 4. Tenta copiar para a área de transferência
    try {
        await navigator.clipboard.writeText(listaJson);
        
        // Exibe o aviso verde/padrão do Obsidian de sucesso
        new Notice(`✅ Lista copiada com sucesso!\n(${nomes.length} notas exportadas em JSON)`);
    } catch (err) {
        // Exibe um erro se algo falhar
        new Notice('❌ Erro ao copiar a lista.');
        console.error('Falha na cópia:', err);
    }
};

// Insere o botão no bloco em que o código DataviewJS foi colocado
dv.container.appendChild(btn);
```