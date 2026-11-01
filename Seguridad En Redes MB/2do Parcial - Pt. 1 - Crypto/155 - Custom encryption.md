# DESCRIPCIÓN:
**Custom encryption** — Cryptography (Medium) — by NGIRIMANA Schadrack · picoCTF 2024

Dan `custom_encryption.py` (el algoritmo de cifrado) y `enc_flag` (la salida de correr ese script). Hay que entender el algoritmo y escribir la función inversa.

# SOLUCIÓN:
#### academy{custom_d2cr0pt6d_203edf41}

`custom_encryption.py` hace esto con el mensaje:
1. `dynamic_xor_encrypt`: recorre el **texto invertido** (`plaintext[::-1]`) y hace XOR de cada carácter con la llave fija `"trudeau"` (repetida cíclicamente) → `semi_cipher`.
2. Un mini Diffie-Hellman de juguete con `p=97`, `g=31`: `a` y `b` aleatorios, `u=g^a mod p`, `v=g^b mod p`, llave compartida `key = v^a mod p`.
3. `encrypt`: por cada carácter del `semi_cipher`, calcula `ord(char) * key * 311` y lo mete en una lista `cipher`.

El `enc_flag` que corrieron viene con **`a` y `b` ya impresos en texto plano** (`a = 94`, `b = 22`) junto con la lista `cipher`. Con `a` y `b` conocidos, reconstruí la llave compartida sin tener que romper nada:

```python
p, g = 97, 31
a, b = 94, 22
u = pow(g, a) % p
v = pow(g, b) % p
key = pow(v, a) % p   # = 81, coincide con pow(u,b)%p

cipher = [226719, 1687797, ...]  # lista de enc_flag
semi = ''.join(chr(c // (key*311)) for c in cipher)   # revierte encrypt()

text_key = 'trudeau'
rev_plain = ''.join(chr(ord(ch) ^ ord(text_key[i % 7])) for i, ch in enumerate(semi))
plain = rev_plain[::-1]   # revierte el [::-1] de dynamic_xor_encrypt
print(plain)  # academy{custom_d2cr0pt6d_203edf41}
```

# NOTAS ADICIONALES:
El script tiene varias "capas" que suenan complicadas (DH de juguete, multiplicación por 311, XOR con texto invertido) pero ninguna es realmente fuerte: la multiplicación es trivialmente invertible con división entera, el XOR es simétrico, y el "secreto" de DH termina expuesto directo en el archivo de salida. La función `is_prime` además está rota (cuenta mal los divisores), aunque no afecta la solución porque `p=97` y `g=31` sí son primos de verdad.

# REFERENCIAS:
https://webshell.cylabacademy.org/
