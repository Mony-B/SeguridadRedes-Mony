# DESCRIPCIÓN:
Can you find the flag in the file? This would be really tedious to look through manually, something tells me there is a better way.

# SOLUCIÓN:

#### picoCTF{grep_is_good_to_find_things_29f42460}

1. Descargar el archivo y con Ctrl+F buscamos la clave: picoCTF{grep_is_good_to_find_things_29f42460}

2. Descargar archivo y listamos para ver si estaba (ls), con un grep lo filtramos:
	```
	mony@Mony:~$ wget https://challenge-files.picoctf.net/c_fickle_tempest/2e9bfa4e1d90ac25a999fefdfb4feb8a2ff4eb73e4c61af4889a3762687ada01/file
--2026-08-19 23:15:22--  https://challenge-files.picoctf.net/c_fickle_tempest/2e9bfa4e1d90ac25a999fefdfb4feb8a2ff4eb73e4c61af4889a3762687ada01/file
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.49, 18.238.132.88, 18.238.132.115, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14546 (14K) [application/octet-stream]
Saving to: ‘file’

file                          100%[=================================================>]  14.21K  --.-KB/s    in 0s

2026-08-19 23:15:24 (102 MB/s) - ‘file’ saved [14546/14546]

mony@Mony:~$ ls
file
mony@Mony:~$ cat file | grep picoCTF
picoCTF{grep_is_good_to_find_things_29f42460}
	```

# NOTAS ADICIONALES:
- Cat abre archivos
- Grep filtra palabras
- Wget descarga desde el enlace pegado dps

# REFERENCIAS:
https://challenge-files.picoctf.net/c_fickle_tempest/2e9bfa4e1d90ac25a999fefdfb4feb8a2ff4eb73e4c61af4889a3762687ada01/file
