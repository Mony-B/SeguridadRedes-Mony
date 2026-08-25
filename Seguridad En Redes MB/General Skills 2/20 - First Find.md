# DESCRIPCIÓN:
Unzip this archive and find the file named 'uber-secret.txt'

# SOLUCIÓN:
#### picoCTF{f1nd_15_f457_ab443fd1}

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/501/files.zip
--2026-08-25 00:54:53--  https://artifacts.picoctf.net/c/501/files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.226.187.22, 13.226.187.66, 13.226.187.40, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.226.187.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3995553 (3.8M) [application/octet-stream]
Saving to: ‘files.zip’

files.zip                     100%[=================================================>]   3.81M  4.67MB/s    in 0.8s

2026-08-25 00:54:55 (4.67 MB/s) - ‘files.zip’ saved [3995553/3995553]

mony@Mony:/mnt/c/Users/Usuario$ cd files

mony@Mony:/mnt/c/Users/Usuario/files$ grep -r "picoCTF"
adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt:picoCTF{f1nd_15_f457_ab443fd1}

```

# NOTAS ADICIONALES:
- nos ahorramos varias búsquedas al filtrarlo con el grep

# REFERENCIAS:
https://webshell.cylabacademy.org/
