# DESCRIPCIÓN:
Decode this [message](https://challenge-files.cylabacademy.net/library/d825fde6581b1311eafdd403da1cc96f1f98fe3fe84cd71d850310ebb3908088/message.wav) from the moon.

How did pictures from the moon landing get sent back to Earth?

What is the CMU mascot?, that might help select a RX option
# SOLUCIÓN:
####  picoCTF{beep_boop_im_in_space}

Comenzamos descargando la utilidad necesaria para hacer uso de SSTV. Después, obtenemos el audio y lo convertimos a imagen ejecutando lo siguiente:

```
wget https://challenge-files.picoctf.net/c_fickle_tempest/678ff56c639c7645276578f3a9767ec2feaed1450045dd982c525b5795f7f589/message.wav
sstv -d message.wav -o result.png
```

Al abrir la imagen resultante, notaremos que está volteada. Basta con girarla desde el editor de imágenes de Kali para que se muestre con claridad la respuesta
# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/