# DESCRIPCIÓN:

# SOLUCIÓN:
#### academy{4p0110_1n_7h3_h0us3_d6af8f37}

Primero, usé el comando `wget` poniendo los tres enlaces separados por un espacio para descargar todos los archivos juntos (el script de Python, el texto con la contraseña y el archivo de la bandera). Después, usé el comando `cat password.txt` para leer la contraseña que venía guardada y la copié. Luego, ejecuté el programa en la terminal con el comando `python3 ende.py -d flag.txt.en` para decirle que quería desencriptar el archivo. Por último, cuando el programa me pidió la contraseña, pegué la que había copiado antes y ahí me mostró la bandera en la pantalla.
 ```
 ┌──(mony㉿Mony)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/617105c28abc79cef2487b00e5d07503f2b87fd29687ee960e7abe3a30294c8b/flag.txt.en https://challenge-files.cylabacademy.net/library/617105c28abc79cef2487b00e5d07503f2b87fd29687ee960e7abe3a30294c8b/password.txt https://challenge-files.cylabacademy.net/library/617105c28abc79cef2487b00e5d07503f2b87fd29687ee960e7abe3a30294c8b/ende.py
--2026-10-03 22:37:34--  https://challenge-files.cylabacademy.net/library/617105c28abc79cef2487b00e5d07503f2b87fd29687ee960e7abe3a30294c8b/flag.txt.en
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 13.226.187.40, 13.226.187.22, 13.226.187.37, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 140 [application/octet-stream]
Saving to: ‘flag.txt.en’

flag.txt.en                          100%[======================================================================>]     140  --.-KB/s    in 0s

2026-10-03 22:37:35 (1.26 MB/s) - ‘flag.txt.en’ saved [140/140]

--2026-10-03 22:37:35--  https://challenge-files.cylabacademy.net/library/617105c28abc79cef2487b00e5d07503f2b87fd29687ee960e7abe3a30294c8b/password.txt
Reusing existing connection to challenge-files.cylabacademy.net:443.
HTTP request sent, awaiting response... 200 OK
Length: 33 [application/octet-stream]
Saving to: ‘password.txt’

password.txt                         100%[======================================================================>]      33  --.-KB/s    in 0s

2026-10-03 22:37:35 (385 KB/s) - ‘password.txt’ saved [33/33]

--2026-10-03 22:37:35--  https://challenge-files.cylabacademy.net/library/617105c28abc79cef2487b00e5d07503f2b87fd29687ee960e7abe3a30294c8b/ende.py
Reusing existing connection to challenge-files.cylabacademy.net:443.
HTTP request sent, awaiting response... 200 OK
Length: 1328 (1.3K) [application/octet-stream]
Saving to: ‘ende.py’

ende.py                              100%[======================================================================>]   1.30K  --.-KB/s    in 0s

2026-10-03 22:37:35 (14.6 MB/s) - ‘ende.py’ saved [1328/1328]

FINISHED --2026-10-03 22:37:35--
Total wall clock time: 0.9s
Downloaded: 3 files, 1.5K in 0s (5.18 MB/s)

┌──(mony㉿Mony)-[~]
└─$ cat password.txt
563e47ddeaf84eca8b2a31201381a898

┌──(mony㉿Mony)-[~]
└─$ python3 ende.py -d flag.txt.en
Please enter the password:563e47ddeaf84eca8b2a31201381a898
academy{4p0110_1n_7h3_h0us3_d6af8f37}
 ```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/