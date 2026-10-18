# DESCRIPCIÓN:
Decrypt this message. Nos dan un archivo con el texto cifrado dentro del formato picoCTF{}.
# SOLUCIÓN:
#### picoCTF{crossingtherubicon} 

┌──(mony㉿Mony)-[~] └─$ # Fuerza bruta en la terminal iterando todos los desplazamientos posibles: └─$ for i in {1..25}; do echo "texto_cifrado_aqui" | tr $(printf %${i}s | tr ' ' '.')a-z a-za-z; done

# NOTAS ADICIONALES:
Cifrado César clásico (desplazamiento de caracteres). Como no sabíamos la llave (el número de posiciones), se aplicó fuerza bruta rotando el abecedario hasta encontrar la frase con sentido en inglés.

# REFERENCIAS:
https://webshell.cylabacademy.org/