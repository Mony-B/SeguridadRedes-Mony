# DESCRIPCIÓN:
**DISKO 4** — Forensics (Medium) — by Darkraicg492 · picoCTF 2026

Dan una imagen de disco (`disko-4.dd.gz`) donde el atacante **borró el archivo** con la flag. Hay que recuperarlo.

# SOLUCIÓN:
#### academy{d3l_d0n7_h1d3_w3ll_f564c3ef}

1. Descomprimí la imagen y listé solo los archivos **borrados** con Sleuthkit (`fls -r -d` = recursivo, solo eliminados):
   ```bash
   gunzip disko-4.dd.gz
   fls -r -d disko-4.dd
   ```
   Resultado:
   ```
   r/r * 522629:   log/messages
   r/r * 532021:   log/dont-delete.gz
   ```
   El segundo (`log/dont-delete.gz`) tiene un nombre bastante irónico para algo que sí se borró — claramente el candidato.

2. Recuperé su contenido por número de inodo con `icat` y lo descomprimí:
   ```bash
   icat disko-4.dd 532021 > dont-delete.gz
   gunzip dont-delete.gz
   cat dont-delete
   # Here is your flag
   # academy{d3l_d0n7_h1d3_w3ll_f564c3ef}
   ```

# NOTAS ADICIONALES:
Borrar un archivo en un sistema de archivos tipo ext no destruye su contenido de inmediato — solo marca el inodo como libre/disponible para reutilizar. Mientras ese espacio no se sobreescriba con datos nuevos, `fls -d` lo sigue listando (marcado con `*`) y `icat` puede leer su contenido directo por número de inodo, igual que con un archivo "vivo".

# REFERENCIAS:
https://webshell.cylabacademy.org/
