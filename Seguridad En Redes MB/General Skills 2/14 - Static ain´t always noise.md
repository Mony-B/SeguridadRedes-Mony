# DESCRIPCIÓN:
Can you look at the data in this binary? The bash script might help!

[static](https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/static), [ltdis.sh](https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/ltdis.sh)

# SOLUCIÓN:
#### picoCTF{d15a5m_t34s3r_20335e41}
```

mony@Mony:/mnt/c/Users/Usuario$ wget https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/static
--2026-08-24 10:54:13--  https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/static
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.160.249.52, 18.160.249.123, 18.160.249.43, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.160.249.52|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16776 (16K) [application/octet-stream]
Saving to: ‘static’

static                        100%[=================================================>]  16.38K  --.-KB/s    in 0.006s

2026-08-24 10:54:16 (2.80 MB/s) - ‘static’ saved [16776/16776]

mony@Mony:/mnt/c/Users/Usuario$ wget https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/ltdis.sh
--2026-08-24 10:54:32--  https://challenge-files.picoctf.net/c_wily_courier/418e2775a501eaabeb99a96c5c467a83539369fe9649e8234644250cfb72d717/ltdis.sh
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.154.206.27, 18.154.206.118, 18.154.206.121, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.154.206.27|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: ‘ltdis.sh’

ltdis.sh                      100%[=================================================>]     785  --.-KB/s    in 0.002s

2026-08-24 10:54:34 (323 KB/s) - ‘ltdis.sh’ saved [785/785]

mony@Mony:/mnt/c/Users/Usuario$ file ltdis.sh
ltdis.sh: Bourne-Again shell script, ASCII text executable
mony@Mony:/mnt/c/Users/Usuario$ chmod +x ltdis.sh
mony@Mony:/mnt/c/Users/Usuario$ ./ltdis.sh
Attempting disassembly of  ...
objdump: 'a.out': No such file
objdump: section '.text' mentioned in a -j option, but not found in any input file
Disassembly failed!
Usage: ltdis.sh <program-file>
Bye!
mony@Mony:/mnt/c/Users/Usuario$ ./ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
mony@Mony:/mnt/c/Users/Usuario$ strings static | grep pico
picoCTF{d15a5m_t34s3r_20335e41}



```


# NOTAS ADICIONALES:
- .sh son archivos que contienen comandos de linux agrupados, se llaman bash.
- rm * borra todos los archivos de la carpeta actual
- rm - rf* borra todos los archivos y carpetas dentro de la carpeta actual, sin preguntar

# REFERENCIAS:
https://webshell.cylabacademy.org/