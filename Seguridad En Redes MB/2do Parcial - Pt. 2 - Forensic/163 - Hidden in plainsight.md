# DESCRIPCIÓN:
**Hidden in plainsight** — Forensics (Easy) — by Yahaya Meddy · picoMini by CMU-Africa

Dan una imagen JPG (`img.jpg`) con algo escondido dentro del archivo (esteganografía). El hint dice que hay que revisar la metadata.

# SOLUCIÓN:
#### academy{h1dd3n_1n_1m4g3_71ae1957}

1. Con `file img.jpg` salió en el comentario JPEG (segmento COM) un string en Base64: `c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9`.
2. Decodifiqué ese Base64:
   ```python
   import base64
   base64.b64decode('c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9').decode()
   # 'steghide:cEF6endvcmQ='
   ```
   Esto dice literalmente **"steghide"** (la herramienta a usar) seguido de otro Base64.
3. Decodifiqué ese segundo Base64 también:
   ```python
   base64.b64decode('cEF6endvcmQ=').decode()
   # 'pAzzword'
   ```
   Esa es la contraseña del `steghide`.
4. Con la contraseña, extraje el contenido oculto de la imagen usando `steghide` (herramienta de esteganografía, no venía instalada en mi máquina así que lo corrí en la webshell de la plataforma):
   ```bash
   steghide extract -sf img.jpg -p pAzzword
   # wrote extracted data to "flag.txt".
   cat flag.txt
   # academy{h1dd3n_1n_1m4g3_71ae1957}
   ```

# NOTAS ADICIONALES:
El comentario JPEG venía con **dos capas de Base64 anidadas**: la primera decodifica a `steghide:<base64>`, indicando qué herramienta usar, y la segunda es la contraseña real de esa herramienta. `steghide` esconde datos modificando los coeficientes DCT de la imagen JPEG de forma que el archivo visualmente no cambia, pero el payload solo se puede recuperar sabiendo la contraseña correcta.

# REFERENCIAS:
https://webshell.cylabacademy.org/
