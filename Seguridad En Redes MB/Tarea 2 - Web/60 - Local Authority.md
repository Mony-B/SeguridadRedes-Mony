# DESCRIPCIÓN:
Can you get the flag? Go to this [website](http://chatelaine.cylabacademy.net:40472/) and see what you can discover.
How is the password checked on this website?
# SOLUCIÓN:
#### academy{j5_15_7r4n5p4r3n7_28ad420c}

Inspeccioné la página y en el style.css no salió nada, pero ingresé al secure.js y vi esta función:
```
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
```
Entonces puse la contraseña y funcionó jaja
# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/