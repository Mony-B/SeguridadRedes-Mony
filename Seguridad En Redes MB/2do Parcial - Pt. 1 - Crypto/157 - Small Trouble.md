# DESCRIPCIÓN:
**Small Trouble** — Cryptography (Medium) — by Yahaya Meddy · picoCTF 2026

RSA con módulo `n` de ~2096 bits, pero el exponente privado `d` se generó chico a propósito (`d = getPrime(256)`, un primo de solo 256 bits) y luego `e = inverse(d, phi)`. El hint apunta directo a "Boneh-Durfee" (ataque para exponente privado pequeño, válido cuando `d < n^0.292`).

# SOLUCIÓN:
#### academy{sm4ll_d_c0409804}

Con `d` de 256 bits y `n` de ~2096 bits, `d` cae claramente debajo del límite de Boneh-Durfee (y, por suerte, también dentro del alcance práctico del ataque de **Wiener** por fracciones continuas, mucho más simple de implementar sin librerías de lattice/LLL):

1. Calculé la fracción continua de `e/n` y sus convergentes `k/d_candidato`.
2. Para cada convergente probé si `phi = (e*d_candidato - 1) / k` es entero.
3. Con ese `phi` candidato, despejé `p + q = n - phi + 1` y el discriminante `(p+q)^2 - 4n`; si es un cuadrado perfecto, de ahí salen `p` y `q`.
4. Validé `p*q == n` — y sí cuadró, confirmando el `d` real.

```python
from math import isqrt

def continued_fraction(num, den):
    cf = []
    while den:
        q = num // den
        cf.append(q)
        num, den = den, num - q*den
    return cf

def convergents(cf):
    nums, dens = [], []
    for i, a in enumerate(cf):
        if i == 0: nums.append(a); dens.append(1)
        elif i == 1: nums.append(a*cf[0]+1); dens.append(a)
        else:
            nums.append(a*nums[-1]+nums[-2])
            dens.append(a*dens[-1]+dens[-2])
    return list(zip(nums, dens))

cf = continued_fraction(e, n)
for k, d in convergents(cf):
    if k == 0 or (e*d - 1) % k: continue
    phi = (e*d - 1)//k
    s = n - phi + 1
    disc = s*s - 4*n
    r = isqrt(disc) if disc >= 0 else -1
    if r*r == disc:
        p, q = (s+r)//2, (s-r)//2
        if p*q == n:
            print("d =", d); break

m = pow(c, d, n)
print(m.to_bytes((m.bit_length()+7)//8, 'big'))
# b'academy{sm4ll_d_c0409804}'
```

El `d` recuperado resultó ser de ~77 dígitos decimales (~256 bits), consistente con el `getPrime(256)` del script generador.

# NOTAS ADICIONALES:
No fue necesario montar el ataque Boneh-Durfee completo (que requiere reducción de lattice LLL, normalmente vía `sage` o `fpylll`, ninguno disponible sin internet en esta máquina). El ataque de Wiener, mucho más simple, ya alcanza casos con `d` hasta ~`n^0.25`; aquí `d` (256 bits) resultó estar dentro de ese rango más generoso de lo esperado, así que no hizo falta ir a la herramienta más pesada que sugería el hint.

# REFERENCIAS:
https://webshell.cylabacademy.org/
