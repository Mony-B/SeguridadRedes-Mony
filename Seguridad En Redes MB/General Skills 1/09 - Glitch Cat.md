# DESCRIPCIÓN:
Our flag printing service has started glitching!

Pistas:
1. ASCII is one of the most common encodings used in programming
2. We know that the glitch output is valid Python, somehow!
3. Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

# SOLUCIÓN:

#### picoCTF{gl17ch_m3_n07_bda68f75}

```
mony@Mony:~$ nc saturn.picoctf.net 58202
'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'

mony@Mony:~$ python3
Python 3.14.4 (main, Apr  8 2026, 04:02:31) [GCC 15.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(\
0x35) + '}'
'picoCTF{gl17ch_m3_n07_bda68f75}'
>>>
```

# NOTAS ADICIONALES:
- Python concatena cadenas con: "+"
- chr() es una función de Python que convierte un número a su caracter correspondiente ASCII
- Esto fue simplemente una suma de cadenas y caracteres

# REFERENCIAS:
https://webshell.cylabacademy.org/