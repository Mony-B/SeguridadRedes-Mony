# DESCRIPCIÓN:
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?

You can download the challenge files here:

- [challenge.zip](https://challenge-files.cylabacademy.net/library/55c0e897129786cdc2c3f7c8f08e346866d9c187f20adf8b2f22a0ed2fe76e37/challenge.zip)

Additional details appear once you launch your instance.

QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.

Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11

3

If you don't have access to a phone, you can also use zbar-tools to convert an image to text

# SOLUCIÓN:
#### academy{p33k_@_b00_5f0d36e7}

 Descargamos el archivo, accedemos a la dirección, escaneamos el QR y listo.
 
```
┌──(mony㉿Mony)-[~/forensic]
└─$ ssh -p 48298 ctf-player@chatelaine.cylabacademy.net

The authenticity of host '[chatelaine.cylabacademy.net]:48298 ([18.190.79.158]:48298)' can't be established.
ED25519 key fingerprint is: SHA256:pXZJJueHk/xqC/LPp14k8Mb1vT0LHQpM4b9yfyz7M24
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[chatelaine.cylabacademy.net]:48298' (ED25519) to the list of known hosts.
ctf-player@chatelaine.cylabacademy.net's password:

ctf-player@challenge:~/drop-in$ Connection to chatelaine.cylabacademy.net closed by remote host.
Connection to chatelaine.cylabacademy.net closed.

┌──(mony㉿Mony)-[~/forensic]
└─$
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/