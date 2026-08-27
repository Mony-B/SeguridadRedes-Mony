# DESCRIPCIÓN:
Find the flag in the Python script!

# SOLUCIÓN:
#### picoCTF{7h3_r04d_l355_7r4v3l3d_ae0b80bd}

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://artifacts.picoctf.net/c/35/serpentine.py
--2026-08-27 01:03:40--  https://artifacts.picoctf.net/c/35/serpentine.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.238.132.115, 18.238.132.88, 18.238.132.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.238.132.115|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2550 (2.5K) [application/octet-stream]
Saving to: ‘serpentine.py’

serpentine.py                                   100%[=====================================================================================================>]   2.49K  --.-KB/s    in 0s

2026-08-27 01:03:40 (26.1 MB/s) - ‘serpentine.py’ saved [2550/2550]

mony@Mony:/mnt/c/Users/Usuario$ nano serpentine.py
mony@Mony:/mnt/c/Users/Usuario$ python3 serpentine.py
/mnt/c/Users/Usuario/serpentine.py:41: SyntaxWarning: "\ " is an invalid escape sequence. Such sequences will not work in the future. Did you mean "\\ "? A raw string is also an option.
  /     \      .- ~ ~ -.

    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~

Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b

Oops! I must have misplaced the print_flag function! Check my source code!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) a

-----------------------------------------------------
Keep it up!
-----------------------------------------------------


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) c
mony@Mony:/mnt/c/Users/Usuario$ nano serpentine.py
mony@Mony:/mnt/c/Users/Usuario$ nano serpentine.py
mony@Mony:/mnt/c/Users/Usuario$ nano -l serpentine.py
mony@Mony:/mnt/c/Users/Usuario$ python3 serpentine.py
/mnt/c/Users/Usuario/serpentine.py:41: SyntaxWarning: "\ " is an invalid escape sequence. Such sequences will not work in the future. Did you mean "\\ "? A raw string is also an option.
  /     \      .- ~ ~ -.

    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~

Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b
picoCTF{7h3_r04d_l355_7r4v3l3d_ae0b80bd}
a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) c
mony@Mony:/mnt/c/Users/Usuario$
```

# NOTAS ADICIONALES:
- Aquí sí le pedí ayuda a Gemini porque me perdí, no encontraba nada en el nano, hasta que me dijo que era la función print_flag() ya existía, pero no la llamábamos y mejor se usaba un mensaje que no servía, pero ya quedó.

# REFERENCIAS:
https://webshell.cylabacademy.org/