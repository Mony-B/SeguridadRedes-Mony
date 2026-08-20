# DESCRIPCIÓN:
There is a nice program that you can talk to by using this command in a shell:
$ nc wily-courier.picoctf.net 62763, but it doesn't speak English...

Pistas:
1. You can practice using netcat with this picoGym problem: what's a netcat?
2. You can practice reading and writing ASCII with this picoGym problem: Let's Warm Up
# SOLUCIÓN:
#### picoCTF{g00d_k1tty!_n1c3_k1tty!_83691}

```
mony@Mony:~$ nc wily-courier.picoctf.net 62763
112
105
99
111
67
84
70
123
103
48
48
100
95
107
49
116
116
121
33
95
110
49
99
51
95
107
49
116
116
121
33
95
56
51
54
57
49
125
10
```

Usamos Cyber Chef para convertir a ASCII y sale la bandera:


# NOTAS ADICIONALES:
- Cyber Cher nos convierte de muuchas cosas, pegamos en input y seleccionamos el formato a convertir, arrastramos a recipe y sale.


# REFERENCIAS:
https://webshell.cylabacademy.org/
[CyberChef](https://gchq.github.io/CyberChef/)
