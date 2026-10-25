# DESCRIPCIÓN:
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again. Download the message [here](https://challenge-files.cylabacademy.net/library/7bfa985513e099d32240b37e499262d5fb6147c074a8ee5ecd932c14deb05ac7/message.txt).

# SOLUCIÓN:
#### academy{FR3QU3NCY_4774CK5_4R3_C001_7B0043A0}

A diferencia de substitution0, aquí no viene la clave al inicio. Toca un ataque de frecuencia y anclas por palabras conocidas.

**Anclas usadas:**
- `ktkuxvb{...}` = `academy{...}` → k→a, t→c, u→d, x→e, v→m, b→y
- `TAHd` = `CTFs` → T→C, A→T, H→F, d→s
- `aqx` = `the` → q→h (a ya conocida)
- `hzko` = `flag` → h→f, z→l, o→g

Con esas anclas se completa el mapeo letra por letra hasta descifrar todo el párrafo (que resulta ser una explicación de qué son los CTFs):

```python
known = {
    'k':'a', 't':'c', 'u':'d', 'x':'e', 'v':'m', 'b':'y',
    'a':'t', 'h':'f', 'd':'s', 'q':'h', 'z':'l', 'o':'g',
    'l':'r', 'e':'o', 'f':'p', 'c':'u', 'r':'n', 'i':'i',
    'n':'k', 'm':'q', 's':'b'
}
for k, v in list(known.items()):
    known[k.upper()] = v.upper()

text = open('message.txt').read()
print(''.join(known.get(c, c) for c in text))
# ... For this problem, the flag is: academy{FR3QU3NCY_4774CK5_4R3_C001_7B0043A0}
```

# NOTAS ADICIONALES:
Resultó ser exactamente el mismo alfabeto de sustitución usado en otras instancias del mismo reto — una vez armado el mapa completo, se puede reutilizar directo.

# REFERENCIAS:
https://en.wikipedia.org/wiki/Frequency_analysis
https://quipqiup.com
https://webshell.cylabacademy.org/
