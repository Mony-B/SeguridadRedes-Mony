# DESCRIPCIÓN:
Download this disk image, find the key and log into the remote machine.

Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.
# SOLUCIÓN:
#### academy{k3y_5l3u7h_0e000cd7}
```
┏━(Message from Kali developers)
┃
┃ This is a minimal installation of Kali Linux, you likely
┃ want to install supplementary tools. Learn how:
┃ ⇒ https://www.kali.org/docs/troubleshooting/common-minimum-setup/
┃
┗━(Run: “touch ~/.hushlogin” to hide this message)
┌──(mony㉿Mony)-[~]
└─$ wget https://challenge-files.cylabacademy.net/library/8af34b0fa863a6efa03d28278ca270b335291ad998f21c3696889bdc9c77ab72/disk.img.gz
--2026-10-08 10:33:00--  https://challenge-files.cylabacademy.net/library/8af34b0fa863a6efa03d28278ca270b335291ad998f21c3696889bdc9c77ab72/disk.img.gz
Resolving challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)... 18.238.132.88, 18.238.132.26, 18.238.132.115, ...
Connecting to challenge-files.cylabacademy.net (challenge-files.cylabacademy.net)|18.238.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 48132743 (46M) [application/octet-stream]
Saving to: ‘disk.img.gz’

disk.img.gz                   100%[=================================================>]  45.90M   824KB/s    in 51s

2026-10-08 10:33:52 (924 KB/s) - ‘disk.img.gz’ saved [48132743/48132743]


┌──(mony㉿Mony)-[~]
└─$ ssh -i key_file -p 33619 ctf-player@xebec.cylabacademy.net
Warning: Identity file key_file not accessible: No such file or directory.
The authenticity of host '[xebec.cylabacademy.net]:33619 ([3.14.181.178]:33619)' can't be established.
ED25519 key fingerprint is: SHA256:ZzFWPkrkkhq4v3aMejPdeBM6CxOJEdDfCOqwc0eXgfY
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[xebec.cylabacademy.net]:33619' (ED25519) to the list of known hosts.
ctf-player@xebec.cylabacademy.net's password:


┌──(mony㉿Mony)-[~]
└─$ gzip -d disk.img.gz
gzip: disk.img already exists; do you wish to overwrite (y or n)? y

┌──(mony㉿Mony)-[~]
└─$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)

┌──(mony㉿Mony)-[~]
└─$ fls -o 471039 disk.img -r | grep -i ssh
Cannot determine file system type

┌──(mony㉿Mony)-[~]
└─$ fls -o 206848 disk.img -r | grep -i ssh
++ r/r 2147:    sshd
+++ l/l 54:     sshd
++ r/r 2148:    sshd
+ d/d 14:       ssh
++ r/r 15:      ssh_host_ed25519_key
++ r/r 16:      ssh_host_ed25519_key.pub
++ r/r 17:      ssh_host_ecdsa_key
++ r/r 18:      ssh_host_ecdsa_key.pub
++ r/r 19:      ssh_host_dsa_key
++ r/r 20:      ssh_host_dsa_key.pub
++ r/r 21:      ssh_host_rsa_key
++ r/r 22:      ssh_host_rsa_key.pub
++ r/r 2136:    ssh_config
++ r/r 2149:    sshd_config
++ r/r 2084:    ssh-keygen
++ r/- * 0:     ssh-copy-id
++ r/- * 0:     ssh-keyscan
++ r/- * 0:     ssh-pkcs11-helper
++ r/r 2140:    ssh-add
++ r/r 2145:    ssh
++ r/r 2144:    ssh-pkcs11-helper
++ r/r 2143:    ssh-keyscan
++ r/r 2142:    ssh-copy-id
++ r/r 2141:    ssh-agent
++ r/r 2150:    sshd
+++++ r/r 676:  sshd
++ d/d 3907:    ssh
+++ r/r 2152:   ssh-sk-helper
+++ r/r 2151:   ssh-pkcs11-helper
+ r/r 712:      setup-sshd
+ d/d 3916:     .ssh

┌──(mony㉿Mony)-[~]
└─$ fls -o 206848 disk.img 3916
r/r 2345:       id_ed25519
r/r 2346:       id_ed25519.pub

┌──(mony㉿Mony)-[~]
└─$ icat -o 206848 disk.img 2346 > key_file

┌──(mony㉿Mony)-[~]
└─$ chmod 600 key_file

┌──(mony㉿Mony)-[~]
└─$ ssh -i key_file -p 33619 ctf-player@xebec.cylabacademy.net
Load key "key_file": error in libcrypto: unsupported
ctf-player@xebec.cylabacademy.net's password:


┌──(mony㉿Mony)-[~]
└─$ icat -o 206848 disk.img 2345 > key_file

┌──(mony㉿Mony)-[~]
└─$ ssh -i key_file -p 33619 ctf-player@xebec.cylabacademy.net
Welcome to Ubuntu 24.04.4 LTS (GNU/Linux 7.0.0-1014-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/pro

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls -lah
total 4.0K
drwxr-xr-x 1 ctf-player ctf-player 20 Oct  8 16:42 .
drwxr-xr-x 1 root       root       24 Sep 23 02:58 ..
drwx------ 2 ctf-player ctf-player 34 Oct  8 16:42 .cache
drwxr-xr-x 2 ctf-player ctf-player 29 Sep 23 02:58 .ssh
-rw-r--r-- 1 root       root       28 Sep 23 02:58 flag.txt
ctf-player@challenge:~$ cat flag.txt
academy{k3y_5l3u7h_0e000cd7}ctf-player@challenge:~$ Connection to xebec.cylabacademy.net closed by remote host.
Connection to xebec.cylabacademy.net closed.
```
# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/