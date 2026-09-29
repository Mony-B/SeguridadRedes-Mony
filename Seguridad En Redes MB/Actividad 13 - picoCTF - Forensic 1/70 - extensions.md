# DESCRIPCIÓN:
This is a really weird text file. Can you find the flag? Get the flag from [TXT](https://challenge-files.cylabacademy.net/library/a5d365fedad883763fb28c78e25a1765220bef6501848c84f2a7a7adf74d83cd/flag.txt)

Hints:
How do operating systems know what kind of file it is? (It's not just the ending!)

Make sure to submit the flag as academy{XXXXX}

# SOLUCIÓN:
#### academy{now_you_know_about_extensions}
Bajamos el archivo con wget, cambiamos la extensión de txt a png y después lo abrimos:

```
wget https://challenge-files.cylabacademy.net/library/a5d365fedad883763fb28c78e25a1765220bef6501848c84f2a7a7adf74d83cd/flag.txt
mv flag.txt flag.png
explorer.exe flag.png
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/