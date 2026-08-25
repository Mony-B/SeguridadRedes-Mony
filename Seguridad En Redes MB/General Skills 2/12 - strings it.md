# DESCRIPCIÓN:
Can you find the flag in [file](https://challenge-files.picoctf.net/c_fickle_tempest/6577d3f1500aebcd300787bd5d96216b30aed379c811f5e83e888f897da4a3d5/strings) without running it?

Pista:
strings
# SOLUCIÓN:

#### picoCTF{5tRIng5_1T_d6306c19}
```
 wget https://challenge-files.picoctf.net/c_fickle_tempest/6577d3f1500aebcd300787bd5d96216b30aed379c811f5e83e888f897da4a3d5/strings
 
 mony@Mony:/mnt/c/Users/Usuario$ chmod +x strings
 
 mony@Mony:/mnt/c/Users/Usuario$ ./strings
Maybe try the 'strings' function? Take a look at the man page

mony@Mony:/mnt/c/Users/Usuario$ cat strings | grep pico
grep: (standard input): binary file matches
mony@Mony:/mnt/c/Users/Usuario$ strings strings | grep pico
picoCTF{5tRIng5_1T_d6306c19}

```
# NOTAS ADICIONALES:
- wget nos descarga archivos
- chmod +x nos otorga permisos de ejecución
- strings - Muestra las cadenas (Caracteres imprimibles) en un archivo binario (no texto).

# REFERENCIAS:
https://webshell.cylabacademy.org/

