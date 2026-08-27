# DESCRIPCIÓN:
Fix the syntax error in this Python script to print the flag.

# SOLUCIÓN:
#### picoCTF{1nd3nt1ty_cr1515_182342f7}

```
mony@Mony:/mnt/c/Users/Usuario$ python3 fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/23/convertme.py
--2026-08-27 00:10:10--  https://artifacts.picoctf.net/c/23/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.157.173.76, 108.157.173.50, 108.157.173.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.157.173.76|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: ‘convertme.py.1’

convertme.py.1                                  100%[=====================================================================================================>]   1.16K  --.-KB/s    in 0.001s

2026-08-27 00:10:11 (1.07 MB/s) - ‘convertme.py.1’ saved [1189/1189]

mony@Mony:/mnt/c/Users/Usuario$
mony@Mony:/mnt/c/Users/Usuario$ nano -l fixme1.py
mony@Mony:/mnt/c/Users/Usuario$ python3 fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}

En el editor de nano corregimos los espacios innecesarios en el último print.
```

# NOTAS ADICIONALES:
- La indentación es muy importante en Python, bueno, la sintaxis en general y por eso no funcionan los programas.
- Nano -l abre el archivo en el editor y muestra los números de líneas de code.

# REFERENCIAS:
https://webshell.cylabacademy.org/