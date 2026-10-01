# 1️⃣ Mapa macro do app (visão geral)

Este é o **mapa de arquitetura do app** baseado no seu Sprint.

```
                ┌───────────────┐
                │   Splash      │
                │   Tela Logo   │
                └───────┬───────┘
                        │
                        ▼
                ┌───────────────┐
                │   Tela 0      │
                │ Boas-vindas   │
                └───┬─────┬─────┘
                    │     │
        ┌───────────┘     └──────────────┐
        ▼                                ▼
 ┌──────────────┐                 ┌──────────────┐
 │ Tela 1       │                 │ Tela 3       │
 │ Login        │                 │ Cadastro     │
 │              │                 │ Profissional │
 └──────┬───────┘                 └──────┬───────┘
        │                                │
        │                                ▼
        │                         ┌──────────────┐
        │                         │ Tela 21      │
        │                         │ Cadastro     │
        │                         │ profissional │
        │                         └──────┬───────┘
        │                                │
        │                                ▼
        │                         ┌──────────────┐
        │                         │ Tela 22      │
        │                         │ Serviços     │
        │                         └──────┬───────┘
        │                                │
        │                                ▼
        │                         ┌──────────────┐
        │                         │ Tela 23      │
        │                         │ Portfólio    │
        │                         └──────┬───────┘
        │                                │
        │                                ▼
        │                         ┌──────────────┐
        │                         │ Tela 20      │
        │                         │ Home         │
        │                         │ Profissional │
        │                         └──────────────┘
        │
        ▼
 ┌──────────────┐
 │ Tela 5       │
 │ Home Cliente │
 └───-────┬─────┘
          │
          ▼
       ┌──────────────┐
       │ Tela 6       │
       │ Busca        │
       └─────┬────────┘
             │
             ▼
       ┌──────────────┐
       │ Tela 8       │
       │ Perfil       │
       │ Profissional │
       └─────┬────────┘
             │
             ▼
       ┌──────────────┐
       │ Tela 9       │
       │ Solicitar    │
       │ Agendamento  │
       └─────┬────────┘
             │
             ▼
       ┌──────────────┐
       │ Tela 10      │
       │ Confirmação  │
       └─────┬────────┘
             │
             ▼
       ┌──────────────┐
       │ Tela 12      │
       │ Agendamentos │
       └─────┬────────┘
             │
             ▼
       ┌──────────────┐
       │ Tela 15      │
       │ Detalhe      │
       │ Atendimento  │
       └─────┬────────┘
             │
             ▼
       ┌──────────────┐
       │ Tela 16      │
       │ Avaliação    │
       └──────────────┘
```

---

# 2️⃣ Fluxo da cliente (a jornada mais importante)

Esse é o **fluxo principal de conversão do app**.

```
Abrir app
   │
   ▼
Boas-vindas
   │
   ▼
Criar conta / Login
   │
   ▼
Home cliente
   │
   ▼
Buscar serviço
   │
   ▼
Lista de profissionais
   │
   ▼
Perfil da profissional
   │
   ▼
Solicitar agendamento
   │
   ▼
Profissional aceita
   │
   ▼
Atendimento realizado
   │
   ▼
Avaliação
```

Isso representa exatamente o macro fluxo que está descrito no Sprint.

---

# 3️⃣ Fluxo da profissional

```
Boas-vindas
   │
   ▼
Quero divulgar meus serviços
   │
   ▼
Cadastro profissional
   │
   ▼
Cadastrar serviços
   │
   ▼
Enviar portfólio
   │
   ▼
Conta aprovada
   │
   ▼
Home profissional
   │
   ▼
Receber pedidos
   │
   ▼
Aceitar atendimento
   │
   ▼
Realizar atendimento
   │
   ▼
Marcar como concluído
```

---

# 4️⃣ Mapa ideal para usar em produto (tipo Uber / Airbnb)

O que as startups fazem normalmente é transformar isso em um **User Flow Diagram**.

Exemplo simplificado:

```
           CLIENTE
              │
              ▼
        Buscar serviço
              │
              ▼
      Ver profissionais
              │
              ▼
       Ver perfil
              │
      ┌───────┴───────┐
      ▼               ▼
  Favoritar      Solicitar
                    │
                    ▼
             Profissional
               recebe
                    │
                    ▼
               Aceita
                    │
                    ▼
               Atendimento
                    │
                    ▼
                Avaliação
```

---

# 5️⃣ Outros mapas

Posso montar para você:

### 🧭 **Mapa visual estilo Figma / UX**

tipo:

```
[Splash]
   ↓
[Welcome]
   ↓
[Login] ─── [Cadastro cliente]
   ↓
[Home]
   ↓
[Busca]
   ↓
[Perfil profissional]
   ↓
[Agendamento]
```

ou ainda melhor:

### 🧠 **Diagrama Mermaid (usado em Notion / Obsidian / GitHub)**

que gera **um fluxograma automático**.

Exemplo:

```
flowchart TD
A[Splash] --> B[Boas vindas]
B --> C[Login]
B --> D[Criar conta]
C --> E[Home cliente]
D --> E
E --> F[Buscar profissionais]
F --> G[Perfil profissional]
G --> H[Solicitar agendamento]
H --> I[Confirmação]
I --> J[Agendamentos]
```

Isso vira um **fluxograma visual automático**.

---

**Sugestão visual da mapa de telas:**
![[Pasted image 20260311230942.png]]