# DESCRIPCIÓN:
**Timestamped Secrets** — Cryptography (Medium) — by Yahaya Meddy · picoCTF 2026

Mensaje cifrado con AES en modo ECB, pero la llave se deriva de un timestamp (hora actual del cifrado). Dan `message.txt` con el ciphertext y un hint del timestamp aproximado, más `encryption.py` (versión redactada) que muestra la lógica.

# SOLUCIÓN:
#### academy{sa3S_sEc9t_f9ccd007}

`encryption.py` muestra que la llave AES-128 se deriva así:
```python
key = sha256(str(timestamp).encode()).digest()[:16]
cipher = AES.new(key, AES.MODE_ECB)
```
y el `message.txt` daba:
```
Hint: The encryption was done around 1790147509 UTC
Ciphertext (hex): e24b9c357ad38df368104cc83fd235607bdac8f0f83123b38a89f459e46a3db2
```

Como el timestamp es un entero pequeño y conocido aproximadamente, se puede fuerza-brutear un rango de segundos alrededor del valor dado, derivar la llave SHA-256 para cada candidato, e intentar descifrar con AES-128-ECB hasta encontrar un resultado que contenga `academy{`.

```python
import hashlib, subprocess

ct = bytes.fromhex('e24b9c357ad38df368104cc83fd235607bdac8f0f83123b38a89f459e46a3db2')
open('ct.bin','wb').write(ct)

base = 1790147509
for ts in range(base-120, base+120):
    key = hashlib.sha256(str(ts).encode()).digest()[:16]
    out = subprocess.run(['openssl','enc','-aes-128-ecb','-d','-K',key.hex(),'-in','ct.bin'],
                          capture_output=True)
    if out.returncode == 0 and b'academy{' in out.stdout:
        print(ts, out.stdout)
        break
# 1790147509 b'academy{sa3S_sEc9t_f9ccd007}'
```

En este caso el propio timestamp del hint (`1790147509`) ya era el exacto, sin necesidad de probar otros valores del rango.

# NOTAS ADICIONALES:
Usé `openssl enc -aes-128-ecb -d` en vez de `pycryptodome` porque la máquina no tenía salida a internet para instalar la librería — `openssl` ya viene preinstalado y hace el mismo trabajo desde la línea de comandos. El modo ECB no necesita IV, lo que simplifica el brute-force (no hay que adivinar también un vector de inicialización).

# REFERENCIAS:
https://webshell.cylabacademy.org/
