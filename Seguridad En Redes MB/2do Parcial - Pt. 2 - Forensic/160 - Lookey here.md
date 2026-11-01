# DESCRIPCIÓN:
**Lookey here** — Forensics (Medium) — by LT 'syreal' Jones / Mubarak Mikail · picoCTF 2022

Dan un archivo de texto enorme (`anthem.flag.txt`, el libro "Anthem" de Ayn Rand completo) y hay que encontrar una flag escondida en algún punto del texto, buscando por el prefijo conocido `academy{`.

# SOLUCIÓN:
#### academy{gr3p_15_@w3s0m3_375ef577}

Con el archivo completo de texto (~108 KB, el libro entero), busqué directamente el prefijo `academy{` con `grep`:

```bash
grep -ob "academy{" anthem.flag.txt
# 49999:academy{
```

Con el offset de byte encontrado, extraje el contenido a partir de ahí:
```bash
tail -c +49999 anthem.flag.txt | head -c 150
# academy{gr3p_15_@w3s0m3_375ef577}
```

# NOTAS ADICIONALES:
No hizo falta abrir el archivo completo ni revisarlo a ojo — con un texto tan largo, `grep -o` (o `-b` para ver también el offset en bytes) encuentra el patrón exacto al instante sin importar cuántas líneas tenga el archivo.

# REFERENCIAS:
https://webshell.cylabacademy.org/
