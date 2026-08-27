# DESCRIPCIÓN:
Fix the syntax error in the Python script to print the flag.

PISTAAA:
Are equality and assignment the same symbol?

# SOLUCIÓN:
#### picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/5/fixme2.py
--2026-08-27 00:14:07--  https://artifacts.picoctf.net/c/5/fixme2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.157.173.39, 108.157.173.50, 108.157.173.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.157.173.39|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1029 (1.0K) [application/octet-stream]
Saving to: ‘fixme2.py’

fixme2.py                                       100%[=====================================================================================================>]   1.00K  --.-KB/s    in 0.002s

2026-08-27 00:14:07 (630 KB/s) - ‘fixme2.py’ saved [1029/1029]

mony@Mony:/mnt/c/Users/Usuario$ nano -l fixme2.py
mony@Mony:/mnt/c/Users/Usuario$ python3 fixme2.py
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}

El error estaba en la línea 22 porque el if estaba igualado, no asignado. O sea con doble igual.
```

# NOTAS ADICIONALES:
- No es lo mismo la igualdad (i=1) a la asignación(if : b== " ")

# REFERENCIAS:
https://webshell.cylabacademy.org/