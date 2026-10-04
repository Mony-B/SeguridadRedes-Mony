# DESCRIPCIÓN:
Can you invoke help flags for a tool or binary? This program has extraordinarily helpful information...

Hints

- This program will only work in the webshell or another Linux computer.
- To get the file accessible in your shell, enter the following in the Terminal prompt: $ wget + url here, where the url can be found in the details section...
- Run this program by entering the following in the Terminal prompt: $ ./warm, but you'll first have to make it executable with $ chmod +x warm
- -h and --help are the most common arguments to give to programs to get more information from them!
- Not every program implements help features like -h and --help.

# SOLUCIÓN:

#### picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}

```
PS C:\Users\Usuario> wsl
mony@Mony:/mnt/c/Users/Usuario$ wget https://challenge-files.picoctf.net/c_wily_courier/11d04620d1b8e59680f745f5e3d3957d48628b1e3e7c56c74c0030e82a778d63/warm
--2026-08-24 10:43:35--  https://challenge-files.picoctf.net/c_wily_courier/11d04620d1b8e59680f745f5e3d3957d48628b1e3e7c56c74c0030e82a778d63/warm
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.49, 18.238.132.26, 18.238.132.88, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19312 (19K) [application/octet-stream]
Saving to: ‘warm’

warm                          100%[=================================================>]  18.86K  --.-KB/s    in 0.08s

2026-08-24 10:43:38 (225 KB/s) - ‘warm’ saved [19312/19312]

mony@Mony:/mnt/c/Users/Usuario$ file warm
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=9e46ec8729d2f2aa8ffc4b1cdc058081bddcfe67, for GNU/Linux 3.2.0, with debug_info, not stripped
mony@Mony:/mnt/c/Users/Usuario$ chmod +x warm
mony@Mony:/mnt/c/Users/Usuario$ ./warm
Hello user! Pass me a -h to learn what I can do!
mony@Mony:/mnt/c/Users/Usuario$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_ac5832c}
```

# NOTAS ADICIONALES:
- - chmod +x nos otorga permisos de ejecución
- ./warm - Ejecuta el binario Warm una vez que ya tiene los permisos de ejecución.
- ELF - Formato de archivo ejecutable en linux, o sea como el exe en Windows.
- file - permite saber de qué tupo es un archivo

# REFERENCIAS:
https://webshell.cylabacademy.org/
