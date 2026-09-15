# DESCRIPCIÓN:
Can you find the flag on this website.
Hint: SQLite
# SOLUCIÓN:
#### picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_98236ce6}

Después de consultar versión de SQLite, nombre de tablas, código SQL, hacemos una consulta directa a la tabla con los campos que nos interesan:
```
|City|Address|Phone|
|---|---|---|
|1|1|picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_98236ce6}|
|1|2|If you are here, you must have seen it|
```
Fotito:
![[Pasted image 20260915002958.png]]
# NOTAS ADICIONALES:
El prota del reto: John the Ripper
# REFERENCIAS:
[picoCTF SQLi Challenge](http://saturn.picoctf.net:61514/welcome.php)
[JWT Debugger - jwt.lannysport.net](https://jwt.lannysport.net/)
[openwall/john: John the Ripper jumbo - advanced offline password cracker, which supports hundreds of hash and cipher types, and runs on many operating systems, CPUs, GPUs, and even some FPGAs](https://github.com/openwall/john)
https://webshell.cylabacademy.org/