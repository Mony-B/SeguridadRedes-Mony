# DESCRIPCIÓN:
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.

# SOLUCIÓN:
#### picoCTF{run_s4n1ty_run}

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/34/runme.py
--2026-08-26 23:38:25--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.157.173.50, 108.157.173.42, 108.157.173.39, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.157.173.50|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: ‘runme.py’

runme.py          100%[=============>]     270  --.-KB/s    in 0s

2026-08-26 23:38:25 (104 MB/s) - ‘runme.py’ saved [270/270]

mony@Mony:/mnt/c/Users/Usuario$ python3 runme.py
picoCTF{run_s4n1ty_run}
```

# NOTAS ADICIONALES:
- Seguimos con wget :)

# REFERENCIAS:
https://webshell.cylabacademy.org/