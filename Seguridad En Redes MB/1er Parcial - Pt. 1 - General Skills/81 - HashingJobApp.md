# DESCRIPCIÓN:
If you want to hash with the best, beat this test! `nc chatelaine.cylabacademy.net 10484`

You can use a commandline tool or web app to hash text

Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

# SOLUCIÓN:
#### academy{4ppl1c4710n_r3c31v3d_467e06bf}

Primero, me conecté al puerto del reto con `nc chatelaine.cylabacademy.net 10484`. Ahí el sistema me empezó a dar varias frases entre comillas, una por una, y me pedía que las convirtiera a código MD5. Para resolverlo, abrí otra pestaña en mi terminal y usé el comando `echo -n "frase" | md5sum` para generar el código de la primera. Copié el resultado, lo pegué como respuesta y tuve que repetir este mismo proceso con las otras frases que me fue lanzando. Por último, al contestar todas las frases correctamente, el sistema me mostró la bandera en la pantalla.
```

┌──(mony㉿Mony)-[~]
└─$ nc chatelaine.cylabacademy.net 10484
Please md5 hash the text between quotes, excluding the quotes: 'bad dogs'
Answer:
Time's up. Press Ctrl-C to disconnect. Feel free to reconnect and try again.

┌──(mony㉿Mony)-[~]
└─$ nc chatelaine.cylabacademy.net 10484
Please md5 hash the text between quotes, excluding the quotes: 'alien abductions'
Answer:
089a281a0b59fe14b5e9d2472ffc5049
089a281a0b59fe14b5e9d2472ffc5049
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'Count Dracula'
Answer:
aff1b17cdcbc3b40afd42d5fe00297da
aff1b17cdcbc3b40afd42d5fe00297da
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'communists'
Answer:
60dc96cdf23898725b1f6862e99b5109
60dc96cdf23898725b1f6862e99b5109
Correct.
academy{4ppl1c4710n_r3c31v3d_467e06bf}

┌──(mony㉿Mony)-[~]
└─
```

```
┏━(Message from Kali developers)
┃
┃ This is a minimal installation of Kali Linux, you likely
┃ want to install supplementary tools. Learn how:
┃ ⇒ https://www.kali.org/docs/troubleshooting/common-minimum-setup/
┃
┗━(Run: “touch ~/.hushlogin” to hide this message)
┌──(mony㉿Mony)-[~]
└─$ echo -n "bad dogs" | md5sum
60cc96ffdc458c98395d6e7b6878a6e9  -

┌──(mony㉿Mony)-[~]
└─$ echo -n "alien abductions" | md5sum
089a281a0b59fe14b5e9d2472ffc5049  -

┌──(mony㉿Mony)-[~]
└─$ echo -n "Count Dracula" | md5sum
aff1b17cdcbc3b40afd42d5fe00297da  -

┌──(mony㉿Mony)-[~]
└─$ echo -n "communists" | md5sum
60dc96cdf23898725b1f6862e99b5109  -

```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/