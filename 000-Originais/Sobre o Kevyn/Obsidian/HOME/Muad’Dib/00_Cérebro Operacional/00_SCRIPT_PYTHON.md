import json
import os
import datetime
import random
import re

# ==============================================================================
# 👇👇👇 ZONA DE CONFIGURAÇÃO (EDITE AQUI) 👇👇👇
# ==============================================================================

# 1. ONDE ESTÁ O ARQUIVO JSON?
# Cole o caminho da pasta onde você salvou o 'dados.json'.
PASTA_ENTRADA = r"C:\Users\SeuUsuario\Desktop\ProjetoNotas\entrada"
NOME_ARQUIVO_JSON = "dados.json"

# 2. PARA ONDE AS NOTAS VÃO?
# Cole o caminho da pasta de destino (pode ser direto a pasta do seu Obsidian).
PASTA_SAIDA = r"C:\Users\SeuUsuario\Documents\ObsidianVault\Inbox"

# 3. PREFIXO DO ARQUIVO
# Texto que vai no início do nome do arquivo .md (Ex: "LIVRO - " ou deixe vazio "")
PREFIXO_ARQUIVO = "LIVRO - "

# ==============================================================================
# 👆👆👆 FIM DA CONFIGURAÇÃO 👆👆👆
# ==============================================================================

def gerar_id_unico():
    """Gera um ID no formato YYYYMMDDHHmmss-random"""
    timestamp = datetime.datetime.now().strftime("%Y%m%d%H%M%S")
    chars = 'abcdefghijklmnopqrstuvwxyz0123456789'
    random_str = ''.join(random.choice(chars) for _ in range(6))
    return f"{timestamp}-{random_str}"

def limpar_nome_arquivo(nome):
    """Remove caracteres inválidos para nomes de arquivo"""
    nome_limpo = re.sub(r'[\\/*?:"<>|]', "", nome)
    return nome_limpo.strip()

def criar_nota_markdown(dados_nota):
    """Cria o conteúdo da nota baseado no modelo atômico"""
    
    id_unico = gerar_id_unico()
    data_hoje = datetime.datetime.now().strftime("%Y-%m-%d")
    
    # --- LÓGICA DAS TAGS (GARANTE #flashcards) ---
    lista_tags = dados_nota.get('tags', [])
    
    if lista_tags is None:
        lista_tags = []
        
    tags_str = " ".join(lista_tags).lower()
    if "flashcards" not in tags_str:
        lista_tags.append("#flashcards")
        
    tags_formatadas = "\n".join([f"  - \"{tag if tag.startswith('#') else '#' + tag}\"" for tag in lista_tags])
    # ---------------------------------------------

    # --- LÓGICA DAS CONEXÕES (ATUALIZADA PARA O NOVO PROMPT) ---
    conexoes_lista = []
    raw_conexoes = dados_nota.get('conexoes', [])
    
    # Verifica se existe e se é lista
    if isinstance(raw_conexoes, list):
        for item in raw_conexoes:
            link_final = ""
            motivo_final = ""

            # CASO 1: O novo formato (Dicionário/Objeto JSON)
            if isinstance(item, dict):
                link_raw = item.get('link', '')
                motivo_raw = item.get('motivo', '')
                
                if link_raw:
                    # Garante os colchetes [[ ]]
                    if not link_raw.startswith("[["):
                        link_final = f"[[{link_raw}]]"
                    else:
                        link_final = link_raw
                    
                    motivo_final = f" - {motivo_raw}" if motivo_raw else ""
                    conexoes_lista.append(f"- {link_final}{motivo_final}")

            # CASO 2: O formato antigo ou fallback (String simples)
            elif isinstance(item, str) and item.strip():
                if not item.startswith("[["):
                    link_final = f"[[{item}]]"
                else:
                    link_final = item
                conexoes_lista.append(f"- {link_final}")
    
    conexoes_formatadas = "\n".join(conexoes_lista)
    # ---------------------------------------------

    # Formatação das Ações
    acoes_brutas = dados_nota.get('acoes', [])
    if acoes_brutas is None: acoes_brutas = []
    acoes_formatadas = "\n".join([f"- [ ] {acao}" for acao in acoes_brutas])
    
    # Formatação dos Flashcards
    flashcards_brutos = dados_nota.get('flashcards', [])
    if flashcards_brutos is None: flashcards_brutos = []
    flashcards_formatados = "\n\n".join(flashcards_brutos)

    # CONSTRUÇÃO DO CONTEÚDO .MD
    conteudo = f"""---
Resumo: {dados_nota.get('resumo', 'Sem resumo')}
Contexto: {dados_nota.get('contexto', 'Sem contexto')}
tags:
{tags_formatadas}
ID único: {id_unico}
created: {data_hoje}
---
# {dados_nota.get('titulo')}

## Conceito
{dados_nota.get('conceito')}

## Importância
{dados_nota.get('importancia')}

## Insight
{dados_nota.get('insight')}

### Conexões:
{conexoes_formatadas}

## Ação
{acoes_formatadas}

## Flashcards

{flashcards_formatados}
"""
    return conteudo

def processar():
    caminho_arquivo_completo = os.path.join(PASTA_ENTRADA, NOME_ARQUIVO_JSON)
    
    if not os.path.exists(PASTA_SAIDA):
        try:
            os.makedirs(PASTA_SAIDA)
            print(f"Pasta de saída criada em: {PASTA_SAIDA}")
        except OSError as e:
            print(f"Erro ao criar pasta de saída: {e}")
            return

    print(f"Lendo arquivo de: {caminho_arquivo_completo}")

    try:
        with open(caminho_arquivo_completo, 'r', encoding='utf-8') as f:
            texto_bruto = f.read()
            
            if "```json" in texto_bruto:
                texto_bruto = texto_bruto.split("```json")[1].split("```")[0]
            elif "```" in texto_bruto:
                texto_bruto = texto_bruto.split("```")[1].split("```")[0]
            
            lista_notas = json.loads(texto_bruto)
            
            print(f"--- Iniciando processamento de {len(lista_notas)} notas ---")
            
            contagem_sucesso = 0
            for nota in lista_notas:
                try:
                    conteudo_md = criar_nota_markdown(nota)
                    
                    titulo = nota.get('titulo', 'SemTitulo')
                    nome_limpo = limpar_nome_arquivo(titulo)
                    nome_arquivo = f"{PREFIXO_ARQUIVO}{nome_limpo}.md"
                    
                    caminho_final = os.path.join(PASTA_SAIDA, nome_arquivo)
                    
                    with open(caminho_final, 'w', encoding='utf-8') as f_out:
                        f_out.write(conteudo_md)
                    
                    print(f"✅ Criado: {nome_arquivo}")
                    contagem_sucesso += 1
                except Exception as e:
                    print(f"❌ Erro ao criar nota '{nota.get('titulo', '?')}': {e}")
                
            print(f"\nProcesso finalizado! {contagem_sucesso} notas geradas na pasta: \n{PASTA_SAIDA}")

    except FileNotFoundError:
        print(f"\n⛔ ERRO CRÍTICO: O arquivo não foi encontrado!")
        print(f"Verifique se o caminho está correto na Configuração: {caminho_arquivo_completo}")
    except json.JSONDecodeError as e:
        print(f"\n⛔ ERRO NO JSON: O conteúdo do arquivo não é um JSON válido.")
        print(f"Dica: Verifique se o AI Studio gerou o JSON completo sem cortar o final.")
        print(f"Erro detalhado: {e}")
    except Exception as e:
        print(f"\n⛔ Erro inesperado: {e}")

if __name__ == "__main__":
    processar()