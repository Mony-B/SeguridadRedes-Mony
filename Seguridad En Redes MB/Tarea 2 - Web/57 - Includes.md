# DESCRIPCIÓN:

Can you get the flag? Go to this [website](http://chatelaine.cylabacademy.net:15412/) and see what you can discover.
Hint: Is there more code than what the inspector initially shows?
# SOLUCIÓN:
Inspeccionamos la página y unimos las claves:
#### academy{1nclu51v17y_1of2_f7w_2of2_64d6df37}

```
[view-source:chatelaine.cylabacademy.net:15412](view-source:http://chatelaine.cylabacademy.net:15412/)

/style.css:
body {
  background-color: lightblue;
}

/*  academy{1nclu51v17y_1of2_  */

/script.js:
function greetings()
{
  alert("This code is in a separate file!");
}

//  f7w_2of2_64d6df37}
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/