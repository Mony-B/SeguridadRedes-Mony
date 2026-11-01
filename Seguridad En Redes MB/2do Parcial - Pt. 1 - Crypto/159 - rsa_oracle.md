# DESCRIPCIÓN:
**rsa_oracle** — Cryptography (Medium) — by Geoffrey Njogu · picoCTF 2024

Dan `secret.enc` (un mensaje cifrado con `openssl enc`, formato `Salted__...`) y `password.enc` (la contraseña usada para ese cifrado, pero cifrada con RSA). Hay un oráculo vivo por netcat (`E` para cifrar, `D` para descifrar) que descifra cualquier cosa **excepto** exactamente el ciphertext de la contraseña.

# SOLUCIÓN:
#### academy{su((3ss_(r@ck1ng_r3@_4263a53c}

Es un **ataque de texto cifrado elegido (CCA)** clásico sobre RSA: como RSA es multiplicativamente homomórfico, si `c = P^e mod n` es el ciphertext prohibido, puedo pedirle al oráculo que descifre `c' = c * k^e mod n` (para cualquier `k` que yo elija) — el oráculo no reconoce `c'` como la contraseña prohibida, y me devuelve `m' = k*P mod n`. Si `k*P < n` (sin "wraparound" del módulo), entonces `m' = k*P` exacto y despejo `P = m'/k` directo, sin necesitar saber `n`.

Pasos:
1. Usé la opción **E** del oráculo para cifrar textos cortos ("2","3","4","5") — el oráculo codifica el texto como hex de sus bytes ASCII y lo eleva a `e mod n`, dándome `s_k = E(k)` para `k = 50, 51, 52, 53` (los códigos ASCII de esos dígitos).
2. Por cada `k`, calculé `c' = c_password * s_k` (producto exacto, sin reducir mod n — el oráculo lo reduce solo al hacer `pow(c', d, n)`) y se lo mandé a **D**.
3. Los resultados para `k=51,52,53` (`m2,m3,m4`) resultaron estar en **progresión aritmética exacta** (`m3-m2 == m4-m3 == 224180712289`), lo que confirma que no hubo wraparound para esos `k` — y esa diferencia constante **es directamente la contraseña** en entero: `P = 224180712289`.
4. Verifiqué: `51 * 224180712289 == m2` ✓
5. Convertí `P` a bytes → contraseña real: **`4263a`**

```python
m2 = int('a6600cc3c53', 16)   # D(c * E(51))
m3 = int('a9a33026fb4', 16)   # D(c * E(52))
P = m3 - m2                    # = 224180712289, si no hubo wraparound
assert 51*P == m2
P.to_bytes((P.bit_length()+7)//8, 'big')  # b'4263a'
```

Con la contraseña (`4263a`) descifré `secret.enc` usando el modo **legacy** de `openssl enc` (sin `-pbkdf2`, que es el derivador de llave MD5 que usa por default una versión vieja de OpenSSL):
```bash
openssl enc -d -aes-256-cbc -in secret.enc -pass pass:4263a
# academy{su((3ss_(r@ck1ng_r3@_4263a53c}
```

# NOTAS ADICIONALES:
Mi primer intento con `k=50` salió mal porque transcribí mal el número `E(50)` del oráculo (me quedó 28 dígitos corto sin darme cuenta), lo que produjo un resultado basura de 512 bits y me hizo creer que la contraseña era del mismo tamaño que el módulo `n` — eso me llevó por un camino innecesariamente complicado (intentando resolver `n` con álgebra lineal sobre 3 ecuaciones). Al repetir con números recién copiados y comparar varios `k` consecutivos, la progresión aritmética hizo evidente que la contraseña era en realidad chiquita. Lección: con números tan largos pasados a mano por chat, conviene verificar la longitud de cada uno contra las demás antes de confiar en el resultado.

Con `openssl enc` moderno (`-pbkdf2`) la clave deriva distinto y da "bad decrypt" — el archivo se generó con el KDF legacy (hash MD5 de una sola pasada), así que hubo que omitir `-pbkdf2` a propósito.

# REFERENCIAS:
https://webshell.cylabacademy.org/
