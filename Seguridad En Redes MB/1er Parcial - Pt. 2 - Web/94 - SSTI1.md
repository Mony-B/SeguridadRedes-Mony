# DESCRIPCIÓN:
I made a cool website where you can announce whatever you want! Try it out! I heard templating is a cool and modular way to build web apps! Check out my website [here](http://chatelaine.cylabacademy.net:28428/)!

Server Side Template Injection

# SOLUCIÓN:
#### academy{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_90c0fc57}

Probé `{{7*7}}` y obtuve `49`, confirmando un SSTI. Después comprobé que usaba Flask/Jinja2 con `{{config}}` y accedí a objetos de Python. Finalmente utilicé el SSTI para ejecutar comandos en el servidor; `whoami` mostró que estaba como `root`. Busqué el flag con `find` y encontré `/challenge/flag`, y después lo leí con `cat`.

# NOTAS ADICIONALES:
La vulnerabilidad principal fue SSTI (Server-Side Template Injection), que permitió ejecutar comandos directamente en el servidor.
# REFERENCIAS:
https://webshell.cylabacademy.org/
Chat GPT
