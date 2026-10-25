# DESCRIPCIÓN:
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher? Download the message [here](https://challenge-files.cylabacademy.net/library/0a2e91276318c0f6d400f5096fdaf87fcf57f37ebabf90004552502979a581c8/message.txt).

# SOLUCIÓN:
#### academy{5UB5717U710N_3V0LU710N_4FBD1EB7}

El archivo empieza con la clave del cifrado en la primera línea: `HRZUEVABDLIOJYTGNXCMWPKSQF`, que es el alfabeto cifrado (A→H, B→R, C→Z, ...).

```python
key = 'HRZUEVABDLIOJYTGNXCMWPKSQF'
decrypt = {}
for i, c in enumerate(key):
    decrypt[c] = chr(ord('A') + i)
    decrypt[c.lower()] = chr(ord('a') + i)

text = open('message.txt').read()
result = ''.join(decrypt.get(c, c) for c in text)
print(result)
```

El texto descifrado revela un fragmento de "The Gold-Bug" de Edgar Allan Poe, terminando con:
```
The flag is: academy{5UB5717U710N_3V0LU710N_4FBD1EB7}
```

# NOTAS ADICIONALES:
Al tener la clave (el alfabeto cifrado completo) al inicio del mensaje, no hizo falta análisis de frecuencia — solo construir la tabla inversa letra por letra.

# REFERENCIAS:
https://en.wikipedia.org/wiki/Frequency_analysis
https://www.dcode.fr/substitution-cipher
https://webshell.cylabacademy.org/
