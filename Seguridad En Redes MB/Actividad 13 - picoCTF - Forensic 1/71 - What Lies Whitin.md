# DESCRIPCIÓN:
here's something in the [building](https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png). Can you retrieve the flag?

There is data encoded somewhere... there might be an online decoder.

# SOLUCIÓN:
#### academy{h1d1ng_1n_th3_b1t5}

Descargamos el archivo con wget y hacemos el comando:
```

┌──(mony㉿Mony)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png
--2026-09-29 10:12:10--  https://challenge-files.cylabacademy.net/library/5235bfccd8f3cc2d059ee828f774846542f28f7ec66cb4f0c6ceb536c38026d4/buildings.png
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.49, 18.238.132.26, 18.238.132.88, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 615860 (601K) [application/octet-stream]
Saving to: ‘buildings.png’

buildings.png                 100%[=================================================>] 601.43K   258KB/s    in 2.3s

2026-09-29 10:12:14 (258 KB/s) - ‘buildings.png’ saved [615860/615860]

──(mony㉿Mony)-[~]
└─$ zsteg -a buildings.png | grep academy
b1,rgb,lsb,xy       .. text: "academy{h1d1ng_1n_th3_b1t5}"

```
# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/