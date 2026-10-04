# DESCRIPCIÓN:
The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols. `ssh -p 41258 ctf-player@chatelaine.cylabacademy.net`

Use password: `8d1db23b`

Where can you get some letters?

# SOLUCIÓN:
####  academy{7h15_mu171v3r53_15_m4dn355_2bf65e09}

Conectarse al puerto por SSH. Usar el comando `/???/???[!_]64 */????.???` con puros comodines y signos de interrogación para saltarse la restricción de letras y forzar al sistema a ejecutar el programa `base64` sobre el archivo de la bandera. Copiar el texto codificado que sale en la terminal. Decodificar el texto de base64 para obtener la Flag.
```
┌──(mony㉿Mony)-[~]
└─$ echo "cmV0dXJuIDAgYWNhZGVteXs3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV8yYmY2NWUwOX0"|base64 -d
return 0 academy{7h15_mu171v3r53_15_m4dn355_2bf65e09}
┌──(mony㉿Mony)-[~]
└─$
```
 
 
# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/