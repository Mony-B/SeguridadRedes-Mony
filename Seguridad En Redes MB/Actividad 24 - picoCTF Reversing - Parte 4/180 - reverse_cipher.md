# DESCRIPCIÓN:
We have recovered a binary (rev) and a text file (rev_this). Can you reverse the flag.
Hint: objdump y Ghidra son herramientas que podrían ayudar con esto.

# SOLUCIÓN:
#### academy{r3v3rs397436647}

1. Se descargan los dos archivos: el binario `rev` y el archivo `rev_this` (que contiene el texto ya cifrado: `academy{w1{1wq87<284;2<}`).
2. Se desensambla `main` del binario con gdb/objdump para entender el algoritmo:
   - El programa abre `flag.txt` (lectura) y `rev_this` (escritura), lee 24 bytes de `flag.txt` y los transforma byte a byte antes de escribirlos en `rev_this`:
     - Índices 0-7: se copian sin modificar.
     - Índices 8-22: si el índice es **par**, se le suma 5 al byte; si es **impar**, se le resta 2.
     - Índice 23: se copia sin modificar.
3. Como ya tenemos la salida (`rev_this`), basta con invertir la transformación byte a byte sobre ese archivo:
   - Índices 0-7 y 23: se dejan igual.
   - Índices 8-22: si el índice es **par**, se le resta 5; si es **impar**, se le suma 2.
4. Script en Python para decodificar:
```python
enc = 'academy{w1{1wq87<284;2<}'
out = []
for i, c in enumerate(enc):
    b = ord(c)
    if i <= 7 or i == 23:
        out.append(chr(b))
    elif i % 2 == 0:
        out.append(chr(b - 5))
    else:
        out.append(chr(b + 2))
print(''.join(out))
# academy{r3v3rs397436647}
```

# NOTAS ADICIONALES:
El nombre de la flag es un juego de palabras: "r3v3rs3" (reverse en leetspeak) + un número identificador de instancia. El binario también imprime "No flag found, please make sure this is run on the server" si no logra abrir `flag.txt`, lo cual confirma que la lógica de transformación es la relevante y no la ejecución directa del programa.

# REFERENCIAS:
N/A
