# DESCRIPCIÓN:
We found this [packet capture](https://challenge-files.cylabacademy.net/library/e64f2c2aaf9bf531af7be1787c1407c47a4cc7b57f251d5108a1151e9721a2d6/shark-on-wire-1-capture.pcap). Recover the flag.

Try using a tool like Wireshark, What are streams?

# SOLUCIÓN:
#### academy{StaT31355_636f6e6e}

Primero descargamos con wgtet el archivo:
```
┌──(mony㉿Mony)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/e64f2c2aaf9bf531af7be1787c1407c47a4cc7b57f251d5108a1151e9721a2d6/shark-on-wire-1-capture.pcap
--2026-09-29 09:10:43--  https://challenge-files.cylabacademy.net/library/e64f2c2aaf9bf531af7be1787c1407c47a4cc7b57f251d5108a1151e9721a2d6/shark-on-wire-1-capture.pcap
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.49, 18.238.132.115, 18.238.132.88, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.49|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 239455 (234K) [application/octet-stream]
Saving to: ‘shark-on-wire-1-capture.pcap.1’

shark-on-wire-1-capture.pcap. 100%[=================================================>] 233.84K   759KB/s    in 0.3s

2026-09-29 09:10:46 (759 KB/s) - ‘shark-on-wire-1-capture.pcap.1’ saved [239455/239455]
```

Ejecutamos wireshark y luego abrimos el archivo shark-on-wire-1-capture.pcap
Ahora en la pestaña de Analyze > Follow > UDP Stream
Ya estando ahí cambiamos la secuencia a 6 y ahi estará la bandera

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/