# DESCRIPCIÓN:
This website puts a two-factor prompt between you and the flag. Register an account, then take a close look at the requests your browser is actually sending. Try [here](http://xebec.cylabacademy.net:38651/) to find the flag.
Hints:
Try using burpsuite to intercept request to capture the flag.
Try mangling the request, maybe their server-side code doesn't handle malformed requests very well.
# SOLUCIÓN:
#### academy{#0TP_Bypvss_SuCc3$S_007829ce}

La solución de este reto comienza llenando el registro. Al toparnos con la validación en dos pasos y no tener el código, usamos FoxyProxy y Burp Suite para interceptar la petición. La clave está en eliminar el parámetro `otp` de la solicitud al enviarla; esto genera un error en la página que nos entrega la bandera.

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/