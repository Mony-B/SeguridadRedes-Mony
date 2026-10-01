# DESCRIPCIÓN:
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://challenge-files.cylabacademy.net/library/f500839660c0dddc9df4e5410dcd8e4d5a27f7ebae825caad4690a9d1646a451/whitepages.txt) is all blank!
There is data encoded somewhere... there might be an online decoder.
# SOLUCIÓN:
#### academy{not_all_spaces_are_created_equal_5fe1602ea91f835386aa3eae672cf4e3}

Para resolver este reto, primero instalamos `pwntools`:
```
sudo apt install python3-pwntools
```

Creamos nuestro script (por ejemplo, con `nano solve.py`) y le pegamos este código. Hay que asegurarnos de tener el archivo `whitepages.txt` en la misma carpeta:


```
from pwn import *

file = open('whitepages.txt', 'rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83', b'0')
data = data.replace(b'\x20', b'1')
data = data.decode('ascii')
data = unbits(data)

print(data)
```

Por último, lo ejecutamos en la terminal para sacar la flag:


```
python3 solve.py
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/