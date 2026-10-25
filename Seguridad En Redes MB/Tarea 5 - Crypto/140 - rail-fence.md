# DESCRIPCIÓN:
A type of transposition cipher is the rail fence cipher. Here is one such cipher encrypted using the rail fence with 4 rails. Can you decrypt it? Download the message [here](https://challenge-files.cylabacademy.net/library/54f070d7a4fbb401b7ae06e5f41a3071cc195039368a58d9c6bb6f5a95b7913c/message.txt).
The decoded message names a phrase. Put that phrase, and nothing else, in the academy flag format: `academy{phrase}`.

# SOLUCIÓN:
#### academy{WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_8CEF1166}

El `message.txt` contiene: `Ta _7N6D86hlg:W3D_H3C31N__C16ef sHR053F38N43DE1 i33___NF`

El cifrado Rail Fence escribe el texto en zigzag a lo largo de N rieles y lo lee fila por fila. Para descifrar con 4 rieles hay que reconstruir en qué riel cae cada posición del zigzag y redistribuir el texto cifrado:

```python
def rail_fence_decode(ciphertext, rails):
    n = len(ciphertext)
    period = 2 * (rails - 1)
    pattern = []
    for i in range(n):
        cycle_pos = i % period
        pattern.append(cycle_pos if cycle_pos < rails else period - cycle_pos)
    rail_lengths = [pattern.count(r) for r in range(rails)]
    rail_strings, idx = [], 0
    for r in range(rails):
        rail_strings.append(list(ciphertext[idx:idx + rail_lengths[r]]))
        idx += rail_lengths[r]
    rail_indices = [0] * rails
    result = []
    for r in pattern:
        result.append(rail_strings[r][rail_indices[r]])
        rail_indices[r] += 1
    return ''.join(result)

msg = "Ta _7N6D86hlg:W3D_H3C31N__C16ef sHR053F38N43DE1 i33___NF"
print(rail_fence_decode(msg, 4))
# The flag is: WH3R3_D035_7H3_F3NC3_8361N_4ND_3ND_8CEF1166
```

# NOTAS ADICIONALES:
Es útil dibujar el zigzag en papel para 4 rieles antes de programar — ayuda a confirmar visualmente qué posiciones caen en qué riel y evita errores al calcular el `period`.

# REFERENCIAS:
https://en.wikipedia.org/wiki/Rail_fence_cipher
https://www.dcode.fr/rail-fence-cipher
https://webshell.cylabacademy.org/
