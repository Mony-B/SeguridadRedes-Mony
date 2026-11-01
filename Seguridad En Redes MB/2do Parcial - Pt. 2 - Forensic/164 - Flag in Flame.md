# DESCRIPCIÓN:
**Flag in Flame** — Forensics (Easy) — by Prince Niyonshuti N. · picoMini by CMU-Africa

Dan un archivo de "logs" (`logs.txt`) que en realidad es un bloque enorme de texto codificado, no logs reales. El hint dice que hay que usar `base64` para decodificarlo y generar una imagen.

# SOLUCIÓN:
#### academy{forensics_analysis_is_amazing_2043dbd1}

1. El contenido de `logs.txt` empieza con `iVBORw0KGgo...`, que es la firma clásica de un **PNG codificado en Base64**.
2. Decodifiqué todo el archivo y lo guardé como imagen:
   ```python
   import base64
   data = open('logs.txt').read().strip()
   raw = base64.b64decode(data)
   open('flaginflame.png','wb').write(raw)
   ```
3. Al abrir la imagen resultante (una ilustración de un hacker frente a una laptop), al pie se ve un texto en **hexadecimal** escrito como parte de la imagen.
4. Hice zoom sobre esa franja para leer el hex con claridad y lo decodifiqué:
   ```python
   h = '61636164656D797B666F72656E736963735F616E616C797369735F69735F616D617A696E675F323034336462643137D'
   bytes.fromhex(h).decode()
   # academy{forensics_analysis_is_amazing_2043dbd1}
   ```

# NOTAS ADICIONALES:
El archivo pesaba ~1.6 MB de puro texto Base64 — no tenía caso abrirlo en un editor, directo a decodificar y ver qué salía. Al leer el hex a simple vista en la imagen hubo que tener cuidado con caracteres parecidos en la tipografía (como `6` vs `b`, o `4` vs un carácter mal zoomeado): conviene hacer varios recortes con zoom alto en vez de confiar en una sola lectura a simple vista, y validar decodificando — si el resultado no es ASCII limpio, algún carácter se leyó mal.

# REFERENCIAS:
https://webshell.cylabacademy.org/
