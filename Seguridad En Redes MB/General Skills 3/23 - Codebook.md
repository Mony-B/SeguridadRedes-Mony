# DESCRIPCIÓN:
Run the Python script `code.py` in the same directory as `codebook.txt`.

# SOLUCIÓN:
#### picoCTF{c0d3b00k_455157_d9aa2df2}

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/1/code.py
--2026-08-26 23:44:47--  https://artifacts.picoctf.net/c/1/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.157.173.76, 108.157.173.39, 108.157.173.50, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.157.173.76|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: ‘code.py.1’

code.py.1         100%[=============>]   1.25K  --.-KB/s    in 0s

2026-08-26 23:44:48 (32.4 MB/s) - ‘code.py.1’ saved [1278/1278]

mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/1/codebook.txt
--2026-08-26 23:44:54--  https://artifacts.picoctf.net/c/1/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.157.173.76, 108.157.173.39, 108.157.173.50, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.157.173.76|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: ‘codebook.txt.1’

codebook.txt.1    100%[=============>]      27  --.-KB/s    in 0s

2026-08-26 23:44:54 (482 KB/s) - ‘codebook.txt.1’ saved [27/27]

mony@Mony:/mnt/c/Users/Usuario$ cat codebook.txt
azbycxdwevfugthsirjqkplomn
mony@Mony:/mnt/c/Users/Usuario$ python3 code.py
picoCTF{c0d3b00k_455157_d9aa2df2}
```

# NOTAS ADICIONALES:
- Algunos script al ejecutarse es posible que requieran la existencia de otros archivos para poder trabajar
- Nano - es un editor de texto en Linux y para salir de ese editor se usa Ctrl +x


# REFERENCIAS:
https://webshell.cylabacademy.org/