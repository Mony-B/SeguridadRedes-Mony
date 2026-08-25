# DESCRIPCIÓN:
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337?

# SOLUCIÓN:
#### picoCTF{learning_about_converting_values_563BAF26}
```
mony@Mony:/mnt/c/Users/Usuario$ nc fickle-tempest.picoctf.net 58317
Let us see how data is stored
light
Please give the 01101100 01101001 01100111 01101000 01110100 as a word.
...
you have 45 seconds.....

Input:
light
Please give me the  o157 o166 o145 o156 as a word.
Input:
oven
Please give me the 7375626d6172696e65 as a word.
Input:
submarine
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_563BAF26}
```

# NOTAS ADICIONALES:
Usamos pura conversión, primero de binario, luego de octal y por últmo de hexadecimal.

# REFERENCIAS:
https://webshell.cylabacademy.org/
https://gchq.github.io/CyberChef/