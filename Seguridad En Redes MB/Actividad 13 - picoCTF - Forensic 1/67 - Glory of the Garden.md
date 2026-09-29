# DESCRIPCIÓN:
This file contains more than it seems. Get the flag from [garden.jpg](https://challenge-files.cylabacademy.net/library/3c60c5a7f7a8067606c51d4b4b3c7913fae709b11e2f2c7adbc0a0b4cda452ff/garden.jpg).
What is a hex editor?

# SOLUCIÓN:
#### academy{more_than_m33ts_the_3y3ff3b9e86}

Descargamos imagen con wget: 
```

┌──(mony㉿Mony)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/3c60c5a7f7a8067606c51d4b4b3c7913fae709b11e2f2c7adbc0a0b4cda452ff/garden.jpg
--2026-09-29 08:45:07--  https://challenge-files.cylabacademy.net/library/3c60c5a7f7a8067606c51d4b4b3c7913fae709b11e2f2c7adbc0a0b4cda452ff/garden.jpg
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.115, 18.238.132.49, 18.238.132.88, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295191 (2.2M) [application/octet-stream]
Saving to: ‘garden.jpg’

garden.jpg                    100%[=================================================>]   2.19M   973KB/s    in 2.3s

```
Y filtramos la bandera:
```
┌──(mony㉿Mony)-[~]
└─$ strings garden.jpg | grep academy
Here is a flag: academy{more_than_m33ts_the_3y3ff3b9e86}
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/