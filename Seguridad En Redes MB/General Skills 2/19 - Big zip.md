# DESCRIPCIÓN:
Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/505/big-zip-files.zip)
Can grep be instructed to look at every file in a directory and its subdirectories?
# SOLUCIÓN:
####  picoCTF{gr3p_15_m4g1c_ef8790dc}

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/505/big-zip-files.zip
--2026-08-25 00:51:25--  https://artifacts.picoctf.net/c/505/big-zip-files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.226.187.40, 13.226.187.37, 13.226.187.22, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.226.187.40|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3182988 (3.0M) [application/octet-stream]
Saving to: ‘big-zip-files.zip’

big-zip-files.zip          100%[=================================================>]   3.04M  4.30MB/s    in 0.7s

2026-08-25 00:51:26 (4.30 MB/s) - ‘big-zip-files.zip’ saved [3182988/3182988]

mony@Mony:/mnt/c/Users/Usuario$ unzip -q big-zip-files.zip

mony@Mony:/mnt/c/Users/Usuario$ grep -r "picoCTF" big-zip-files/
big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}

```


# NOTAS ADICIONALES:
- unzip -q - sirve para descomprimir sin mostrar todo

# REFERENCIAS:
https://webshell.cylabacademy.org/
