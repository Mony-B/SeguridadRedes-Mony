# DESCRIPCIÓN:
Someone's commits seems to be preventing the program from working. Who is it?

You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/156/challenge.zip)
Hints
In collaborative projects, many users can make many changes. How can you see the changes within one file?

Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control)

You can use `python3 <file>.py` to try running the code, though you won't need to for this challenge.

# SOLUCIÓN:

#### picoCTF{@sk_th3_1nt3rn_d2d29f22}

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c_titan/156/challenge.zip

--2026-09-03 23:44:13--  https://artifacts.picoctf.net/c_titan/156/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.157.173.50, 108.157.173.76, 108.157.173.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.157.173.50|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 293739 (287K) [application/octet-stream]
Saving to: ‘challenge.zip.3’

challenge.zip.3               100%[=================================================>] 286.85K  1.25MB/s    in 0.2s

2026-09-03 23:44:15 (1.25 MB/s) - ‘challenge.zip.3’ saved [293739/293739]

mony@Mony:/mnt/c/Users/Usuario$
mony@Mony:/mnt/c/Users/Usuario$ unzip -q challenge.zip.3
mony@Mony:/mnt/c/Users/Usuario$ cd drop-in
mony@Mony:/mnt/c/Users/Usuario/drop-in$ git log message.py | grep picoCTF
Author: picoCTF{@sk_th3_1nt3rn_d2d29f22} <ops@picoctf.com>
Author: picoCTF <ops@picoctf.com>
mony@Mony:/mnt/c/Users/Usuario/drop-in$
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/