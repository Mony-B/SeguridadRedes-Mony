# DESCRIPCIÓN:
Help us test the form by submiting the username as `test` and password as `test!`
# SOLUCIÓN:
#### academy{proxies_all_the_way_661fc398}

Abrir el enlace del reto. Presionar F12 para abrir las herramientas de desarrollador y entrar a la pestaña de Red. Marcar la casilla de "Keep log". Ingresar la palabra `test` en los campos de usuario y contraseña, y enviar el formulario. Revisar en la lista las peticiones de redirección con estado 302. Copiar los valores codificados que aparecen en los parámetros `id=` de las URLs en esos saltos intermedios. Decodificar ambas partes del texto de Base64 y unirlas para obtener la Flag completa.
![[Pasted image 20261004000201.png]]

```

┌──(mony㉿Mony)-[~]
└─$ echo YWNhZGVteXtwcm94aWVzX2Fs | base64 -d
academy{proxies_al
┌──(mony㉿Mony)-[~]
└─$ echo bF90aGVfd2F5XzY2MWZjMzk4fQ | base64 -d
l_the_way_661fc398}
```
# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/