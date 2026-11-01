# DESCRIPCIÓN:
**Timeline 0** — Forensics (Medium) — by LT 'syreal' Jones · picoCTF 2026

Dan una imagen de disco (`partition4.img.gz`) y hay que encontrar la flag dentro, envolviéndola en el formato `academy{}`. Los hints apuntan a crear una **MAC timeline con Sleuthkit** y buscar timestamps raros (muy viejos) de un "timestomping" descuidado.

# SOLUCIÓN:
#### academy{71m311n3_0u7113r_h3r_43a2e7af}

Herramientas usadas: **Sleuthkit** (`fls`, `mactime`, `icat`) — no venían instaladas en mi máquina ni se pudieron instalar sin internet completo, así que corrí todo en Kali Linux (que ya las trae).

1. Descomprimí la imagen y generé el "bodyfile" (listado de archivos con sus metadatos MAC — Modified/Accessed/Changed/Born):
   ```bash
   gunzip partition4.img.gz
   fls -r -m "/" partition4.img > body.txt
   mactime -b body.txt > timeline.txt
   ```
2. Revisé las entradas **más viejas** del timeline (mactime ordena cronológicamente, así que un timestomping sale hasta arriba del archivo):
   ```bash
   head -30 timeline.txt
   ```
   Y ahí salió el outlier evidente:
   ```
   Tue Jan 01 1985 11:00:00   41 macb r/rrw-r--r-- 0 0 4945  /bin/bcab
   ```
   — fecha absurda (1985), las **4 banderas MAC B** cambiadas al mismo tiempo (clásico de un timestomp hecho con una sola llamada que pisa las 4 marcas de tiempo a la vez), nombre de archivo sin sentido (`bcab`) y solo 41 bytes de tamaño, en medio de puros archivos de sistema normales.
3. Extraje el contenido de ese archivo por su número de inodo (4945):
   ```bash
   icat partition4.img 4945
   # NzFtMzExbjNfMHU3MTEzcl9oM3JfNDNhMmU3YWYK
   ```
4. Era Base64:
   ```python
   import base64
   base64.b64decode('NzFtMzExbjNfMHU3MTEzcl9oM3JfNDNhMmU3YWYK').decode()
   # 71m311n3_0u7113r_h3r_43a2e7af
   ```
5. El enunciado pide envolver lo encontrado en el formato de flag: `academy{71m311n3_0u7113r_h3r_43a2e7af}`.

# NOTAS ADICIONALES:
No hizo falta revisar todo el timeline a mano — con ordenarlo cronológicamente y mirar solo las primeras líneas, cualquier archivo con una fecha que no encaje con el resto del sistema (en este caso, 1985, cuando todo lo demás es 2021-2023) salta a la vista de inmediato.

# REFERENCIAS:
https://webshell.cylabacademy.org/
