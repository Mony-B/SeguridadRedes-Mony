# DESCRIPCIÓN:
**rotation** — Cryptography (Medium) — by Loic Shema · picoCTF 2023

Dan un `encrypted.txt` con la flag cifrada. El hint "Sometimes rotation is right" apunta a un cifrado César con rotación hacia la derecha.

# SOLUCIÓN:
#### academy{r0tat1on_d3crypt3d_42440c4b}

El contenido de `encrypted.txt` fue:
```
ikilmug{z0bib1wv_l3kzgxb3l_42440k4j}
```

Como ya sabía que el formato de flag siempre es `academy{...}`, comparé letra por letra `academy` vs `ikilmug`:

| plano | a | c | a | d | e | m | y |
| ----- | - | - | - | - | - | - | - |
| cifrado | i | k | i | l | m | u | g |

`a→i` es un desplazamiento de **+8** (César hacia la derecha, como decía el hint). Confirmé que el shift +8 es consistente en las 7 letras y lo apliqué en reversa (-8) a todo el string para descifrar:

```python
s = 'ikilmug{z0bib1wv_l3kzgxb3l_42440k4j}'
def dec(c):
    if c.isalpha():
        base = ord('a') if c.islower() else ord('A')
        return chr((ord(c)-base-8)%26+base)
    return c
print(''.join(dec(c) for c in s))
# academy{r0tat1on_d3crypt3d_42440c4b}
```

Los dígitos y el guion bajo se dejan intactos (no son parte del alfabeto rotado).

# NOTAS ADICIONALES:
No hizo falta fuerza bruta de los 26 shifts posibles: como el prefijo de la flag siempre es literalmente la palabra `academy`, comparar `academy` contra las primeras 7 letras del cifrado da el shift exacto de inmediato.

# REFERENCIAS:
https://webshell.cylabacademy.org/
