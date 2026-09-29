# DESCRIPCIÓN:
Do you know how to use the web inspector?

Use the web inspector on other files included by the web page.
The flag may or may not be encoded
# SOLUCIÓN:
#### academy{web_succ3ssfully_d3c0ded_e0ea179a}

Siguiendo la pista proporcionada, procedimos a inspeccionar el código fuente de los archivos secundarios de la página web. Al revisar el archivo `about.html`, detectamos un atributo no estándar llamado `notify_true` dentro de una etiqueta `<section>`. El valor asignado a este atributo era una cadena de texto codificada en Base64 (`YWNh...`). Al decodificar dicho valor, logramos obtener la bandera del reto. 

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/