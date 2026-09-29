# DESCRIPCIÓN:
We have several pages hidden. Can you find the one with the flag? The website is running [here](http://chatelaine.cylabacademy.net:36084/)
folders folders folders
# SOLUCIÓN:
#### academy{succ3ss_@h3n1c@10n_e77e3359}
Para resolver este reto, identificamos en el código fuente inicial que los recursos se cargaban desde un directorio llamado `/secret/`. A partir de ahí, realizamos una enumeración manual de carpetas expuestas, navegando por la ruta `/secret/hidden/` hasta llegar a `/secret/hidden/superhidden/`. Aunque esta última página parecía estar en blanco en el navegador, al inspeccionar el código fuente (`Ctrl + U`) descubrimos texto oculto en el HTML con el mensaje "can you see me" y la bandera.
Después de link tras link:
```
en: [chatelaine.cylabacademy.net:15449//secret/hidden/superhidden/](http://chatelaine.cylabacademy.net:15449//secret/hidden/superhidden/)

|   |
|---|
|<!DOCTYPE html>|
|<html>|
|<head>|
|<title></title>|
|<link rel="stylesheet" href="[mycss.css](http://chatelaine.cylabacademy.net:15449//secret/hidden/superhidden/mycss.css)" />|
|</head>|
||
|<body>|
|<h1>Finally. You found me. But can you see me</h1>|
|<h3 class="flag">academy{succ3ss_@h3n1c@10n_e77e3359}</h3>|
|</body>|
|</html>|
||
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/