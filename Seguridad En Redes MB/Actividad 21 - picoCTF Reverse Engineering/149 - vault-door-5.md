# DESCRIPCIÓN:
**vault-door-5** — Reverse Engineering (Medium) — by Mark E. Haase · picoCTF 2019

Minion #7781 used base 8 and base 16, but this is base 64, which is like... eight times stronger, right? La fuente usa `URLDecoder`/URL-encoding y `Base64`.

# SOLUCIÓN:
#### academy{c0nv3rt1ng_fr0m_ba5e_64_75865cc3}

Aquí `checkPassword` no compara el password directo: primero le hace **URL-encode** (cada byte → `%XX` en hex) y luego **Base64-encode** al resultado, y compara eso contra un string Base64 fijo. Para sacar el password hay que deshacer el proceso al revés:

1. Tomé el string Base64 (`expected`) y lo decodifiqué (Base64 → texto plano). Da como resultado algo tipo `%63%30%6e%76%33...`, puro URL-encoding.
2. Cada grupo de 3 caracteres `%XX` es un byte en hexadecimal — lo convertí a su carácter ASCII (ej. `%63` = `0x63` = `c`).
3. Uniendo los 32 caracteres resultantes se arma el password: `c0nv3rt1ng_fr0m_ba5e_64_75865cc3`, que en leetspeak es "converting_from_base_64_" + sufijo random.

Ese es el password, envuelto en `academy{...}`.

# NOTAS ADICIONALES:
Es el mismo truco que vault-door-4 (disfrazar texto con otra codificación) pero con doble capa: primero URL-encoding, luego Base64 encima. Hay que pelarlas en orden inverso: Base64 primero (la capa de "afuera"), URL-decoding después.

> **Nota:** la plataforma regenera el archivo (y el string de comparación) cada vez que lo vuelves a descargar — si el flag da "incorrecto", vuelve a bajar el `.java` antes de recalcular.

# REFERENCIAS:
https://webshell.cylabacademy.org/
