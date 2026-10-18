# DESCRIPCIÓN:
I found this cipher in an old book. Can you figure out what it says? Connect with nc...

# SOLUCIÓN:
#### picoCTF{b311a_luna}
┌──(mony㉿Mony)-[~] └─$ # Texto capturado por netcat y analizado en un Vigenère Solver automático.

# NOTAS ADICIONALES:
El título del reto es una referencia histórica a Giovan Battista Bellaso y su "Cifra", precursora del cifrado Vigenère. Al conectarnos por netcat nos regresa un bloque de texto muy largo en inglés cifrado. Usando análisis de frecuencia automatizado, se descubre que la llave es "flag" y se decodifica todo el mensaje.

# REFERENCIAS:
https://webshell.cylabacademy.org/