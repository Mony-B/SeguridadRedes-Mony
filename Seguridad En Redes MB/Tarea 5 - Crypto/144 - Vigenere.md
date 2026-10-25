# DESCRIPCIÓN:
Can you decrypt this message? Decrypt this [message](https://challenge-files.cylabacademy.net/library/848831bc0df5e68fe8f320c91c47f635bce35a7c8236c696f9478bfaf39cfd10/cipher.txt) using this key "CYLAB".

# SOLUCIÓN:
#### academy{D0NT_US3_V1G3N3R3_C1PH3R_42ccuf9c}

El `cipher.txt` contiene: `caldfow{O0NU_WQ3_G1G3O3T3_A1AH3S_42eaff9d}`

El cifrado Vigenere desplaza cada letra del texto plano según la letra correspondiente de la clave (que se repite cíclicamente). Para descifrar: `P_i = (C_i - K_i + 26) mod 26`. Los caracteres no alfabéticos se dejan igual.

```python
def vigenere_decrypt(ciphertext, key):
    key = key.upper()
    result, key_index = [], 0
    for char in ciphertext:
        if char.isalpha():
            base = ord('A') if char.isupper() else ord('a')
            shift = ord(key[key_index % len(key)]) - ord('A')
            result.append(chr((ord(char) - base - shift + 26) % 26 + base))
            key_index += 1
        else:
            result.append(char)
    return ''.join(result)

ciphertext = "caldfow{O0NU_WQ3_G1G3O3T3_A1AH3S_42eaff9d}"
print(vigenere_decrypt(ciphertext, "CYLAB"))
# academy{D0NT_US3_V1G3N3R3_C1PH3R_42ccuf9c}
```

El mensaje descifrado dice "DON'T USE VIGENERE CIPHER" — ironizando sobre la debilidad del propio cifrado usado en el reto.

# NOTAS ADICIONALES:
El cifrado Vigenere fue considerado "le chiffre indéchiffrable" durante siglos, pero hoy es trivialmente rompible incluso sin conocer la clave (índice de coincidencia, test de Kasiski). Con la clave dada, basta la operación inversa letra por letra.

# REFERENCIAS:
https://en.wikipedia.org/wiki/Vigen%C3%A8re_cipher
https://webshell.cylabacademy.org/
