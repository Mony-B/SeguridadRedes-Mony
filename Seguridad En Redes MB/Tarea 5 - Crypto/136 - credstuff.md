# DESCRIPCIÓN:
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it? Download the leak [here](https://challenge-files.cylabacademy.net/library/7f760cee144ac7237469fd6bfab7c748d6f1d101ca47c101187ca7d8f5c721f0/leak.tar).
The first user in `usernames.txt` corresponds to the first password in `passwords.txt`, and así sucesivamente.

# SOLUCIÓN:
#### academy{C7r1F_54V35_71M3}

```
┌──(mony㉿Mony)-[~/crypto]
└─$ tar -xf leak.tar
┌──(mony㉿Mony)-[~/crypto]
└─$ grep -n "cultiris" leak/usernames.txt
378:cultiris
┌──(mony㉿Mony)-[~/crypto]
└─$ sed -n '378p' leak/passwords.txt
npnqrzl{P7e1S_54I35_71Z3}
┌──(mony㉿Mony)-[~/crypto]
└─$ echo "npnqrzl{P7e1S_54I35_71Z3}" | tr 'A-Za-z' 'N-ZA-Mn-za-m'
academy{C7r1F_54V35_71M3}
```

`npnqrzl` descifrado con ROT13 da justo `academy`, lo que confirma el cifrado usado en todas las contraseñas del leak.

# NOTAS ADICIONALES:
El hint sugería que otras contraseñas del leak darían pistas sobre el cifrado — varias de ellas, al aplicar ROT13, revelan palabras legibles, lo que permite confirmar el método sin tener que adivinarlo a ciegas.

# REFERENCIAS:
https://es.wikipedia.org/wiki/ROT13
https://webshell.cylabacademy.org/
