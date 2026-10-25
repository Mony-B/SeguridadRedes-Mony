# DESCRIPCIÓN:
We received an encrypted message. The modulus is built from primes large enough that factoring them isn't an option, at least not today. See if you can make sense of the numbers and reveal the flag. Download the [message](https://challenge-files.cylabacademy.net/library/c85258d1bfc43eacb36ad1dad1f13f53e3bb9de78790da47f98669733ded9001/message.txt).

# SOLUCIÓN:
#### academy{t1ny_e_d9b985d8}

El archivo `message.txt` da un módulo RSA `n` de 4096 bits, `e = 20` y el cifrado `c`.

La clave: `c` tiene muchos menos bits que `n` (c < n), lo que significa que `m^e` **nunca dio la vuelta al módulo** — o sea `c = m^e` en los enteros, sin reducción mod n. No hace falta factorizar nada ni usar ataques de Coppersmith: basta sacar la raíz entera exacta de grado `e` de `c`.

```
┌──(mony㉿Mony)-[~/crypto]
└─$ python3
>>> def integer_nth_root(val, n_root):
...     low, high = 0, 1 << ((val.bit_length() + n_root - 1) // n_root + 1)
...     while low <= high:
...         mid = (low + high) // 2
...         p = mid ** n_root
...         if p == val: return mid, True
...         elif p < val: low = mid + 1
...         else: high = mid - 1
...     return high, False
>>> m, exact = integer_nth_root(c, e)
>>> m.to_bytes((m.bit_length()+7)//8, 'big')
b'academy{t1ny_e_d9b985d8}'
```

# NOTAS ADICIONALES:
Si el exponente público `e` es chico y el mensaje es corto, `m^e` puede quedar por debajo de `n` y entonces nunca se aplica el módulo — RSA se rompe sin tocar `n` para nada.

# REFERENCIAS:
https://en.wikipedia.org/wiki/RSA_(cryptosystem)#Attacks_against_plain_RSA
https://webshell.cylabacademy.org/
