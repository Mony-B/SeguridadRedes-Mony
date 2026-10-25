# DESCRIPCIÓN:
It seems that another encrypted message has been intercepted. The encryptor seems to have learned their lesson though and now there isn't any punctuation! Can you still crack the cipher? Download the message [here](https://challenge-files.cylabacademy.net/library/750a77d87fa924d5ec8a173d7354dd57792a1597cab3d89fa7443608ba0a35e7/message.txt).

# SOLUCIÓN:
#### academy{N6R4M_4N41Y515_15_73D10U5_FD56C357}

Sin espacios ni puntuación, el ataque de frecuencia por palabras no funciona — tocó resolverlo con un **solver de sustitución monoalfabética** (hill-climbing / simulated annealing) usando estadísticas de cuadrigramas de inglés para evaluar qué tan "legible" es cada candidato de desencriptado:

```python
import re, math, random, string
from collections import defaultdict

# corpus de referencia en inglés para sacar frecuencias de cuadrigramas
text = open('corpus_en.txt', encoding='utf-8', errors='ignore').read().upper()
text = re.sub(r'[^A-Z]', '', text)
quad_counts = defaultdict(int)
for i in range(len(text) - 3):
    quad_counts[text[i:i+4]] += 1
total = sum(quad_counts.values())
floor = math.log(0.01 / total)
quad_log = {k: math.log(v/total) for k, v in quad_counts.items()}

def score(s):
    return sum(quad_log.get(s[i:i+4], floor) for i in range(len(s)-3))

alphabet = list(string.ascii_uppercase)
cipher = open('message.txt').read().upper()

best = None
for restart in range(12):
    mapping = dict(zip(alphabet, random.sample(alphabet, 26)))
    cur = score(''.join(mapping.get(c, c) for c in cipher))
    for _ in range(20000):
        a, b = random.sample(alphabet, 2)
        mapping[a], mapping[b] = mapping[b], mapping[a]
        new = score(''.join(mapping.get(c, c) for c in cipher))
        if new > cur or random.random() < math.exp((new - cur) / 50):
            cur = new
        else:
            mapping[a], mapping[b] = mapping[b], mapping[a]
    if best is None or cur > best[0]:
        best = (cur, dict(mapping))

print(''.join(best[1].get(c, c) for c in cipher))
```

El texto descifrado habla de competencias de seguridad para high school (CyberPatriot, US Cyber Challenge) y termina con:
```
THE FLAG IS ACADEMY{N6R4M_4N41Y515_15_73D10U5_FD56C357}
```

# NOTAS ADICIONALES:
El hint de "analizar grupos de letras" apunta justo a esto: sin espacios, hace falta un análisis de n-gramas (aquí cuadrigramas) en vez de un ataque de frecuencia por palabra individual.

# REFERENCIAS:
https://en.wikipedia.org/wiki/N-gram
https://en.wikipedia.org/wiki/Frequency_analysis
https://quipqiup.com
https://webshell.cylabacademy.org/
