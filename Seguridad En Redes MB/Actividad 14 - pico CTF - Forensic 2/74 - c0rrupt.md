# DESCRIPCIÓN:

# SOLUCIÓN:
#### academy{c0rrupt10n_1847995}

Instalamos `pngcheck` para validar la estructura del PNG:

```
sudo apt install pngcheck
```

Ejecutamos el análisis para detectar la corrupción en la imagen:

```
pngcheck -v mystery
```

El reto consiste en reparar el archivo editando y estableciendo correctamente los nombres de cada _chunk_. Una vez corregidos los valores, basta con abrir la imagen para revelar la bandera:


```
open mystery
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/