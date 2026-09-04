# DESCRIPCIÓN:
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at?
# SOLUCIÓN:
#### picoCTF{th3_c0nsp1r4cy_l1v3s_4d184b0d}

- **Acceder al sitio:** Entré a la página web del reto.
    
- **Preparar el navegador:** Instalé la extensión _Cookie-Editor_.
    
- **Iniciar sesión:** Ingresé utilizando credenciales aleatorias (usuario _random_) para generar una sesión inicial.
    
- **Manipular la cookie:** Abrí la extensión, busqué la cookie de mi sesión activa y cambié el valor del parámetro `admin` de `False` a `True`.
    
- **Capturar la bandera:** Guardé los cambios en la extensión, recargué la página con mis nuevos permisos de administrador y obtuve la bandera: `picoCTF{th3_c0nsp1r4cy_l1v3s_4d184b0d}`.
# NOTAS ADICIONALES:

# REFERENCIAS:
