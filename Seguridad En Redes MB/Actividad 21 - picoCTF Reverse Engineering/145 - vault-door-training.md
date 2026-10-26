# DESCRIPCIÓN:
**vault-door-training** — Reverse Engineering (Easy) — by Mark E. Haase · picoCTF 2019

Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility.

The source code for the training vault is here: [VaultDoorTraining.java](https://challenge-files.cylabacademy.net/library/83cea9a75c072b1b2dff071720061929c5a4e9817a86613e1c51ebc0540cbc73/VaultDoorTraining.java)

# SOLUCIÓN:
#### academy{w4rm1ng_Up_w1tH_jAv4_4cfa5369b93}

Abrí el `.java` y fui directo al método `checkPassword`:

```java
public boolean checkPassword(String password) {
    return password.equals("w4rm1ng_Up_w1tH_jAv4_4cfa5369b93");
}
```

La contraseña está literalmente escrita en el código fuente (como bien dice el comentario del Minion #9567, "¿será seguro poner la contraseña en el código?" — pues no). Solo la copié y la metí en el formato `academy{...}` que usa el `main` (quita el prefijo `academy{` y el `}` final antes de comparar).

# NOTAS ADICIONALES:
Nivel de calentamiento: el checkeo es una comparación directa de string, sin ningún tipo de transformación. Sirve para entender el patrón `main` que se repite en los demás vault-door (recorta `academy{...}` y llama a `checkPassword`).

# REFERENCIAS:
https://webshell.cylabacademy.org/
