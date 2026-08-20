# DESCRIPCIÓN: 
This file has a flag in plain sight (aka "in-the-clear").

Pistas:
1. Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.
2. To get the file accessible in your shell, enter the following in the Terminal prompt: $ wget and a link to the flag. The link can be copied from the details section.
3. $ man cat
# SOLUCIÓN:

#### picoCTF{s4n1ty_v3r1f13d_9b8fa0bc}
```
monybichiyal-academy@webshell:~$ cat flag | grep picoCTF
picoCTF{s4n1ty_v3r1f13d_9b8fa0bc}
monybichiyal-academy@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/1a44abd1b8ea719b212d4645d5e9805a9db2e9062845609829d5d15e8e7d578c/flag
--2026-08-20 05:22:52--  https://challenge-files.picoctf.net/c_wily_courier/1a44abd1b8ea719b212d4645d5e9805a9db2e9062845609829d5d15e8e7d578c/flag
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.64, 3.160.5.40, 3.160.5.95, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag.1'

flag.1                                          100%[=====================================================================================================>]      34  --.-KB/s    in 0s      

2026-08-20 05:22:52 (601 KB/s) - 'flag.1' saved [34/34]

monybichiyal-academy@webshell:~$ cat flag.1 | grep picoCTF
picoCTF{s4n1ty_v3r1f13d_9b8fa0bc}

```

# NOTAS ADICIONALES:
Nuevamente usamos el wget, cat y grep

# REFERENCIAS:
https://webshell.cylabacademy.org/
https://challenge-files.picoctf.net/c_wily_courier/1a44abd1b8ea719b212d4645d5e9805a9db2e9062845609829d5d15e8e7d578c/flag