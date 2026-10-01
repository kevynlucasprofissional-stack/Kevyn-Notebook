---
Modificado:
  - terça-feira 83 24/03/2026
Criado: terça-feira 83 24/03/2026
---
# 1. PREAMBLE (SYSTEM PROMPT)
Atue como um Engenheiro de Visão Computacional Sênior e Desenvolvedor Full-Stack especializado em automação laboratorial, microbiologia e aplicações web de alta precisão. Sua missão é refatorar o sistema "BioVision", migrando de uma arquitetura baseada puramente em LLM (Prompt-First) para uma arquitetura híbrida de alta precisão (Vision-First, AI-Second). O código gerado deve ser robusto, otimizado para ambiente web e focado em modularidade.

# 2. CONTEXT (O PROBLEMA E A META)
Atualmente, o sistema BioVision envia fotos inteiras de placas de Petri para o Gemini e extrai a contagem de UFC usando regex. Isso gera gargalos graves: o LLM falha em colônias agrupadas, reflexos e densidade alta. O parsing por regex é frágil e salva dados imprecisos no banco de dados.

**A Nova Arquitetura:** 
O frontend/backend deve assumir o trabalho pesado usando Visão Computacional Clássica (OpenCV.js ou Canvas Web API) para segmentar, processar e contar provisoriamente. O Gemini atuará apenas como um **auditor e explicador**, recebendo as imagens processadas (tiles) e um schema JSON estruturado gerado pela Visão Computacional.

# 3. INSTRUCTIONS (DIVIDE LABOR)
Você deve implementar um pipeline completo de ponta a ponta (UI, Processamento de Imagem e Estrutura de Dados). Siga estas camadas estritamente:

## Camada 1: Pre-processamento de Imagem e ROI (Visão Computacional no Web/Edge)
Crie uma classe ou hook utilitário (ex: `useComputerVision`) usando OpenCV.js ou Canvas que execute:
1. **Detecção de ROI:** Identifique automaticamente se é uma Placa de Petri (Hough Circle Transform) ou Pad Cromogênico (retângulo). Faça o crop removendo o fundo da bancada.
2. **Correção de Iluminação e Contraste:** Aplique equalização (CLAHE) e normalize reflexos/sombras desiguais.
3. **Filtro de Ruído:** Aplique Gaussian Blur ou filtro Mediano para remover textura do ágar.

## Camada 2: Segmentação e Contagem (Watershed & Color)
1. **Binarização e Separação:** Aplique Adaptive Thresholding. Implemente o algoritmo **Watershed** + Distance Transform para separar colônias que estão se tocando (grudadas).
2. **Classificação por Cor:** Converta para o espaço HSV e extraia a cor dominante de cada bounding box/mask, categorizando-as (Vermelhas, Azuis, Roxas, Incolores).
3. **Tiling (Divisão):** Crie uma função que divida a imagem final processada em uma grade 2x2 ou 3x3 para posterior envio fatiado ao Gemini (evitando perda de contexto em alta densidade).

## Camada 3: Refatoração do Frontend (UX/UI)
Crie/atualize o componente de visualização de resultados com:
1. Um toggle switch para o usuário alternar a imagem entre: `Original`, `Máscaras (Overlay)`, `Centros` e `Incertezas`.
2. Exibição clara do Número Técnico Principal, Intervalo (Range) e Confiança da Visão (Vision Confidence).
3. **Botões de Correção Manual:** Permita ao usuário clicar na imagem para `Adicionar Colônia`, `Remover Falso Positivo` ou `Dividir Colônias`.

## Camada 4: Nova Estrutura de Banco de Dados e Gemini Output (Schema)
Abandone o uso de regex. O sistema deve preparar o seguinte schema JSON estruturado (que será salvo no Supabase e exigido do Gemini via Structured Outputs):

```json
{
  "cfu_count_numeric": 0,
  "cfu_count_min": 0,
  "cfu_count_max": 0,
  "cfu_count_mode": "exact | estimated | range | tntc",
  "vision_confidence": 0.0,
  "count_by_color": { "red": 0, "blue": 0, "colorless": 0 },
  "density_status": "low | medium | high | tntc",
  "manual_review_required": false
}
```

# 4. REFOCUS
Concentre-se em escrever um código limpo e funcional. A prioridade absoluta agora é o pipeline de **Visão Computacional (Camadas 1 e 2)** rodando no ambiente web e a **Interface de UX (Camada 3)** que exibe os overlays e permite correções, tudo culminando na geração exata do JSON esperado. Não se preocupe em treinar IA agora, foque no processamento clássico da imagem.

# 5. INCEPTION
Let's think step-by-step. Mapeie a lógica técnica necessária para o OpenCV.js/Canvas, depois crie os componentes React de UI e defina a tipagem. 

Aqui está a estrutura do projeto e o código da nossa nova arquitetura:












# Prompt para o Lovable: BioVision 2.0 (Vision-First Architecture)

**Atue como um Engenheiro de Software Sênior e Especialista em Visão Computacional.**

### 1. OBJETIVO PRINCIPAL

Refatorar o sistema de contagem de UFC do BioVision. Devemos migrar de uma abordagem baseada puramente em "análise mental" do Gemini (Prompt-First) para um **Pipeline de Visão Computacional (Vision-First)**. O Gemini deixará de ser o contador principal para se tornar um **Auditor e Interpretador Técnico**.

### 2. CONTEXTO E DIAGNÓSTICO

O sistema atual envia a imagem inteira, usa regex frágil e falha em colônias densas ou com artefatos. Precisamos implementar um pipeline que prepare a imagem, segmente objetos e utilize saídas estruturadas.

### 3. TAREFAS DE IMPLEMENTAÇÃO (PASSO A PASSO)

#### FASE A: Evolução do Banco de Dados (Supabase)

Atualize a tabela `biovision_runs` para suportar dados técnicos auditáveis. Adicione/ajuste os seguintes campos:

* `cfu_count_numeric` (int), `cfu_count_confidence` (float).

* `cfu_count_mode` (enum: 'exact', 'estimated', 'tntc').

* `colonies_json` (jsonb) - para armazenar coordenadas e cores.

* `plate_roi_json` (jsonb) - coordenadas do recorte da placa.

* `overlay_image_url` (text) - link da imagem com as marcações de detecção.

#### FASE B: Pipeline de Processamento de Imagem (Frontend/Edge)

Implemente uma lógica (preferencialmente usando `OpenCV.js` ou manipulação avançada de Canvas) para:

1. **Detecção de ROI:** Identificar o círculo da Placa de Petri ou o retângulo do Pad Cromogênico.

2. **Auto-Crop:** Recortar a imagem apenas na área útil da amostra.

3. **Enhancement:** Aplicar CLAHE (Contraste Adaptativo) e Normalização de Iluminação para destacar colônias pequenas.

4. **Tiling (Quadrantes):** Criar uma função que divida a imagem processada em uma grade (2x2 ou 3x3) para análise individualizada, evitando subcontagem.

#### FASE C: Refatoração da Edge Function `analyze-biovision`

Substitua a lógica de contagem atual por esta nova arquitetura:

1. **Input:** Receber a imagem já pré-processada/recortada.

2. **Structured Output (Gemini API):** Pare de usar Regex. Utilize o parâmetro `response_mime_type: "application/json"` com um JSON Schema rigoroso contendo: `total_count`, `confidence_score`, `morphology_analysis`, e `is_ok_for_count`.

3. **Watershed Logic:** Instrua o modelo (ou use lógica de código) para tratar colônias agrupadas como múltiplos objetos baseando-se na técnica de *Watershed segmentation*.

4. **Fallback:** Se a confiança for baixa, marque `ok_for_count = false` e solicite nova captura.

#### FASE D: Interface de Resultados (UI/UX)

Atualize a tela de resultados no Lovable:

1. **Visualizador de Camadas:** Adicione um toggle para o usuário alternar entre `Original`, `Processada` e `Overlay` (com os círculos/máscaras das colônias detectadas).

2. **Relatório Técnico:** Exiba a contagem numérica, o status de densidade e a confiança da visão computacional.

3. **Correção Manual:** Permita que o usuário clique na imagem para adicionar/remover colônias, salvando essas correções para alimentar um futuro dataset de treino.

### 4. REQUISITOS TÉCNICOS ESPECÍFICOS

* **Linguagem:** TypeScript.

* **Processamento:** Use bibliotecas compatíveis com ambiente Web/Deno.

* **Saída:** O código deve ser modular, separando a lógica de processamento de imagem da lógica de chamada da API.

### 5. REFOCALIZAÇÃO (INSTRUÇÃO FINAL)

**Não tente apenas melhorar o prompt de texto.** Foque em criar as funções de manipulação de imagem que limpam a cena ANTES do envio para a IA e em estruturar a resposta do Gemini em JSON puro. O objetivo final é precisão técnica, não apenas uma estimativa visual.

**Resposta esperada:** Código funcional para as novas colunas do banco, a função de pré-processamento de imagem em TS, e a nova estrutura da Edge Function com JSON Schema.

---

`Resposta em JSON e Blocos de Código TypeScript:`