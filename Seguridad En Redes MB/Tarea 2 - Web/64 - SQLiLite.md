# DESCRIPCIÓN:
Can you login to this website? Try to login [here](http://chatelaine.cylabacademy.net:25542/)
`admin` is the user you want to login as.
# SOLUCIÓN:
#### academy{L00k5_l1k3_y0u_solv3d_it_d69457c6}
Básicamente el formulario de login nos mostraba la consulta de la base de datos, así que era vulnerable a SQLi. En el campo de usuario le metí el payload `admin' --` y en la contraseña lo que sea (tipo `1234`).
La comilla simple cerró el parámetro del usuario y los guiones comentaron el resto de la consulta, lo que anuló por completo la validación de la contraseña. Con eso jaló directo y nos dio acceso como administrador.
Ya adentro decía que se inició sesión pero no se veía la bandera a simple vista. Le di **Ctrl + U** para ver el código fuente y ahí estaba escondida dentro de una etiqueta `<p hidden>`
# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/