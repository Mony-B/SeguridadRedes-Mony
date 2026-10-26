# DESCRIPCIÓN:
**vault-door-4** — Reverse Engineering (Medium) — by Mark E. Haase · picoCTF 2019

This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://challenge-files.cylabacademy.net/library/e8b3667853e7380d04e46c5b844bbad1cbd0855975b83213e23045054681c91d/VaultDoor4.java)

**Hints:**
1. Buscar una "tabla ASCII".
2. Saber la diferencia entre números octales, decimales y hexadecimales.

# SOLUCIÓN:
#### academy{jU5t_4_bUnCh_0f_bYt3s_136aaf3703}

El array `myBytes` mezcla literales en 3 bases distintas (decimal, hexadecimal `0x..` y octal `0...`) más algunos caracteres directos, y la contraseña debe coincidir byte a byte. Convertí cada valor a su carácter ASCII según su base:

- **Fila 1 (decimal):** `106,85,53,116,95,52,95,98` → `jU5t_4_b`
- **Fila 2 (hex `0x..`):** `0x55,0x6e,0x43,0x68,0x5f,0x30,0x66,0x5f` → `UnCh_0f_`
- **Fila 3 (octal `0..`):** `0142,0131,0164,063,0163,0137,061,063` → `bYt3s_13`
  (ej. `061` en octal = 6·8 + 1 = 49 = `1`)
- **Fila 4 (char literal):** `'6','a','a','f','3','7','0','3'` → `6aaf3703`

Concatenando las 4 filas: `jU5t_4_bUnCh_0f_bYt3s_136aaf3703`, que se lee "Just_4_bunch_0f_bytes_" + sufijo random. Ese es el password, envuelto en `academy{...}`.

# NOTAS ADICIONALES:
Clave para no perderse: un literal que empieza con `0x` es hexadecimal, uno que empieza con `0` (sin la `x`) y solo tiene dígitos 0-7 es octal, y cualquier otro número normal es decimal. Una vez identificada la base de cada literal, se convierte a decimal y ese valor es el código ASCII del carácter.

> **Nota:** la plataforma regenera el archivo (y el string/bytes de comparación) cada vez que lo vuelves a descargar — si el flag da "incorrecto", vuelve a bajar el `.java` antes de recalcular.

# REFERENCIAS:
https://webshell.cylabacademy.org/
