# DESCRIPCIÓN:
**Corrupted file** — Forensics (Easy) — by Yahaya Meddy · picoMini by CMU-Africa

Dan un archivo (`file`, sin extensión) que no abre con nada. El hint dice que es un JPEG y que hay que revisar el header con una herramienta como `xxd`/`hexdump`.

# SOLUCIÓN:
#### academy{r3st0r1ng_th3_by73s_69066302}

Con `xxd file | head` se ve el inicio de los bytes:
```
00000000: 5c78 ffe0 0010 4a46 4946 0001 0100 0001  \x....JFIF......
```
Un JPEG válido siempre empieza con la firma `FF D8 FF E0` (seguida de `JFIF`). Aquí los primeros dos bytes estaban cambiados: `5C 78` en vez de `FF D8` (curiosamente `5C 78` en ASCII es literalmente `\x`, como si alguien hubiera copiado mal un literal de bytes tipo `\xFF\xD8` y se hubiera quedado solo con el texto). El resto del header (`FF E0 ... JFIF`) ya estaba intacto.

Reparé los dos primeros bytes directamente:
```python
data = bytearray(open('file','rb').read())
data[0] = 0xFF
data[1] = 0xD8
open('file_fixed.jpg','wb').write(data)
```

Con eso el archivo ya abre como JPEG válido (800x500) y la imagen tiene la flag escrita como texto:
```
academy{r3st0r1ng_th3_by73s_69066302}
```

# NOTAS ADICIONALES:
No hizo falta reparar nada más del archivo — con corromper deliberadamente solo los primeros bytes de la firma (magic number), el resto de los datos JPEG sigue intacto y cualquier visor lo reconoce en cuanto el header vuelve a ser válido. Para este tipo de retos conviene memorizar los magic numbers más comunes: JPEG = `FF D8 FF`, PNG = `89 50 4E 47`, PDF = `25 50 44 46`, ZIP = `50 4B 03 04`, GIF = `47 49 46 38`.

# REFERENCIAS:
https://webshell.cylabacademy.org/
