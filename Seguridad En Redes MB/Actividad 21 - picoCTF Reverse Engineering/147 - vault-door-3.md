# DESCRIPCIÓN:
**vault-door-3** — Reverse Engineering (Medium) — by Mark E. Haase · picoCTF 2019

This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://challenge-files.cylabacademy.net/library/2142576c74296209b8a72720ae1c3c1a408fb11d9c2dc07ee8613febf6252834/VaultDoor3.java)

**Hint:** Hacer una tabla con cada valor de las variables del loop y el índice del buffer al que escriben.

# SOLUCIÓN:
#### academy{jU5t_a_s1mpl3_an4gr4m_4_u_e7de62}

`checkPassword` arma un `buffer[32]` a partir del `password` que metemos, con 4 loops distintos, y al final compara `buffer` contra el string fijo `"jU5t_a_sna_3lpm16gd4e_u_4_m7re42"`. Como ya conocemos el resultado (`buffer`) y la regla de cada loop, lo que hice fue invertir el mapeo: para cada posición del buffer, de dónde sale ese carácter en `password`, y de ahí derivar qué carácter de `password` corresponde a cada carácter del buffer conocido.

Mapeo (buffer[i] = password[j]):

- `i = 0..7`   → `j = i` (copia directa)
- `i = 8..15`  → `j = 23 - i`
- `i = 16,18,20,...,30` → `j = 46 - i`
- `i = 17,19,21,...,31` → `j = i` (copia directa, el último loop va de 31 a 17)

Armé la tabla completa (32 filas) y, como cada `j` aparece exactamente una vez, pude despejar `password[j] = buffer[i]` para cada posición, usando el string objetivo como los valores de `buffer`. Al ordenar `password[0..31]` quedó:

`jU5t_a_s1mpl3_an4gr4m_4_u_d78c62`

Que se lee "Just_a_simple_anagram_4_u_" + sufijo random. Ese es justo el password que hay que mandar (envuelto en `academy{...}`), y al pasar por los 4 loops del reto se reordena hasta formar el string fijo con el que compara.

# NOTAS ADICIONALES:
El truco está en que el reto compara contra una versión "desordenada" (`buffer`) del password real — el password bonito/legible es la entrada, no el string fijo del código. Por eso hay que invertir la permutación en vez de solo "copiar" el string fijo.

# REFERENCIAS:
https://webshell.cylabacademy.org/

> **Nota:** la plataforma regeneró el archivo con un string de comparación distinto al bajarlo de nuevo (ojo con esto en los demás vault-door: si el flag da "incorrecto", re-descargar el .java antes de rehacer el reto).
