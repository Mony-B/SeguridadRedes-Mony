# DESCRIPCIÓN:
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag?

Connect to fickle-tempest.picoctf.net 64279.

# SOLUCIÓN:
#### picoCTF{digital_plumb3r_00da27CC}

```
mony@Mony:~$ nc fickle-tempest.picoctf.net 64279 | grep picoCTF
picoCTF{digital_plumb3r_00da27CC}
```

# NOTAS ADICIONALES:
- Nuevamente usamos Net Cat para conectarnos y filtramos con grape, ya que era bastante texto innecesario, y no guardamos, solo filtramos.
- La barrita ´|´ o pipe, redirige la salida de un comando a otro comando

# REFERENCIAS:
https://webshell.cylabacademy.org/