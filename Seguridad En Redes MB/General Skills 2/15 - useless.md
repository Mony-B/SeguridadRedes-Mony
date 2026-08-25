# DESCRIPCIÓN:
There's an interesting script in the user's home directory

The work computer is running SSH. We've been given a script which performs some basic calculations, explore the script and find a flag.

`Hostname: saturn.picoctf.net Port: 53411 Username: picoplayer Password: password`

# SOLUCIÓN:

####      picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_3823}
```
mony@Mony:/mnt/c/Users/Usuario$ ssh picoplayer@saturn.picoctf.net -p 53411
The authenticity of host '[saturn.picoctf.net]:53411 ([13.59.203.175]:53411)' can't be established.
ED25519 key fingerprint is: SHA256:DiJcS90U9QussLS8HLR6l6BGJb5eCA0vRmA18IvDvw8
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:53411' (ED25519) to the list of known hosts.
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
picoplayer@saturn.picoctf.net's password:
Welcome to Ubuntu 20.04.6 LTS (GNU/Linux 6.17.0-1019-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

picoplayer@challenge:~$ ls
useless
picoplayer@challenge:~$ ./uselesss
-bash: ./uselesss: No such file or directory
picoplayer@challenge:~$ ./useless
Read the code first
picoplayer@challenge:~$ cat useless
#!/bin/bash
# Basic mathematical operations via command-line arguments

if [ $# != 3 ]
then
  echo "Read the code first"
else
        if [[ "$1" == "add" ]]
        then
          sum=$(( $2 + $3 ))
          echo "The Sum is: $sum"

        elif [[ "$1" == "sub" ]]
        then
          sub=$(( $2 - $3 ))
          echo "The Substract is: $sub"

        elif [[ "$1" == "div" ]]
        then
          div=$(( $2 / $3 ))
          echo "The quotient is: $div"

        elif [[ "$1" == "mul" ]]
        then
          mul=$(( $2 * $3 ))
          echo "The product is: $mul"

        else
          echo "Read the manual"

        fi
fi
picoplayer@challenge:~$ man useless

useless
     useless, — This is a simple calculator script

SYNOPSIS
     useless, [add sub mul div] number1 number2

DESCRIPTION
     Use the useless, macro to make simple calulations like addition,subtraction, multiplication and division.

Examples
     ./useless add 1 2
       This will add 1 and 2 and return 3

     ./useless mul 2 3
       This will return 6 as a product of 2 and 3

     ./useless div 6 3
       This will return 2 as a quotient of 6 and 3

     ./useless sub 6 5
       This will return 1 as a remainder of substraction of 5 from 6

Authors
     This script was designed and developed by Cylab Africa

     picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_3823}

picoplayer@challenge:~$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
mony@Mony:/mnt/c/Users/Usuario$
```

# NOTAS ADICIONALES:
- man te proporciona un manual de ayuda completo de un comando o ejecutable si es lo que hay

# REFERENCIAS:
https://webshell.cylabacademy.org/
