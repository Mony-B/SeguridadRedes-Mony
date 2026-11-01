# DESCRIPCIÓN:
**Shared Secrets** — Cryptography (Easy) — by Yahaya Meddy · picoCTF 2026

Un intercambio de llaves tipo Diffie-Hellman donde "una parte filtró algo". Dan `message.txt` (con `g`, `p`, `A`, `b` y el mensaje cifrado `enc`) y `encryption.py` con la lógica de cifrado.

# SOLUCIÓN:
#### academy{dh_s3cr3t_5d9c8fbe}

Leyendo `encryption.py` se ve el intercambio DH clásico:
- Servidor tiene secreto `a`, público `A = g^a mod p`.
- Cliente tiene secreto `b`, público `B = g^b mod p`.
- Llave compartida: `shared = A^b mod p` (o equivalentemente `B^a mod p`).
- Cifra el flag con XOR byte a byte usando `shared % 256` como "llave" de un solo byte.

El descuido: en `message.txt` no solo viene la llave pública `A` del servidor, sino también **el secreto `b` del cliente** (que nunca debería hacerse público). Con `A` y `b` ya no hace falta romper el logaritmo discreto: calculas la llave compartida directo.

```python
g = 2
p = <primo de 1048 bits dado>
A = <dado>
b = <dado, es el secreto filtrado>
enc = bytes.fromhex(<dado>)

shared = pow(A, b, p)
key = shared % 256
flag = bytes([x ^ key for x in enc])
print(flag)  # b'academy{dh_s3cr3t_5d9c8fbe}'
```

# NOTAS ADICIONALES:
El cifrado real es débil de por sí (XOR con una sola llave de un byte repetida, ni siquiera un keystream), pero ni hizo falta explotar eso — bastó con que el secreto privado `b` se filtró en el archivo que se supone solo debía traer datos públicos.

# REFERENCIAS:
https://webshell.cylabacademy.org/
