# DESCRIPCIÓN:
Can you crack the password to get the flag?

Download the password checker [here](https://artifacts.picoctf.net/c/11/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/11/level1.flag.txt.enc) in the same directory too.

# SOLUCIÓN:
#### picoCTF{545h_r1ng1ng_fa343060}

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/11/level1.py
--2026-08-27 00:23:16--  https://artifacts.picoctf.net/c/11/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.157.173.50, 108.157.173.39, 108.157.173.76, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.157.173.50|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: ‘level1.py’

level1.py                                       100%[=====================================================================================================>]     876  --.-KB/s    in 0s

2026-08-27 00:23:17 (13.6 MB/s) - ‘level1.py’ saved [876/876]

mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/11/level1.flag.txt.enc
--2026-08-27 00:23:27--  https://artifacts.picoctf.net/c/11/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.157.173.50, 108.157.173.39, 108.157.173.76, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.157.173.50|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: ‘level1.flag.txt.enc’

level1.flag.txt.enc                             100%[=====================================================================================================>]      30  --.-KB/s    in 0s

2026-08-27 00:23:27 (20.1 MB/s) - ‘level1.flag.txt.enc’ saved [30/30]

mony@Mony:/mnt/c/Users/Usuario$ nano level1.py

mony@Mony:/mnt/c/Users/Usuario$ python3 level1.py
Please enter correct password for flag: 1e1a
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_fa343060}


Bueno, aquí fue ver la función y descubrir la clave solo poniendo atención.
```

# NOTAS ADICIONALES:
- A veces hay que revisar el, código y revisar su lógica para entender de donde se puede obtener la bandera :/

# REFERENCIAS:
https://webshell.cylabacademy.org/