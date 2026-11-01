# DESCRIPCIÓN:
**basic-mod2** — Cryptography (Medium) — by Will Hong · picoCTF 2022

Un reto de "modular arithmetic": dan un `message.txt` con una lista de números. Hay que tomar cada número mod 41, sacar el inverso modular de ese resultado (mod 41), y mapear el inverso a un carácter según el charset: 1-26 → alfabeto (a-z), 27-36 → dígitos (0-9), 37 → guion bajo `_`.

# SOLUCIÓN:
#### academy{1nv3r53ly_h4rd_fed0a735}

El mensaje descargado fue:
```
309 44 274 149 57 378 313 311 64 420 405 86 98 195 256 48 238 277 448 411 240 436 214
```

Para cada número `n` de la lista:
1. Calculé `m = n mod 41`.
2. Calculé el inverso modular de `m` módulo 41 (el `y` tal que `m*y ≡ 1 (mod 41)`), usando `pow(m, -1, 41)` en Python.
3. Mapeé ese inverso al charset dado (1→'a', 2→'b', ..., 26→'z', 27→'0', ..., 36→'9', 37→'_').

Script usado:
```python
nums = [309,44,274,149,57,378,313,311,64,420,405,86,98,195,256,48,238,277,448,411,240,436,214]
charset = {i: chr(ord('a')+i-1) for i in range(1,27)}
charset.update({i: str(i-27) for i in range(27,37)})
charset[37] = '_'

res = ''
for n in nums:
    m = n % 41
    inv = pow(m, -1, 41)
    res += charset[inv]
print(res)  # 1nv3r53ly_h4rd_fed0a735
```

Resultado: `1nv3r53ly_h4rd_fed0a735`, envuelto en `academy{...}`.

# NOTAS ADICIONALES:
Como 41 es primo, todo elemento no-cero módulo 41 tiene inverso, así que no hubo que preocuparse por casos sin solución. Python 3.8+ permite `pow(base, -1, mod)` directo para el inverso modular, sin tener que implementar el algoritmo extendido de Euclides a mano.

# REFERENCIAS:
https://webshell.cylabacademy.org/
