# DESCRIPCIÓN:
How to automate tasks to run at intervals on linux servers?

Use ssh to connect to this server:

`Server: saturn.picoctf.net Port: 54139 Username: picoplayer Password: emrdK96SGH`

# SOLUCIÓN:
#### picoCTF{Sch3DUL7NG_T45K3_L1NUX_0bb95b71}

1. ```
mony@Mony:/mnt/c/Users/Usuario$ ssh -p 56333 picoplayer@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:56333 ([13.59.203.175]:56333)' can't be established.
ED25519 key fingerprint is: SHA256:dMTscRrUiURy7uMu5eGWwEKdd2FzqLzx6LfWhssWnNQ
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:11: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:56333' (ED25519) to the list of known hosts.
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

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

picoplayer@challenge:~$ cat /etc/crontab
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_0bb95b71}
picoplayer@challenge:~$ Connection to saturn.picoctf.net closed by remote host.
    ```


# NOTAS ADICIONALES:
- **cron:** Es el administrador de procesos en segundo plano de Linux que ejecuta scripts o comandos a intervalos regulares.
    
- **crontab:** El archivo principal (o tabla) donde se configuran los horarios y las tareas que `cron` debe ejecutar.

# REFERENCIAS:
https://webshell.cylabacademy.org/