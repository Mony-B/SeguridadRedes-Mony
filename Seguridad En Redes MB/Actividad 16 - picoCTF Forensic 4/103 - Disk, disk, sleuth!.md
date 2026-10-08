# DESCRIPCIÓN:
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image. [dds1-alpine.flag.img.gz](https://challenge-files.cylabacademy.net/library/34106bdd624e0aec8af0ba0e9c52e7fd45d5d1415761ffc98b2130cace440057/dds1-alpine.flag.img.gz)

Hints

Have you ever used `file` to determine what a file was?

Relevant terminal-fu in Challenge Library: [https://learn.cylabacademy.org/library/85](https://learn.cylabacademy.org/library/85)

Mastering this terminal-fu would enable you to find the flag in a single command: [https://learn.cylabacademy.org/library/48](https://learn.cylabacademy.org/library/48)

Using your own computer, you could use qemu to boot from this disk!
# SOLUCIÓN:
#### academy{f0r3ns1c4t0r_n30phyt3_6502313d}

```
┌──(mony㉿Mony)-[~]
└─$ srch_strings dds1-alpine.flag.img | grep academy
  SAY academy{f0r3ns1c4t0r_n30phyt3_6502313d}
```
# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/