# DESCRIPCIÓN:
There is some interesting information hidden around this site. Can you find it?

You should have enough hints to find the files, don't run a brute forcer.
# SOLUCIÓN:
#### picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_9588550}

# NOTAS ADICIONALES:
```
Primero inspeccionamos el html y scamos la parte 1, después, el .css y se encontraba la parte 2, enseguida con ayuda de Jimmy descubrimos las otras partes:

http://wily-courier.picoctf.net:51811/robots.txt

┌──(mony㉿Mony)-[~]
└─$ curl -s http://wily-courier.picoctf.net:51811/.htaccess
# Part 4: 3s_2_lO0k
# I love making websites on my Mac, I can Store a lot of information there.

┌──(mony㉿Mony)-[~]
└─$ curl -s http://wily-courier.picoctf.net:51811/.DS_Store
Congrats! You've completed the scavenger hunt! Part 5: _9588550}
```
# REFERENCIAS:
[wily-courier.picoctf.net:51811/
https://gemini.google.com/

