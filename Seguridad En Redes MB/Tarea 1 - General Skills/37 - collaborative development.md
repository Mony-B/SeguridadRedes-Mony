# DESCRIPCIÓN:
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?

You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/71/challenge.zip)

Hints

`git branch -a` will let you see available branches

How can file 'diffs' be brought to the main branch? Don't forget to `git config`!

Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.

# SOLUCIÓN:
#### **`picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_4c24302f}`**
```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c_titan/71/challenge.zip
--2026-09-03 23:55:24--  https://artifacts.picoctf.net/c_titan/71/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 108.157.173.76, 108.157.173.50, 108.157.173.42, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|108.157.173.76|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24467 (24K) [application/octet-stream]
Saving to: ‘challenge.zip.4’

challenge.zip.4               100%[=================================================>]  23.89K  --.-KB/s    in 0.02s

2026-09-03 23:55:25 (1.41 MB/s) - ‘challenge.zip.4’ saved [24467/24467]

mony@Mony:/mnt/c/Users/Usuario$ unzip -q challenge.zip.4
replace drop-in/.git/description? [y]es, [n]o, [A]ll, [N]one, [r]ename: A
mony@Mony:/mnt/c/Users/Usuario$ cd drop-in
mony@Mony:/mnt/c/Users/Usuario/drop-in$ git branch -a
  feature/part-1
  feature/part-2
  feature/part-3
* main
  master
mony@Mony:/mnt/c/Users/Usuario/drop-in$ git show feature/part-1:flag.py
git show feature/part-2:flag.py
git show feature/part-3:flag.py
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')
print("Printing the flag...")

print("w0rk_4c24302f}")
mony@Mony:/mnt/c/Users/Usuario/drop-in$
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/