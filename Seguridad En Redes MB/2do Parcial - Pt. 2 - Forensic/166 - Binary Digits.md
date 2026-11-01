# DESCRIPCIÓN:
**Binary Digits** — Forensics (Easy) — by Yahaya Meddy · picoCTF 2026

Dan un archivo `digits.bin` que es puro texto de 1s y 0s (71,424 caracteres). Hay que recuperar algo significativo de ahí.

# SOLUCIÓN:
#### academy{h1dd3n_1n_th3_b1n4ry_fd12019b}

El archivo es una cadena binaria (múltiplo exacto de 8 bits = 8928 bytes). La convertí de binario a bytes:

```python
bits = open('digits.bin').read().strip()
b = int(bits, 2).to_bytes(len(bits)//8, 'big')
open('digits_decoded.bin','wb').write(b)
```

Los primeros bytes resultantes fueron `ff d8 ff e0 ... JFIF` — firma de un **JPEG**. Renombré a `.jpg` y al abrirlo, la imagen (texto en rojo sobre fondo blanco, igual al patrón de otros retos de esta tanda) tenía la flag escrita directo:
```
academy{h1dd3n_1n_th3_b1n4ry_fd12019b}
```

# NOTAS ADICIONALES:
Mismo patrón que **Corrupted file** y **Flag in Flame**: datos de una imagen disfrazados en otra codificación (binario, hex, Base64). En cuanto se reconoce la firma `FF D8 FF E0` + `JFIF` tras decodificar, ya se sabe que es cuestión de guardar los bytes con extensión `.jpg` y abrir la imagen.

# REFERENCIAS:
https://webshell.cylabacademy.org/
