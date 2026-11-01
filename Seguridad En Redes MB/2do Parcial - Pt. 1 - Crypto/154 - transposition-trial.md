# DESCRIPCIÓN:
**transposition-trial** — Cryptography (Medium) — by Will Hong · picoCTF 2022

Un `message.txt` corrupto: nada se reemplazó, pero cada bloque de 3 caracteres quedó revuelto (misma permutación en todos los bloques). Dan como pista que la primera palabra del mensaje original tiene 3 letras.

# SOLUCIÓN:
#### academy{7R4N5P051N6_15_3XP3N51V3_27F6D45C}

El mensaje cifrado (54 caracteres, múltiplo de 3) era:
```
heTfl g as icaaemd{7y4NRP051N5_16_35P3X51N3_V7F2D46C}5
```

1. El primer bloque de 3 es `heT`. Si la primera palabra del texto plano es de 3 letras, lo más razonable en una oración en inglés es que empiece con `"The"` (mayúscula inicial, artículo común).
2. Comparando `"The"` (plano) contra `"heT"` (cifrado) deduje la permutación: `cifrado[0]=plano[1]`, `cifrado[1]=plano[2]`, `cifrado[2]=plano[0]` — es decir, cada bloque se rota un lugar a la izquierda al cifrar. Para descifrar, cada bloque `[c0,c1,c2]` se reordena como `[c2,c0,c1]`.
3. Apliqué esa misma rotación a los 18 bloques de 3 caracteres de todo el mensaje:

```python
s = open('message.txt').read().strip('\n')
out = []
for i in range(0, len(s), 3):
    b = s[i:i+3]
    out.append(b[2] + b[0] + b[1])
print(''.join(out))
# The flag is academy{7R4N5P051N6_15_3XP3N51V3_27F6D45C}
```

# NOTAS ADICIONALES:
No fue necesario probar las 6 permutaciones posibles de un bloque de 3 (3! = 6) por fuerza bruta: con un solo bloque conocido (la palabra de 3 letras) se despeja la permutación exacta y se aplica igual a todo el resto, porque el enunciado aclara que es la misma revoltura en cada bloque.

# REFERENCIAS:
https://webshell.cylabacademy.org/
