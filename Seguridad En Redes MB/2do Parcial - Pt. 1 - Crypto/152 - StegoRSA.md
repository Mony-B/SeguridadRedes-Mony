# DESCRIPCIÓN:
**StegoRSA** — Cryptography (Easy) — by Yahaya Meddy · picoCTF 2026

Dan un mensaje cifrado con RSA (`flag.enc`) y una imagen (`image.jpg`). La llave pública no está, pero el enunciado insinúa que alguien fue descuidado con la llave privada. Hints: "Metadata can tell you more than you expect" y "Hex can be turned back into a key file".

# SOLUCIÓN:
#### academy{rs4_k3y_1n_1mg_9db27b2c}

1. Revisé los metadatos EXIF de `image.jpg` y en el segmento **COM (comentario JPEG)** venía un string larguísimo en hexadecimal.
2. Decodifiqué ese hex a bytes (`bytes.fromhex(...)`) y resultó ser exactamente una llave privada RSA en formato PEM:
   ```
   -----BEGIN PRIVATE KEY-----
   ...
   -----END PRIVATE KEY-----
   ```
3. Con esa llave privada descifré directo `flag.enc` (256 bytes = un solo bloque RSA con módulo de 2048 bits, padding PKCS#1 v1.5):
   ```bash
   openssl pkeyutl -decrypt -inkey private_key.pem -in flag.enc -out flag_decrypted.txt
   cat flag_decrypted.txt
   # academy{rs4_k3y_1n_1mg_9db27b2c}
   ```

Script usado para extraer la llave del comentario EXIF:
```python
data = open('image.jpg','rb').read()
idx = data.find(b'\xff\xfe')  # marcador COM de JPEG
length = (data[idx+2]<<8) + data[idx+3]
comment = data[idx+4:idx+2+length]
hexstr = comment.decode('ascii').strip()
key = bytes.fromhex(hexstr)
open('private_key.pem','wb').write(key)
```

# NOTAS ADICIONALES:
Probé primero con padding OAEP (`-pkeyopt rsa_padding_mode:oaep`) y falló con "oaep decoding error" — el cifrado usaba el padding por default de `pkeyutl` (PKCS#1 v1.5), que sí funcionó a la primera.

# REFERENCIAS:
https://webshell.cylabacademy.org/
