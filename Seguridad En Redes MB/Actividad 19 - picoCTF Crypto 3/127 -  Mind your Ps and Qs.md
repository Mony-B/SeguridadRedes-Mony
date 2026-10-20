# DESCRIPCIÓN:
In RSA, a small ee value can be problematic, but what about NN? Can you decrypt this? [values](https://challenge-files.cylabacademy.net/library/fce60438262ba3f80dcba1d40e65a745f7b587f7cc4dbc149504cfe9777487c4/values)

Bits are expensive, I used only a little bit over 100 to save money

# SOLUCIÓN:
#### academy{sma11_N_n0_g0od_a3ac7152}
```
┌──(mony㉿Mony)-[~/crypto/mindpqs]
└─$ cat values
Decrypt my super sick RSA:
c: 717608817902276639011922897702552744324264244069272484013719744328086856277690292
n: 1368992139315019955067447961537607041364451719382349005056752379702694554965203011
e: 65537

┌──(mony㉿Mony)-[~/crypto/mindpqs]
└─$ python3
Python 3.14.7 (main, Sep  5 2026, 05:55:41) [GCC 16.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> p=2074606527507983503944226222695401999839
>>> q=659880377875535146491994798968813949893149
>>> n=p*q
>>> n
1368992139315019955067447961537607041364451719382349005056752379702694554965203011
>>> tn=(p-1)*(q-1)
>>> tn
1368992139315019955067447961537607041363789764397945961926756440677503045613310024
>>> d=pow(e, -1, tn)
Traceback (most recent call last):
  File "<python-input-6>", line 1, in <module>
    d=pow(e, -1, tn)
          ^
NameError: name 'e' is not defined
>>> e=65537
>>> d=pow(e, -1, tn)
>>> d
1335528211958219033938649700488379178015379077266012711533746937374554178880433593
>>> c=717608817902276639011922897702552744324264244069272484013719744328086856277690292
>>> m=pow(c,d,n)
>>> flag=bytes.fromhex(hex(m)[2:]).decode()
Traceback (most recent call last):
  File "<python-input-12>", line 1, in <module>
    flag=bytes.fromhex(hex(m)[2:]).decode()
         ~~~~~~~~~~~~~^^^^^^^^^^^^
ValueError: fromhex() arg must contain an even number of hexadecimal digits
>>> hex_m = hex(m)[2:]
... if len(hex_m) % 2 != 0:
...     hex_m = "0" + hex_m
...
... flag = bytes.fromhex(hex_m).decode()
... print(flag)
... hex_m
... flag
...
KeyboardInterrupt
>>> hex_m = hex(m)[2:]
... if len(hex_m) % 2 != 0:
...     hex_m = "0" + hex_m
...
... flag = bytes.fromhex(hex_m).decode()
... print(flag)
...

}2517ca3a_do0g_0n_N_11ams{ymedaca
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/