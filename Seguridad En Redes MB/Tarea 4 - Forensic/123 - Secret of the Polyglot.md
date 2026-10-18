# DESCRIPCIÓN:
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?

Download the suspicious file [here](https://challenge-files.cylabacademy.net/library/00e64c4ab0a092f8fef0d856d022560edd3e465c62dce1b270d764a99a9c4e1a/flag2of2-final.pdf).

This problem can be solved by just opening the file in different ways

# SOLUCIÓN:
#### academy{f1u3n7_1n_pn9_&_pdf_241519c6}

```
┌──(mony㉿Mony)-[~/forensic] 
└─$ pdftotext flag2of2-final.pdf 
└─$ cat flag2of2-final.txt # Extrae la segunda mitad: 1n_pn9_&_pdf_241519c6} 
└─$ mv flag2of2-final.pdf imagen.png # Se abre la imagen para ver la primera mitad
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/