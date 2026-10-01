# Plano de Mudancas - Ciclo 0004

## Escopo

Lote `SRC-000021` a `SRC-000034`, em `Outras notas criadas por Kevyn`.

## Decisoes do lote

- Tratar `SRC-000021` e `SRC-000022` como conteudo operacional sensivel. Credenciais, senhas e chaves nao serao copiadas para o vault.
- Tratar `SRC-000024` como material produzido/rascunhado por Kevyn sobre funil/copy de emagrecimento, nao como fonte sobre emagrecimento ou saude.
- Tratar `SRC-000023` e `SRC-000025` a `SRC-000034` como evidencias de planejamento de campanha/oficina de IA chamada IMRIA, com foco em co-pilotos, promessa pratica, oferta, escassez, preco e roteiros curtos.
- Criar uma nota de fonte agregada para o lote, sem transcrever segredos nem reproduzir o e-book.

## Mudancas previstas

### UNI-000014

- Fontes: `SRC-000021` e `SRC-000022`.
- Destinos: `Fonte - Materiais IMRIA e marketing 2025`, `Inteligencia artificial e automacao`, `Metodo de estudo e producao`.
- Operacao: criar fonte agregada e ampliar notas existentes.
- Justificativa: os arquivos mostram uso de curso/Hotmart, intencao de gravar, criar notas atomicas e agente RAG, alem de manutencao de credencial Gemini.
- Risco de duplicacao: baixo.
- Risco interpretativo: medio; nao inferir dominio tecnico apenas por haver credencial.
- Validacao prevista: verificar ausencia de segredo copiado.

### UNI-000015

- Fontes: `SRC-000023`, `SRC-000025` a `SRC-000034`.
- Destinos: `Fonte - Materiais IMRIA e marketing 2025`, `Inteligencia artificial e automacao`, `Marketing comunicacao e processos`, `Portfolio de projetos`.
- Operacao: criar fonte agregada e ampliar notas existentes.
- Justificativa: o conjunto evidencia campanha/oficina pratica de IA, roteiros de criativos, funil de oferta, escassez, garantia e posicionamento de co-pilotos.
- Risco de duplicacao: medio, mitigado por integrar apenas padroes de competencia.
- Risco interpretativo: medio; nao presumir realizacao do evento sem evidencia externa de execucao.
- Validacao prevista: registrar como projeto/material de campanha com continuidade nao confirmada.

### UNI-000016

- Fonte: `SRC-000024`.
- Destinos: `Fonte - Materiais IMRIA e marketing 2025`, `Marketing comunicacao e processos`, `Negocios e marketing`.
- Operacao: criar fonte agregada e ampliar notas existentes.
- Justificativa: o e-book mostra producao de copy/funil, gatilhos de marketing, narrativa de dor-transformacao e uso de Excalidraw; nao descreve Kevyn diretamente.
- Risco de duplicacao: alto se o texto for copiado; mitigacao: nao reproduzir o e-book.
- Risco interpretativo: alto se for tratado como orientacao de saude; mitigacao: classificar como material de marketing produzido/estudado.
- Validacao prevista: revisar ausencia de conteudo de emagrecimento como secao tematica do vault.

## Mudancas fora do escopo

- Nao salvar API keys, senhas, e-mails de acesso ou links autenticados.
- Nao criar nota sobre nutricao, dieta ou emagrecimento.
- Nao validar a qualidade medica, juridica ou comercial das promessas de marketing.
- Nao alterar `Dados Kevyn`.
