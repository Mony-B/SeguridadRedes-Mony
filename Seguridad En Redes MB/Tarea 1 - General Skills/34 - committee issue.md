# DESCRIPCIÓN:
 accidentally wrote the flag down. Good thing I deleted it!

You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/77/challenge.zip)

Version control can help you recover files if you change or lose them!

Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control)

You can 'checkout' commits to see the files inside them

# SOLUCIÓN:
#### picoCTF{s@n1t1z3_30e86d36}

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c_titan/77/challenge.zip
--2026-09-03 03:46:06--  https://artifacts.picoctf.net/c_titan/77/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.226.187.37, 13.226.187.66, 13.226.187.40, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.226.187.37|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19199 (19K) [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip                 100%[=================================================>]  18.75K  --.-KB/s    in 0.008s

2026-09-03 03:46:07 (2.42 MB/s) - ‘challenge.zip’ saved [19199/19199]

mony@Mony:/mnt/c/Users/Usuario$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample
  inflating: drop-in/.git/hooks/commit-msg.sample
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample
  inflating: drop-in/.git/hooks/post-update.sample
  inflating: drop-in/.git/hooks/pre-applypatch.sample
  inflating: drop-in/.git/hooks/pre-commit.sample
  inflating: drop-in/.git/hooks/pre-merge-commit.sample
  inflating: drop-in/.git/hooks/pre-push.sample
  inflating: drop-in/.git/hooks/pre-rebase.sample
  inflating: drop-in/.git/hooks/pre-receive.sample
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample
  inflating: drop-in/.git/hooks/update.sample
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD
  inflating: drop-in/.git/config
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/96/
 extracting: drop-in/.git/objects/96/f7309de67d785ec0b93b8766ff2882bef5c3ef
   creating: drop-in/.git/objects/8c/
 extracting: drop-in/.git/objects/8c/1d254e2da6713e33acd6d622fc1dae357ec3c6
   creating: drop-in/.git/objects/3d/
 extracting: drop-in/.git/objects/3d/5ec8a26ee7b092a1760fea18f384c35e435139
   creating: drop-in/.git/objects/d5/
 extracting: drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7
   creating: drop-in/.git/objects/0c/
 extracting: drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03
   creating: drop-in/.git/objects/e1/
 extracting: drop-in/.git/objects/e1/237df82d2e69f62dd53279abc1c8aeb66f6d64
  inflating: drop-in/.git/index
 extracting: drop-in/.git/COMMIT_EDITMSG
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master
 extracting: drop-in/message.txt
mony@Mony:/mnt/c/Users/Usuario$ cd drop -in
-bash: cd: too many arguments
mony@Mony:/mnt/c/Users/Usuario$ cd drop -in
-bash: cd: too many arguments
mony@Mony:/mnt/c/Users/Usuario$ cd drop -in
-bash: cd: too many arguments
mony@Mony:/mnt/c/Users/Usuario$
mony@Mony:/mnt/c/Users/Usuario$ cd drop-in
mony@Mony:/mnt/c/Users/Usuario/drop-in$ git log
commit e1237df82d2e69f62dd53279abc1c8aeb66f6d64 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:14 2024 +0000

    remove sensitive info

commit 3d5ec8a26ee7b092a1760fea18f384c35e435139
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:14 2024 +0000

    create flag
mony@Mony:/mnt/c/Users/Usuario/drop-in$ git log -p
commit e1237df82d2e69f62dd53279abc1c8aeb66f6d64 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:14 2024 +0000

    remove sensitive info

diff --git a/message.txt b/message.txt
index 96f7309..d552d1e 100644
--- a/message.txt
+++ b/message.txt
@@ -1 +1 @@
-picoCTF{s@n1t1z3_30e86d36}
+TOP SECRET

commit 3d5ec8a26ee7b092a1760fea18f384c35e435139
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:14 2024 +0000

    create flag

diff --git a/message.txt b/message.txt
new file mode 100644
index 0000000..96f7309
--- /dev/null
+++ b/message.txt
@@ -0,0 +1 @@
+picoCTF{s@n1t1z3_30e86d36}
mony@Mony:/mnt/c/Users/Usuario/drop-in$
```

# NOTAS ADICIONALES:
`git log -p` para inspeccionar el registro detallado de todos los cambios realizados en el repositorio.

# REFERENCIAS:
https://webshell.cylabacademy.org/