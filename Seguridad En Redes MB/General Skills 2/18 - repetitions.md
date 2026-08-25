# DESCRIPCIÓN:
Can you make sense of this file?

Download the file [here](https://artifacts.picoctf.net/c/477/enc_flag).
Multiple decoding is always good.

# SOLUCIÓN:
#### picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_de523f49}
Decodificamos y decodificamos hasta llegar a la solución, como si fuera una muñeca de esas que traen oootra muñeca adentro y así sucesivamente.

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/477/enc_flag
--2026-08-25 00:15:14--  https://artifacts.picoctf.net/c/477/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.238.132.49, 18.238.132.26, 18.238.132.115, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 349 [application/octet-stream]
Saving to: ‘enc_flag’

enc_flag                      100%[=================================================>]     349  --.-KB/s    in 0s

2026-08-25 00:15:14 (5.74 MB/s) - ‘enc_flag’ saved [349/349]

mony@Mony:/mnt/c/Users/Usuario$ cat enc_flag
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbHBWV0VKVVZGWmFWMDVHV2tkYVNHUlZDazFyY0ZkVWJGWlhZVlpLU0dWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==

mony@Mony:/mnt/c/Users/Usuario$ cat enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_de523f49}
```

# NOTAS ADICIONALES:
- si algo termina con ´´== , es porque es de codificación base64

# REFERENCIAS:
https://webshell.cylabacademy.org/
