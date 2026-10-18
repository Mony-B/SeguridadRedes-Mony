# DESCRIPCIÓN:
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with nc...

# SOLUCIÓN:
#### picoCTF{frequency_is_c_over_lambda} 

┌──(mony㉿Mony)-[~] └─$ # Bloque de texto extraído y analizado en Quipqiup.

# NOTAS ADICIONALES:
Se trata de un cifrado de sustitución simple aleatorio (no es un desplazamiento lineal como César). Cada letra fue cambiada por otra distinta. La forma matemática de romper esto es mediante "Análisis de Frecuencias" evaluando cuáles letras se repiten más en el texto cifrado y emparejándolas con las letras más comunes del idioma inglés (E, T, A, O, I, N).

# REFERENCIAS:
https://webshell.cylabacademy.org/