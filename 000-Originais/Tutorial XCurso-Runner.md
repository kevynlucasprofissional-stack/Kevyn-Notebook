Se você acabou de baixar/extrair essa versão nova, a sequência correta no **PowerShell** é esta. O próprio instalador recomenda o fluxo `doctor → login → probe`.

### 1. Entrar na pasta que você baixou

Exemplo:

```powershell
cd "C:\Users\SEU_USUARIO\Downloads\xcursos-runner"
```

Use o caminho real da pasta extraída.

### 2. Instalar/atualizar o XCursos Runner

```powershell
powershell -ExecutionPolicy Bypass -File .\install.ps1
```

Esse script instala o runner em `%LOCALAPPDATA%\XCursosRunner`, configura o `xcursos` e o `xcursos-all` no PATH e preserva a configuração, perfil do Chrome e estado anterior.

Depois que terminar, **feche esse PowerShell e abra outro novo**.

### 3. Verificar se a versão instalada está acessível

```powershell
xcursos version
```

Hoje o projeto ainda reporta internamente **4.2.6**, porque a melhoria de `SKIPPED` foi adicionada sem novo bump de versão.

### 4. Verificar toda a configuração

```powershell
xcursos doctor
```

Aqui você quer conferir principalmente:

```text
Node.js      OK
Chrome       OK
yt-dlp       OK
ffprobe      OK
```

O runner exige Node 22/24/26, Chrome Stable, `yt-dlp` e `ffprobe`.

Se tudo estiver OK, prossiga.

### 5. Abrir o Chrome dedicado do XCursos

```powershell
xcursos login
```

Vai abrir o Chrome próprio do runner.

Então:

1. passe pelo Cloudflare manualmente, se aparecer;
    
2. faça login no XCursos;
    
3. entre no curso **VENDA TODO SANTO DIA 2026 - LEANDRO LADEIRA**;
    
4. abra uma aula normal;
    
5. volte ao PowerShell;
    
6. pressione **ENTER**.
    

Esse é exatamente o fluxo previsto pelo runner.

### 6. Confirmar que ele está entendendo corretamente a aula

```powershell
xcursos probe --json
```

Aqui ele **não baixa nada**. Só verifica se consegue identificar corretamente curso, aula, posição, total e mídia.

Eu recomendo fazer esse teste antes de iniciar tudo.

### 7. Opcional: teste de uma única aula

Se quiser ter certeza de que download + ffprobe estão funcionando:

```powershell
xcursos current --json
```

Isso processa apenas a aula que está aberta.

Não é obrigatório.

### 8. Script final — baixar/continuar o curso inteiro

Depois disso:

```powershell
xcursos-all
```

Esse é o comando que você realmente deixa rodando.

Ele:

- retoma o estado anterior;
    
- não baixa novamente aulas já concluídas;
    
- usa retries;
    
- tenta recuperar falhas transitórias;
    
- salva checkpoints;
    
- continua o curso;
    
- e, **na versão que acabamos de alterar, as posições 106–123 serão registradas como `SKIPPED` e não serão baixadas**.
    

Então, na prática, seu fluxo desta vez é:

```powershell
# 1. Na pasta extraída
powershell -ExecutionPolicy Bypass -File .\install.ps1

# 2. Fechar o PowerShell e abrir outro

# 3. Conferir instalação
xcursos version

# 4. Conferir dependências
xcursos doctor

# 5. Abrir/login no Chrome XCursos
xcursos login

# 6. Conferir se reconheceu a aula
xcursos probe --json

# 7. FINAL
xcursos-all
```

**Não precisa apagar manifesto, pasta do curso, perfil do Chrome nem downloads anteriores.** A atualização foi projetada justamente para reaproveitar esse estado.