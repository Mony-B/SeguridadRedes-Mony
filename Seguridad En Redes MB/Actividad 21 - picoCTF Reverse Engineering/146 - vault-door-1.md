# DESCRIPCIÓN:
**vault-door-1** — Reverse Engineering (Medium) — by Mark E. Haase · picoCTF 2019

This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://challenge-files.cylabacademy.net/library/7ff7ce9573f5e92a7652cfc30195172dbf0305f2baa7b14dd3206365cbc83750/VaultDoor1.java)

**Hint:** Look up el método `charAt()`.

# SOLUCIÓN:
#### academy{d35cr4mbl3_tH3_cH4r4cT3r5_d66e42}

Aquí `checkPassword` ya no compara un string completo, sino que valida letra por letra con `password.charAt(i) == 'x'` para cada una de las 32 posiciones, pero las condiciones están puestas en desorden (no van del índice 0 al 31). Lo que hice fue armar una tabla índice → carácter leyendo cada línea del `&&`:

| idx | char | idx | char | idx | char | idx | char |
| --- | ---- | --- | ---- | --- | ---- | --- | ---- |
| 0   | d    | 8   | l    | 16  | H    | 24  | 5    |
| 1   | 3    | 9   | 3    | 17  | 4    | 25  | _    |
| 2   | 5    | 10  | _    | 18  | r    | 26  | d    |
| 3   | c    | 11  | t    | 19  | 4    | 27  | 6    |
| 4   | r    | 12  | H    | 20  | c    | 28  | 6    |
| 5   | 4    | 13  | 3    | 21  | T    | 29  | e    |
| 6   | m    | 14  | _    | 22  | 3    | 30  | 4    |
| 7   | b    | 15  | c    | 23  | r    | 31  | 2    |

Juntando los 32 caracteres en orden (0→31) queda `d35cr4mbl3_tH3_cH4r4cT3r5_d66e42`, que en leetspeak se lee "descramble_the_characters_" + el sufijo random. La metí en el formato `academy{...}`.

# NOTAS ADICIONALES:
Como no checa `password.length()` de forma explícita salvo por el `&&` inicial `password.length() == 32`, cualquier posición que no aparece en la lista de `charAt` no importa para la validación — pero como cubre las 32 posiciones completas, no hay huecos.

# REFERENCIAS:
https://webshell.cylabacademy.org/
