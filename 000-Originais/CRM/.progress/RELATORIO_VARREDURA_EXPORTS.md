# Missão: Varredura de Exportações de WhatsApp no Google Drive

**Data:** 15/08/2026
**Objetivo:** Encontrar exportações de conversas do WhatsApp em `G:\Meu Drive` (foco: `Obsidian` e `Notebook ACER`) para enriquecer o CRM.

---

## 📊 Resultado da varredura

| Métrica | Valor |
|---|---|
| **Exportações encontradas** | **58** (únicas; duplicatas de Backup/Codex excluídas) |
| **Com card correspondente no CRM** | 23 |
| **Sem card (avaliar criação)** | 35 |
| **Status** | 57 pendentes / 1 ignorada |

## 📁 Fontes principais

1. **`Obsidian/Vaults Neo/MAT/Dados ACIRV/Conversas Zap/`** — 41 arquivos (grupos ACIRV: SudoExpo, Marketing, Diretoria, Empreender, Facieg, imprensa etc.)
2. **`Notebook ACER/Downloads/`** — Aline Dutra (5 versões!), INFOS LP, Vivianne Oliveira, Paulinho, Karol
3. **`Google AI Studio/`** — Aline Dutra, Ágora (zip), Paulinho
4. **`Obsidian/CRM/`** — Iasmim, Jéssica (já integrados aos dossiês existentes)
5. **`Obsidian/Backup de cofres/.../Dados brutos/`** — Júlia (Paulim), Jota Jao, Dj Thiago MD, Kelvyn Prof, Ione, Mari que Cria, Silvana, Chá e Prosa, Princeso Paulinho, Jéssica Xavier, VCOM, Equipe Midas (espelhadas no Codex Obsidian — duplicatas)

## 🔍 Identidades reveladas (números sem nome)

- **+55 64 8438-8531** → **FocalizeQuiri** (canal de notícias de Quirinópolis)
- **+55 64 9221-7305** → **Ranichelle do Sebrae** (pediu fotos do evento; menciona Renata e Kamélia)

## ⚠️ Correções aplicadas

- **"Conversa com Paulinho.txt"** = conversa com **Marcos Paulo Freitas** (confidente) → card `Marcos Paulo.md`
- **"Aline Dutra.txt"** = exportação "WhatsApp Chat Export Free" (100 msgs limite) → card `Aline Dutra.md`
- **"250726 preparação para conversa com psi Suzana.txt"** = **NÃO é exportação** (transcrição TurboScribe de sessão) → `skipped`
- **Duplicata de card detectada**: `Kelvyn - Prof. de Fisica e Matematica.md` vs `Kelvyn- Prof. de Fisica e Matematica.md` → dedup pendente
- INFOS LP = grupo criado por Vivianne Oliveira (12/08) — envio de BuscaProcesso.pdf e relatorio_fraudes_licitacoes.pdf (trabalho de licitações!)

## ▶️ Próximos passos (fase de processamento)

1. **Prioridade 1 — Pessoas (23 com card):** ler cada exportação e enriquecer o card (Marcos Paulo, Aline Dutra, Ione, Silvana, Mari que Cria, Jota, Júlia Paulim, Vivianne, Raphael, Janaine, José Carlos Cintra...)
2. **Prioridade 2 — Grupos ACIRV:** avaliar se valem cards próprios (SudoExpo, Marketing Conecta, Diretoria) ou apenas contexto nos cards das pessoas
3. **Prioridade 3 — Criar cards novos:** FocalizeQuiri, Ranichelle, Ágora, Lara Dutra (Lumina), Renata Gomes
4. **Dedup:** resolver duplicata Kelvyn + verificar "Júlia (Paulim)" vs "Princeso Paulinho" vs "Paulinho"

## 📁 Arquivos de controle

- `whatsapp_exports_control.json` — **fonte da verdade** (58 exportações com status, card alvo, notas)
- `whatsapp_exports_inventory.json` — inventário bruto (tamanho, data, caminho)

## 🔒 Regras

- Somente leitura; sem cópias de mensagens nos cards; sem invenção; autoria verificada no arquivo (`dd/mm/aaaa hh:mm - Nome:` no formato oficial)
