# DESCRIPCIÓN:
Can you win in a convincing manner against this chess bot? He won't go easy on you! You can find the challenge [here](http://xebec.cylabacademy.net:40363/).

Try understanding the code and how the websocket client is interacting with the server

# SOLUCIÓN:
#### academy{c1i3nt_s1d3_w3b_s0ck3t5_906748f0}

Para resolverlo, primero abrí la consola del navegador  para ver cómo se comunicaba el juego. Me di cuenta de que el servidor le pedía al navegador el puntaje de la partida y confiaba ciegamente en él. Entonces, le mandé el mensaje `sendMessage("eval -1000000")`.

Lo mandé porque el servidor no revisa si ese puntaje es real, simplemente se lo cree. Al recibir ese número, el bot pensó que iba perdiendo por un millón de puntos, se rindió solo y me dio la bandera.
![[Pasted image 20261004023201.png]]

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/