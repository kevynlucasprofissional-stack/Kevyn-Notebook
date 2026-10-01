---

### **Análise da Otimização e Nota para o Engenheiro:**

1.  **Papel Especializado:** O agente agora é um "Estrategista de Análise". Isso o coloca na posição correta: ele não está fazendo a análise final, está planejando e avaliando a viabilidade dela.

2.  **Contrato de Dados Modificado:** Este é o ponto crucial. O contrato deste prompt é diferente dos outros. Ele não espera um único arquivo de dados, mas sim o **"CORPUS DE DADOS COMPLETO"**. Ele também precisa de um segundo input: a **"LISTA DE FRAMEWORKS DE ANÁLISE"**.

3.  **Instruções Claras e Acionáveis:** As instruções foram divididas em "Etapa A" e "Etapa B", tornando o processo mais lógico para a IA. O seu excelente exemplo foi integrado diretamente nas instruções para guiar o tom e o conteúdo da resposta.

4.  **Saída Estruturada:** O formato de saída é explicitamente definido. Isso garante que o resultado seja consistente e fácil de ler toda vez que você rodar o processo.

---

### **💡 Nota para o Engenheiro (Como adaptar o `main.py`)**

Este prompt é um "Passo Zero" especial e deve ser executado **antes** do loop principal de análise. A lógica no seu `main.py` precisará de uma função dedicada para isso, algo como `executar_analise_de_dados(nome_alvo)`.

Esta função deverá fazer o seguinte:

1.  **Coletar todos os dados:** Ler **todos** os arquivos dentro da pasta `input_data/nome_do_alvo` e juntar todo o conteúdo em uma única string gigante (`corpus_completo`).
2.  **Coletar os frameworks:** Ler os nomes dos arquivos na pasta `prompt_parts` (de `02_` em diante) para criar a lista de frameworks (ex: `['DISC Analyzer', 'Eneagrama Analyzer', ...]`).
3.  **Montar o Prompt Especial:** Construir o prompt final combinando o conteúdo deste `01_gestao_dados.md`, o `corpus_completo` e a `lista_de_frameworks`.
4.  **Executar e Salvar:** Chamar a API do Gemini uma única vez e salvar o resultado como `output_analysis/nome_do_alvo/_Relatorio_Qualidade_Dados.md` (o underscore `_` no início do nome é uma boa prática para indicar que é um arquivo de metadados e fazê-lo aparecer no topo da lista de arquivos).

Depois que esta função rodar, seu loop principal (`processar_alvo`) pode começar, executando as análises individuais (`02_disc`, `03_eneagrama`, etc.) como planejado anteriormente.

Esta abordagem mantém a modularidade e adiciona uma camada de inteligência estratégica ao seu processo.