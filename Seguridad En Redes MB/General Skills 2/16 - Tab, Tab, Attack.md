# DESCRIPCIÓN:
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames.
After `unzip`ing, this problem can be solved with 11 button-presses...(mostly Tab)...

[Addadshashanammu.zip](https://challenge-files.picoctf.net/c_wily_courier/56f53a4189949d066fe969e998769a4e0390123be59782c06e6c0a52c78403e2/Addadshashanammu.zip)

# SOLUCIÓN:
#### picoCTF{l3v3l_up!_t4k3_4_r35t!_fc588427} 

```
mony@Mony:/mnt/c/Users/Usuario$ wget https://challenge-files.picoctf.net/c_wily_courier/56f53a4189949d066fe969e998769a4e0390123be59782c06e6c0a52c78403e2/Addadshashanammu.zip
--2026-08-24 11:21:25--  https://challenge-files.picoctf.net/c_wily_courier/56f53a4189949d066fe969e998769a4e0390123be59782c06e6c0a52c78403e2/Addadshashanammu.zip
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 18.238.132.88, 18.238.132.49, 18.238.132.115, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|18.238.132.88|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 5166 (5.0K) [application/octet-stream]
Saving to: ‘Addadshashanammu.zip’

Addadshashanammu.zip          100%[=================================================>]   5.04K  --.-KB/s    in 0s

2026-08-24 11:21:29 (50.7 MB/s) - ‘Addadshashanammu.zip’ saved [5166/5166

mony@Mony:/mnt/c/Users/Usuario$ strings Addadshashanammu.zip | grep pico
printf("*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_fc588427}\n");

```

# NOTAS ADICIONALES:
^a - va al inicio 
^e - va al final

# REFERENCIAS:
https://webshell.cylabacademy.org/
