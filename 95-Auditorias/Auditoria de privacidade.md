---
id: auditoria-de-privacidade
titulo: Auditoria de privacidade
tipo: auditoria
status: curado
profundidade: avancada
versao_schema: '1.0'
versao_conteudo: '1.1'
idioma: pt-BR
data_criacao: 2026-06-17
ultima_revisao: 2026-06-17
grau_confianca: alto
sensibilidade: muito_alta
camada_evidencia: documento_operacional
tags:
- tipo/auditoria
- auditoria/privacidade
notas_relacionadas:
- '[[LEIA-ME]]'
- '[[Aviso de privacidade e sensibilidade]]'
- '[[Saude mental - registros e limites]]'
- '[[Historico de pensamentos de morte]]'
- '[[Trilha de auditoria das interpretacoes]]'
- '[[Claims principais]]'
- '[[MOC Geral]]'
---

# Auditoria de privacidade

## Escopo

Verificar se o release expõe dados íntimos, dados de terceiros ou material clínico sem sinalização adequada.

## Controles aplicados

- vault classificado como privado;
- notas sensíveis marcadas como `alta` ou `muito_alta`;
- transcrições e diários mantidos em área de fontes brutas;
- aviso de privacidade no ponto de entrada;
- arquivos originais preservados, sem publicação externa;
- interpretações clínicas separadas de fatos.

## Limitação

A auditoria não testa criptografia, permissões do sistema operacional ou serviços de sincronização. O usuário deve escolher armazenamento compatível com o nível de sensibilidade.
