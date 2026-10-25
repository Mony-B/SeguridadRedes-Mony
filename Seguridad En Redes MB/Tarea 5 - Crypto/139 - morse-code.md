# DESCRIPCIÓN:
Morse code is well known. Can you decrypt this? Download the file [here](https://challenge-files.cylabacademy.net/library/3728bfa4e8314fddd6b7e9f3fae9cb453b459a0bd4b3a29a9224701152f0cd89/morse_chal.wav).
Wrap your answer with academy{}, put underscores in place of pauses, and use all uppercase.

# SOLUCIÓN:
#### academy{WH47_H47H_90D_W20U9H7}

El archivo es un `.wav` mono con señales de código Morse. Se analiza la energía del audio en ventanas de 10ms para detectar pulsos (encendido/apagado):

```
┌──(mony㉿Mony)-[~/crypto]
└─$ python3
>>> import wave, numpy as np
>>> w = wave.open('morse_chal.wav')
>>> frames = w.readframes(w.getnframes())
>>> data = np.frombuffer(frames, dtype=np.int16).astype(float)
>>> sr = w.getframerate()
>>> window = int(sr * 0.01)
>>> energy = np.array([np.sum(data[i:i+window]**2) for i in range(0, len(data)-window, window)])
>>> threshold = energy.max() * 0.05
>>> binary = (energy > threshold).astype(int)
```

Las duraciones (en ventanas de 10ms) definen el alfabeto Morse:
- Encendido: 10 = punto `.`, 30 = raya `-`
- Apagado: 10 = separador intra-letra, 40 = separador de letra, 80 = separador de palabra (`_`)

```
>>> # tras decodificar runs y mapear con la tabla Morse estándar:
WH47_H47H_90D_W20U9H7
```

El mensaje es "WHAT HATH GOD WROUGHT" en leet speak — la primera frase enviada por telégrafo en código Morse (Samuel Morse, 1844).

# NOTAS ADICIONALES:
Audacity también funciona muy bien para ver visualmente los pulsos y confirmar las duraciones a simple vista, tal como sugiere el hint.

# REFERENCIAS:
https://es.wikipedia.org/wiki/C%C3%B3digo_Morse
https://en.wikipedia.org/wiki/What_hath_God_wrought
https://webshell.cylabacademy.org/
