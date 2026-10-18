# DESCRIPCIÓN:
Can you get the real meaning from this file? Nos dan un archivo descargable.

# SOLUCIÓN:
┌──(mony㉿Mony)-[~] └─$ cat enc_flag | base64 -d | base64 -d | tr 'A-Za-z' 'T-ZA-St-za-s'

# NOTAS ADICIONALES:
Este es un reto tipo "muñeca rusa" de codificaciones anidadas. Al leer el archivo, se observa la estructura típica de Base64. Al decodificarlo la primera vez, entrega otra cadena en Base64. Al decodificarla por segunda vez, arroja un texto cifrado con ROT/César clásico, el cual se rompió iterando el desplazamiento.

# REFERENCIAS:
https://webshell.cylabacademy.org/