# DESCRIPCIÓN:
Run the Python script and convert the given number from decimal to binary to get the flag.

# SOLUCIÓN:
#### picoCTF{4ll_y0ur_b4535_9c3b7d4d}

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/23/
convertme.py
--2026-08-26 23:47:46--  https://artifacts.picoctf.net/c/23/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.238.132.115, 18.238.132.26, 18.238.132.49, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: ‘convertme.py’

convertme.py      100%[=============>]   1.16K  --.-KB/s    in 0.001s

2026-08-26 23:47:46 (827 KB/s) - ‘convertme.py’ saved [1189/1189]

mony@Mony:/mnt/c/Users/Usuario$ python3 convertme.py
If 22 is in decimal base, what is it in binary base?
Answer: 0b10110
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}


PS C:\Users\Usuario> python
Python 3.12.6 (tags/v3.12.6:a4a2d2b, Sep  6 2024, 20:11:23) [MSC v.1940 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(22)
'0b10110'
>>>

```

# NOTAS ADICIONALES:
En Python convertimos de Decimal a Binario sin necesidad de otros programas.

# REFERENCIAS:
https://webshell.cylabacademy.org/