
# DESCRIPCIÓN:
Connect to this PostgreSQL server and find the flag! `psql -h xebec.cylabacademy.net -p 12728 -U postgres pico`

Password is `postgres`

What does a SQL database contain?

# SOLUCIÓN:
#### academy{L3arN_S0m3_5qL_t0d4Y_d4538dde}

Ingresamos puerto, user y contraseña, ejecutamos comando básico que revela contenido en sql y sale:
```
┌──(mony㉿Mony)-[~]
└─$ psql -h xebec.cylabacademy.net -p 12728 -U postgres pico
Password for user postgres:
psql (18.6 (Debian 18.6-3))
Type "help" for help.

pico=# SELECT * FROM flags;
 id | firstname | lastname  |                address
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | academy{L3arN_S0m3_5qL_t0d4Y_d4538dde}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=#
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/