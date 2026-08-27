# DESCRIPCIÓN:
Using a Secure Shell (SSH) is going to be pretty important.
1. [](https://linux.die.net/man/1/ssh)[https://linux.die.net/man/1/ssh](https://linux.die.net/man/1/ssh) 
2. You can try logging in 'as' someone with `<user>`@titan.picoctf.net
3. How could you specify the port?
4. Remember, passwords are hidden when typed into the shell

# SOLUCIÓN:
#### picoCTF{s3cur3_c0nn3ct10n_07a987ac}

```
mony@Mony:/mnt/c/Users/Usuario$ ssh ctf-player@titan.picoctf.net -p 5183
1
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
ctf-player@titan.picoctf.net's password:
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_07a987ac}
Connection to titan.picoctf.net closed.
mony@Mony:/mnt/c/Users/Usuario$
```

# NOTAS ADICIONALES:
- SSH es Secure Shell, muy importante para hacer loggin.

# REFERENCIAS:
https://webshell.cylabacademy.org/
[ssh(1): OpenSSH SSH client - Linux man page](https://linux.die.net/man/1/ssh)