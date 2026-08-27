# DESCRIPCIÓN:
Can you crack the password to get the flag?

Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.

There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

# SOLUCIÓN:
#### picoCTF{m45h_fl1ng1ng_cd6ed2eb}

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/17/level3.py https://artifacts.picoctf.net/c/17/level3.flag.txt.enc https://artifacts.picoctf.net/c/17/level3.hash.bin
--2026-08-27 00:44:16--  https://artifacts.picoctf.net/c/17/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.226.187.66, 13.226.187.40, 13.226.187.37, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.226.187.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: ‘level3.py’

level3.py                                       100%[=====================================================================================================>]   1.31K  --.-KB/s    in 0.002s

2026-08-27 00:44:16 (840 KB/s) - ‘level3.py’ saved [1337/1337]

--2026-08-27 00:44:16--  https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
Reusing existing connection to artifacts.picoctf.net:443.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: ‘level3.flag.txt.enc’

level3.flag.txt.enc                             100%[=====================================================================================================>]      31  --.-KB/s    in 0s

2026-08-27 00:44:16 (16.1 MB/s) - ‘level3.flag.txt.enc’ saved [31/31]

--2026-08-27 00:44:16--  https://artifacts.picoctf.net/c/17/level3.hash.bin
Reusing existing connection to artifacts.picoctf.net:443.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: ‘level3.hash.bin’

level3.hash.bin                                 100%[=====================================================================================================>]      16  --.-KB/s    in 0s

2026-08-27 00:44:16 (7.25 MB/s) - ‘level3.hash.bin’ saved [16/16]

FINISHED --2026-08-27 00:44:16--
Total wall clock time: 0.5s
Downloaded: 3 files, 1.4K in 0.002s (868 KB/s)

mony@Mony:/mnt/c/Users/Usuario$ nano level3.py
mony@Mony:/mnt/c/Users/Usuario$ python3 level3.py
Please enter correct password for flag: 4dcf
That password is incorrect
mony@Mony:/mnt/c/Users/Usuario$ python3 level3.py
Please enter correct password for flag: f159
That password is incorrect
mony@Mony:/mnt/c/Users/Usuario$ python3 level3.py
Please enter correct password for flag: f09e
That password is incorrect
mony@Mony:/mnt/c/Users/Usuario$ python3 level3.py
Please enter correct password for flag: 3961
That password is incorrect
mony@Mony:/mnt/c/Users/Usuario$ python3 level3.py
Please enter correct password for flag: 752e
That password is incorrect
mony@Mony:/mnt/c/Users/Usuario$ python3 level3.py
Please enter correct password for flag: dba8
That password is incorrect
mony@Mony:/mnt/c/Users/Usuario$ python3 level3.py
Please enter correct password for flag: 87ab
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}
```
# NOTAS ADICIONALES:
Yo con el nano vi la lista de contraseñas y chequé una a una, peeero, también se puede con un "tail", el cual nos muestra las últimas 10 líneas de nuestro archivo, y como se mencionaba desde antes que estaban al final, pues evitamos usar el nano.

# REFERENCIAS:
https://webshell.cylabacademy.org/