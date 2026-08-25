# DESCRIPCIÓN:
What does this bDNhcm5fdGgzX3IwcDM1 mean? I think it has something to do with bases.

# SOLUCIÓN:
#### picoCTF{l3arn_th3_r0p35}
```
>>> import base64
>>> base64.b64decode("bDNhcm5fdGgzX3IwcDM1")
b'l3arn_th3_r0p35'
>>>
```

# NOTAS ADICIONALES:
- 'Base64' convierte datos, texto o cosas complejas en texto plano.

# REFERENCIAS:
https://webshell.cylabacademy.org/