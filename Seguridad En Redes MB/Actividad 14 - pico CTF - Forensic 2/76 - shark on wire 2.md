# DESCRIPCIÓN:

# SOLUCIÓN:
##### academy{p1LLf3r3d_data_v1a_st3g0}
Primero ocupamos instalar scapy:

```
sudo apt install python3-scapy
```

Revisando bien, los paquetes que nos sirven se van al puerto 22 y traen las letras escondidas. Con este script las juntamos y sacamos la flag:

```
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
	if UDP in p and p[UDP].dport == 22:
		if p[UDP].sport > 5000:
			flag += chr(p[UDP].sport-5000)
			
print(flag)
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/