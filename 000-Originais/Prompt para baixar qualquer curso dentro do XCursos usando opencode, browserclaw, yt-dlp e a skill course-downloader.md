Use a skill `course-downloader`.

Baixe **completamente o curso que está atualmente aberto no BrowserClaw**, da primeira aula válida até a última.

Regras obrigatórias:

- Use o **BrowserClaw** para navegar pelo curso.
    
- Use o **yt-dlp** para baixar as videoaulas.
    
- Considere o curso atualmente aberto como o `CURSO_ALVO`.
    
- Comece pela **primeira aula real do curso**, mesmo que a página esteja atualmente em outra posição.
    
- Percorra todas as aulas na **ordem real da plataforma**.
    
- Use o contador global da plataforma e a navegação **Próxima** como referência principal quando disponíveis.
    
- Para cada aula:
    
    1. identifique curso, módulo, aula e posição;
        
    2. identifique a fonte de vídeo usando a estratégia definida pela skill;
        
    3. baixe o vídeo com `yt-dlp`;
        
    4. valide que o arquivo foi criado corretamente;
        
    5. registre o progresso;
        
    6. avance somente uma aula;
        
    7. confirme que a posição mudou corretamente antes de continuar.
        
- Não baixe PDFs, ZIPs, planilhas, prompts ou outros materiais complementares.
    
- Não use links `/api/materials/download` como videoaula.
    
- Não baixe a mesma aula duas vezes.
    
- Não confie no status “Concluída” da plataforma para decidir se uma aula já foi baixada.
    
- Não reorganize as aulas com base apenas nos números escritos nos títulos.
    
- Não abra novas abas desnecessariamente se a página correta do curso já estiver aberta.
    
- Não entre em loops de ferramentas. Se uma abordagem retornar `undefined`, falhar ou não produzir nova informação, mude de estratégia em vez de repetir a mesma chamada.
    
- Salve os vídeos dentro de `Downloads/Cursos/`, organizados automaticamente por:  
    `Nome do Curso / Módulo / Aula`.
    
- Preserve e utilize o estado da execução para permitir retomada em caso de erro ou interrupção.
    
- Se uma URL de vídeo assinada expirar, obtenha uma URL nova na própria aula e tente novamente.
    
- Se uma aula usar um player diferente do padrão do XCursos, use o fallback provider-agnostic da skill.
    
- Se houver DRM, registre a aula como `DRM_PROTECTED` e continue sem tentar contornar a proteção.
    
- Continue trabalhando autonomamente até chegar à última aula. Não me pergunte a cada etapa se deve continuar.
    
- Só considere o curso concluído depois de auditar que todas as posições foram processadas ou devidamente classificadas.
    

Ao terminar, apresente um relatório contendo:

- nome do curso;
    
- total de aulas identificado;
    
- quantidade de aulas processadas;
    
- downloads concluídos;
    
- falhas;
    
- aulas sem vídeo;
    
- aulas protegidas por DRM;
    
- posições eventualmente recuperadas após saltos;
    
- pasta final onde o curso foi salvo.
    

Se todas as aulas tiverem sido cobertas corretamente, finalize com:

**DOWNLOAD COMPLETO DO CURSO CONCLUÍDO**

Caso existam exceções, finalize com:

**PROCESSAMENTO CONCLUÍDO COM EXCEÇÕES**