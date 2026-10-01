**1º** Primeiro baixe em JPG todos os arquivos que irá precisar, que geralmente serão meta, difusse, displacement, normal map (DX e GL) e Rough. 

**2º** Crie um material universal. Dê dois clicks no material universal e entre no Node Editor.

**3º** Importe os JPG baixados para dentro do Node Editor. Link difusse/Albedo, Rough/Roughness, normal/normal (O roxo sempre é o normal), displacement/texture do Displacement linkado ao displacement universal (Crie um displacement com o Shift+C, link ao displacement Universal, e link o JPG Displacement em Texture do displacement).

**4º** Caso fique muito grande, crie um Transform com o Shift+C, link em todas as texturas JPG e diminua a escala com o lock aspect radio ativado.