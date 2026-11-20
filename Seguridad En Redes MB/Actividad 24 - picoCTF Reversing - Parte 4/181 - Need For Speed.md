# DESCRIPCIÓN:
The name of the game is speed. Are you quick enough to solve this problem and keep it above 50 mph?
Hint: ¿Cuál es la key final?

# SOLUCIÓN:
#### academy{Good job keeping bus #31b86b76 speeding along!}

El binario simula que hay que "ser rápido" (referencia a la película *Speed*), pero es una trampa: si solo lo ejecutas y esperas, el programa de verdad tarda muchísimo en "calcular la llave" y el `alarm()` de 1 segundo lo mata antes ("Not fast enough. BOOM!"). La solución es por análisis estático, sin ejecutar el programa:

1. Desensamblar `calculate_key`:
   - Pone `key = 0xbe9139d0` y lo va decrementando en un loop hasta que vuelve a valer `0xdf489ce8` (esto tarda muchísimo por el wraparound de 32 bits, de ahí la "lentitud" simulada).
   - Esto se repite 8 veces, pero cada vez el resultado final del loop interno es el mismo: `0xdf489ce8`.
   - Es decir, **la key siempre es la misma constante: `0xdf489ce8`**, sin importar el tiempo. No depende de nada dinámico.

2. Desensamblar `decrypt_flag(key)`:
   - Recorre el arreglo cifrado `flag` (55 bytes, símbolo en `.data`, offset 0x4020) byte por byte (`i` de 0 a 54).
   - Para cada byte `i`: usa el byte 0 de `key` si `i` es par, o el byte 1 de `key` si `i` es impar (little-endian), y hace XOR con `flag[i]`.
   - Cada vez que `i % 3 == 2`, `key` se incrementa en 1.

3. Extraer los 55 bytes cifrados de la sección `.data` del binario (con `objdump -s -j .data`) y replicar el algoritmo en Python:
```python
flag_bytes = bytes.fromhex("89ff89f88cf193e7adf384f8ccf683fecdf78bf99ef581fbd0fe85efd1bfc1ad90a4c5fec3aad4ef85f993f89ff290bc99f097f29ebd87")
key = 0xdf489ce8
out = bytearray(flag_bytes)
for i in range(55):
    kb = key & 0xFF if i % 2 == 0 else (key >> 8) & 0xFF
    out[i] ^= kb
    if i % 3 == 2:
        key += 1
print(out.decode())
# academy{Good job keeping bus #31b86b76 speeding along!}
```

# NOTAS ADICIONALES:
No es necesario correr el binario ni ganarle la carrera al `alarm()`: toda la "velocidad" es humo, el valor de la key es una constante fija que se puede deducir leyendo el ensamblador de `calculate_key`. El hint ("¿Cuál es la key final?") apunta directo a esto.

# REFERENCIAS:
N/A
