# DESCRIPCIÓN:
Can you crack the password to get the flag?

Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.

# SOLUCIÓN:
#### picoCTF{tr45h_51ng1ng_9701e681}

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/14/level2.py
--2026-08-27 00:37:03--  https://artifacts.picoctf.net/c/14/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.226.187.37, 13.226.187.22, 13.226.187.66, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: ‘level2.py’

level2.py                                       100%[=====================================================================================================>]     914  --.-KB/s    in 0.001s

2026-08-27 00:37:04 (866 KB/s) - ‘level2.py’ saved [914/914]

mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
--2026-08-27 00:37:13--  https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.226.187.37, 13.226.187.22, 13.226.187.66, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: ‘level2.flag.txt.enc’

level2.flag.txt.enc                             100%[=====================================================================================================>]      31  --.-KB/s    in 0s

2026-08-27 00:37:13 (19.4 MB/s) - ‘level2.flag.txt.enc’ saved [31/31]

mony@Mony:/mnt/c/Users/Usuario$ nano level2.py
mony@Mony:/mnt/c/Users/Usuario$ python3 level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}

Bueno,aquí en el nano vi que estaban los caracteres a convertir, lo hice con python, me dieorn la clave que era 4ec9 y listoo.
```

# NOTAS ADICIONALES:
- Siempre hay que estar pendientes a las conversiones, al parecer hay muchas.

# REFERENCIAS:
https://webshell.cylabacademy.org/