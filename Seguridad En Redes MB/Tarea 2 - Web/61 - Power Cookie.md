# DESCRIPCIÓN:
Can you get the flag? Go to this [website](http://xebec.cylabacademy.net:39473/) and see what you can discover.
Do you know how to modify cookies?
# SOLUCIÓN:
#### academy{gr4d3_A_c00k13_2dd015a8}

Para resolver este reto, primero inspeccionamos el código fuente y descubrimos en el archivo `guest.js` que el sistema asigna una cookie llamada `isAdmin` con el valor `0` para los invitados. Como la página bloquea el acceso a este rol, abrimos las Herramientas de Desarrollador del navegador y nos dirigimos a la pestaña **Application** dentro de la sección de **Cookies**. Ahí, editamos manualmente el valor de la cookie `isAdmin`, cambiándolo de `0` a `1`. Al recargar la página, el servidor nos identifica con privilegios de administrador y nos entrega la bandera.

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/