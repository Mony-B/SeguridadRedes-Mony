# DESCRIPCIÓN:
This service provides you an encrypted flag. Can you decrypt it with just N & e? Connect to the program with netcat:
`$ nc chatelaine.cylabacademy.net <puerto>`
El código fuente (`encrypt.py`) también se puede descargar desde la página del reto.

# SOLUCIÓN:
#### academy{tw0_1$_pr!m3cfb893a9}

El servicio entrega `N`, `e=65537` y el cifrado `c`. El hint 2 pregunta "¿algo interesante sobre N?" — y efectivamente, **N es par**. Si N es par, uno de sus factores primos es 2, así que la factorización es trivial y no hace falta romper nada "de verdad":

```
┌──(mony㉿Mony)-[~]
└─$ nc xebec.cylabacademy.net 18727
N: 14950734937165157753005877161454882854881707046524364056645819778273206753528699553602326006000506216567855496702100498911815628181381632998317773331350894
e: 65537
cyphertext: 2829618467733724263179180966330360226308930978905477224798251836327462100502101315001780289839021104797836409664919458484491824666076359486305222778808183

┌──(mony㉿Mony)-[~]
└─$ python3
>>> N % 2
0
>>> p, q = 2, N // 2
>>> phi = (p-1)*(q-1)        # = q - 1
>>> d = pow(e, -1, phi)
>>> m = pow(c, d, N)
>>> m.to_bytes((m.bit_length()+7)//8, 'big')
b'academy{tw0_1$_pr!m3cfb893a9}'
```

# NOTAS ADICIONALES:
RSA solo es seguro si N = p·q con p y q primos grandes y secretos. Si por mala generación de aleatoriedad uno de los primos resulta ser 2 (par), factorizar N es instantáneo y toda la seguridad se cae — justo lo que insinúa el nombre del reto ("Even RSA").

# REFERENCIAS:
https://webshell.cylabacademy.org/
