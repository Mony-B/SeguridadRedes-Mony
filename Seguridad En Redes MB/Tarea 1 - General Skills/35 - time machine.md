# DESCRIPCIÓN:
What was I last working on? I remember writing a note to help me remember...

You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/162/challenge.zip)

The `cat` command will let you read a file, but that won't help you here!

Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).

When committing a file with git, a message can (and should) be included.
# SOLUCIÓN:
####     picoCTF{t1m3m@ch1n3_e8c98b3a}
```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c_titan/162/challenge.zip
mony@Mony:/mnt/c/Users/Usuario$ unzip -q challenge.zip
mony@Mony:/mnt/c/Users/Usuario$ cd drop-in
mony@Mony:/mnt/c/Users/Usuario/drop-in$ git log
commit 712314f105348e295f8cadd7d7dc4e9fa871e9a2 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:26 2024 +0000

    picoCTF{t1m3m@ch1n3_e8c98b3a}
```


# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/