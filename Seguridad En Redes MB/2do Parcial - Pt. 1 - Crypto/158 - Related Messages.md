# DESCRIPCIÓN:
**Related Messages** — Cryptography (Medium) — by Philip Thayer · picoCTF 2026

RSA clásico (e=17=0x11, módulo N de 2048 bits) pero el mismo remitente mandó **dos mensajes relacionados**: el original (con un typo) y uno corregido, cifrados con la misma llave. `chall.py` muestra que publican `ciphertext`, `ciphertext2`, la diferencia `Message - Message_fixed` (que es un número pequeño conocido, `-3`) y `N`. El hint apunta directo a "Franklin-Reiter related message attack".

# SOLUCIÓN:
#### academy{m3ssage_w1th_typ0}

El ataque de Franklin-Reiter explota que, si dos mensajes `M1, M2` están relacionados por una diferencia **conocida** (`M1 - M2 = diff`, aquí `diff = -3`) y se cifraron con el mismo `(N, e)`, se pueden construir dos polinomios sobre `Z_N[x]` que comparten como única raíz común el mensaje `M1`:

```
g1(x) = x^e - c1                  (raíz: x = M1)
h(x)  = (x - diff)^e - c2         (raíz: x = M1, porque M2 = M1 - diff)
```

El **gcd polinomial** de `g1` y `h` (calculado con el algoritmo de Euclides para polinomios, usando inversos modulares de los coeficientes líder mod N) da, si todo sale bien, un polinomio lineal `a1*x + a0`, de donde `M1 = -a0 * a1⁻¹ mod N`.

Implementé aritmética de polinomios (suma, resta, multiplicación, potencia, división con resto) mod N a mano en Python puro (sin librerías externas, porque la máquina no tenía salida a internet para instalar nada) y corrí el algoritmo de Euclides hasta llegar a un polinomio de grado 1:

```python
# (ver también el script completo guardado en el repo de la actividad)
g1 = [(-c1) % N] + [0]*(e-1) + [1]          # x^17 - c1
h  = poly_pow([(-diff) % N, 1], e, N)        # (x - diff)^17
h  = poly_sub(h, [c2 % N], N)                #            - c2

g = poly_gcd(g1, h, N)        # sale de grado 1
a0, a1 = g
M1 = (-a0 * pow(a1, -1, N)) % N
```

Esto recuperó `M1` (el mensaje **original, con el typo**):
```
M1 → b'academy{m3ssage_w1th_typ0z'   # nota la 'z' de más, sin cerrar llave
```

Como el enunciado deja claro que `M1` es el mensaje con el error, la flag real está en `Message_fixed = M1 - diff = M1 + 3`:
```python
M2 = (M1 + 3) % N
M2.to_bytes((M2.bit_length()+7)//8, 'big')
# b'academy{m3ssage_w1th_typ0}'
```

# NOTAS ADICIONALES:
`output.txt` venía con `ciphertext` y `ciphertext2` en líneas separadas (no en una sola línea separados por espacio, como se ve en el `print(ciphertext, ciphertext2)` del script fuente) — probablemente la plataforma reformatea el archivo al generarlo para descarga. Hubo que ajustar el parseo según el archivo real, no según el código fuente a ciegas.

# REFERENCIAS:
https://webshell.cylabacademy.org/
