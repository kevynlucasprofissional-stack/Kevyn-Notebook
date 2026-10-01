---
id: schema-yaml
titulo: Schema YAML
tipo: infraestrutura
status: auditado
profundidade: avancada
versao_schema: '1.0'
versao_conteudo: '1.0'
idioma: pt-BR
data_criacao: 2026-06-17
ultima_revisao: 2026-06-17
tags:
- infraestrutura/schema
---
# Schema YAML

## Campos universais

```yaml
id: identificador-estavel
titulo: Título legível
tipo: tipo_principal
status: rascunho | em_revisao | revisado | auditado | arquivado
profundidade: indice | introdutoria | intermediaria | avancada | dossie | fonte_integral
versao_schema: "1.0"
versao_conteudo: "1.0"
idioma: pt-BR
data_criacao: 2026-06-17
ultima_revisao: 2026-06-17
```

## Campos epistemológicos

```yaml
camada_evidencia: registro_direto | registro_profissional | fato_corrobado | sintese_derivada | interpretacao_ia | simbolico_espiritual | hipotese_de_trabalho | misto
grau_confianca: alto | medio_alto | medio | medio_baixo | baixo | nao_avaliado
sensibilidade: baixa | media | alta | muito_alta
fontes_primarias: []
fontes_derivadas: []
```

## Campos de projetos

```yaml
estado_projeto: ideia | planejado | ativo | pausado | concluido | encerrado | incerto
horizonte: curto | medio | longo
ultima_evidencia: 2026-06-15
```

## Regra

Campos usados em Bases e Dataview usam vocabulário controlado. Prosa explicativa permanece no corpo da nota.
