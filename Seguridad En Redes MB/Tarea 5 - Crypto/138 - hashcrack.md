# DESCRIPCIÓN:
A company stored a secret message on a server which got breached due to the admin using weakly hashed passwords. Can you gain access to the secret stored within the server? Access the server using `nc xebec.cylabacademy.net <puerto>`.

# SOLUCIÓN:
#### academy{UseStr0nG_h@shEs_&PaSswDs!_35c6b1f4}

El servicio presenta **3 hashes en secuencia**, uno por algoritmo. El algoritmo se identifica por la longitud en hexadecimal: 32=MD5, 40=SHA-1, 64=SHA-256.

```
┌──(mony㉿Mony)-[~]
└─$ nc xebec.cylabacademy.net 29063
Welcome!! Looking For the Secret?

We have identified a hash: 482c811da5d5b4bc6d497ffa98491e38
Enter the password for identified hash: password123
Correct! You've cracked the MD5 hash with no secret found!

Flag is yet to be revealed!! Crack this hash: b7a875fc1ea228b9061041b7cec4bd3c52ab3ce3
Enter the password for the identified hash: letmein
Correct! You've cracked the SHA-1 hash with no secret found!

Almost there!! Crack this hash: 916e8c4f79b25028c9e467f1eb8eee6d6bbdff965f9928310ad30a8d88697745
Enter the password for the identified hash: qwerty098
Correct! You've cracked the SHA-256 hash with a secret found.
The flag is: academy{UseStr0nG_h@shEs_&PaSswDs!_35c6b1f4}
```

- MD5 (32 hex): `482c811d...` → contraseña muy común, `password123`.
- SHA-1 (40 hex): `b7a875fc...` → otra contraseña común, `letmein`.
- SHA-256 (64 hex): `916e8c4f...` → se crackea contra un diccionario (rockyou.txt) → `qwerty098`.

# NOTAS ADICIONALES:
Hashes sin sal (`salt`) de contraseñas débiles se rompen al instante con un diccionario — justo la lección del reto: usar siempre hashing con sal y contraseñas fuertes.

# REFERENCIAS:
https://primer.cylabacademy.org/#_hashing
https://webshell.cylabacademy.org/
