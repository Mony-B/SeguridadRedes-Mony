## DESCRIPCIÓN: 
The numbers... what do they mean? Nos proporcionan una imagen con una secuencia de números y unas llaves. 16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 } 

## SOLUCIÓN:
#### picoCTF{thenumbersmason}
```┌──(mony㉿Mony)-[~] └─$ python3 -c "print(''.join([chr(int(x)+96) if x.isdigit() else x for x in '20 8 5 14 21 13 2 5 18 19 13 1 19 15 14'.split()]))" ```
## NOTAS ADICIONALES: 
Es un cifrado de sustitución básico A1Z26, donde cada número corresponde directamente a su posición en el alfabeto inglés (A=1, B=2, C=3, ..., Z=26). 
## REFERENCIAS: 
https://gchq.github.io/CyberChef/#recipe=A1Z26_Cipher_Decode()