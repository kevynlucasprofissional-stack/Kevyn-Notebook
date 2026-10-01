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
# DICA: No Windows, mantenha o 'r' antes das aspas para evitar erros com barras.
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
    # Remove caracteres proibidos em sistemas de arquivos
    nome_limpo = re.sub(r'[\\/*?:"<>|]', "", nome)
    # Remove espaços extras e quebras de linha
    return nome_limpo.strip()

def criar_nota_markdown(dados_nota):
    """Cria o conteúdo da nota baseado no modelo atômico"""
    
    id_unico = gerar_id_unico()
    data_hoje = datetime.datetime.now().strftime("%Y-%m-%d")
    
    # --- LÓGICA DAS TAGS (GARANTE #flashcards) ---
    lista_tags = dados_nota.get('tags', [])
    
    # Se a lista vier vazia ou None, inicializa como lista
    if lista_tags is None:
        lista_tags = []
        
    # Normaliza tags para string e verifica existência de flashcards
    tags_str = " ".join(lista_tags).lower()
    if "flashcards" not in tags_str:
        lista_tags.append("#flashcards")
        
    # Formatação final das tags para o YAML
    tags_formatadas = "\n".join([f"  - \"{tag if tag.startswith('#') else '#' + tag}\"" for tag in lista_tags])
    # ---------------------------------------------

    # Formatação das Conexões
    conexoes_lista = []
    for conexao in dados_nota.get('conexoes', []):
        if conexao: # Evita itens vazios
            if not conexao.startswith("[["):
                conexao = f"[[{conexao}]]"
            conexoes_lista.append(f"- {conexao}")
    conexoes_formatadas = "\n".join(conexoes_lista)

    # Formatação das Ações
    acoes_formatadas = "\n".join([f"- [ ] {acao}" for acao in dados_nota.get('acoes', [])])
    
    # Formatação dos Flashcards
    flashcards_formatados = "\n\n".join(dados_nota.get('flashcards', []))

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
    # Monta os caminhos completos
    caminho_arquivo_completo = os.path.join(PASTA_ENTRADA, NOME_ARQUIVO_JSON)
    
    # Cria pasta de saída se não existir
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
            
            # Limpeza de blocos de código markdown (```json ... ```)
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