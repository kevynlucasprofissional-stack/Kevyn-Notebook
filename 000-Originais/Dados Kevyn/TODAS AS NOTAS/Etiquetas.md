#flashcards para marcar notas com flashcards
#tarefas Para unificar as tarefas.
#infomativo para notas sobre informações, use quando for **um dado útil ou factual**, sem aprofundamento pessoal.
#fugaz para notas fugazes, ideias que ainda não foram tiradas do papel, insights periódicos, etc...
#aprendizado Para notas de estudo, livros, cursos e qualquer conteúdo educativo. Use quando estiver **estudando, digerindo ou organizando conhecimento**.
#permanente para notas importantes, são aquelas com qual eu já gastei tempo, projetos aprofundados.

O objetivo de uma etiqueta é criar uma conexão entre dois galhos da árvore de conhecimento.
### 🧠 Processo Mental Ágil para Etiquetar Cartões
1. **É uma tarefa prática ou algo que devo fazer?**  
    → **Sim** → `#tarefas`  
    → **Não** → Próxima pergunta
    
2. **Estou estudando, digerindo ou organizando conhecimento?**  
    (ex: resumo de livro, curso, aula, mapa mental, insight técnico)  
    → **Sim** → `#aprendizado`  
    → **Não** → Próxima pergunta
    
3. **É um dado útil, factual, ou uma informação objetiva que pode ser reutilizada?**  
    (ex: "Adobe Premiere tem o atalho X para cortar", "o CPF é um número com 11 dígitos")  
    → **Sim** → `#informativo`  
    → **Não** → Próxima pergunta
    
4. **É uma ideia crua, insight, rascunho ou anotação passageira?**  
    (ex: brainstorm, ideia de vídeo, possível projeto futuro)  
    → **Sim** → `#fugaz`  
    → **Não** → Próxima pergunta
    
5. **É um conteúdo que já refinei, aprofundei e quero manter como base?**  
    (ex: princípios, visão de projeto, planejamento estruturado, ideias testadas)  
    → **Sim** → `#permanente`  
    → **Não** → Próxima pergunta
    
6. **É algo que quero transformar em flashcard para memorizar?**  
    (ex: fórmulas, conceitos, datas, vocabulário, etc.)  
    → **Sim** → `#flashcards`  
    → **Não** → Volte e reavalie.
    
### 💡 Dica prática:
Você pode até usar **duas etiquetas**, se elas criarem uma ponte lógica (ex: `#aprendizado` + `#flashcards` para um conceito que você está estudando e quer memorizar).
### 🔁 Rotina de Revisão de Etiquetas (manual ou semiautomática)

#### 📍 Critério: cartões com **mais de 2 etiquetas**

**Objetivo:** Reduzir excesso e manter clareza sem perder conexões úteis.

---

### 🧭 Etapas para revisão:

1. **Filtrar cartões com mais de 2 etiquetas**  
    (No Obsidian ou Notion, crie uma visualização com filtro: `count(tags) > 2` ou use uma consulta de texto avançada).
    
2. **Para cada cartão, pergunte:**
    
    - ❓ _"Cada etiqueta neste cartão representa uma forma diferente de eu encontrá-lo ou conectar esse conteúdo?"_  
        → Se **não**, remova a etiqueta menos útil.
        
    - 🔁 _"Essa etiqueta ainda representa o estágio atual do conteúdo?"_  
        → Ex: algo que era `#fugaz` pode já ter virado `#permanente`.
        
    - 🧩 _"Essas etiquetas estão ajudando ou confundindo a função do cartão?"_  
        → Se estão redundantes (ex: `#informativo` e `#aprendizado` para o mesmo dado básico), escolha a mais precisa.
        
3. **Ajuste ou reordene etiquetas conforme necessário.**  
    Você pode até criar uma convenção visual para facilitar (ex: ordem lógica → `#fugaz` → `#aprendizado` → `#permanente`).
### Código para revisão de notas com 2 etiquetas ou mais usando Data View

table tags as Etiquetas, file.name as Cartão
from ""
where length(tags) > 2
sort file.name asc

Você verá uma **tabela com todos os seus cartões que têm mais de 2 etiquetas**, permitindo uma revisão rápida e organizada.
