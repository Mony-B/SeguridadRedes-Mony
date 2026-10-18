# DESCRIPCIÓN:
Every file gets a flag. The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://challenge-files.cylabacademy.net/library/afab2dc0b8164303df06666c7b574103668443cba057e14f9d6683ce67665bda/flag.png)
# SOLUCIÓN:
#### academy{Hiddinng_An_imag3_within_@n_ima9e_c55a7afe}

```

┌──(mony㉿Mony)-[~/forensic]
└─$ binwalk -e flag.png

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
75            0x4B            Zlib compressed data, default compression
15929         0x3E39          Zip archive data, at least v1.0 to extract, name: secret/
15994         0x3E7A          Zip archive data, at least v1.0 to extract, compressed size: 5349, uncompressed size: 5349, name: secret/flag.png

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented


┌──(mony㉿Mony)-[~/forensic]
└─$ cd _flag.png.extracted
ls -la
total 968
drwxr-xr-x 3 mony mony   4096 Oct 17 19:55 .
drwxr-xr-x 3 mony mony   4096 Oct 17 19:55 ..
-rw-r--r-- 1 mony mony   5671 Oct 17 19:55 3E39.zip
-rw-r--r-- 1 mony mony 945450 Oct 17 19:55 4B
-rw-r--r-- 1 mony mony  21525 Oct 17 19:55 4B.zlib
drwxr-xr-x 2 mony mony   4096 Sep 22 22:33 secret

┌──(mony㉿Mony)-[~/forensic/_flag.png.extracted]
└─$ cd secret

┌──(mony㉿Mony)-[~/forensic/_flag.png.extracted/secret]
└─$ ls
flag.png

┌──(mony㉿Mony)-[~/forensic/_flag.png.extracted/secret]
└─$ flag.png
flag.png: command not found

┌──(mony㉿Mony)-[~/forensic/_flag.png.extracted/secret]
└─$ explorer.exe .

y en la imagen salía a flag.

```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/