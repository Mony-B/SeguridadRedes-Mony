# DESCRIPCIÓN:
**Riddle Registry** — Forensics (Easy) — by Prince Niyonshuti N. · picoMini by CMU-Africa

Dan un PDF (`confidential.pdf`) cuyo texto visible es solo relleno sin sentido. El hint dice que no hay que fiarse del texto visible, la pista está "más allá de la superficie" — en los metadatos.

# SOLUCIÓN:
#### academy{puzzl3d_m3tadata_f0und!_2d947385}

Con `strings` sobre el PDF, en los metadatos del documento apareció el campo `/Author` con un valor en **Base64**:
```bash
strings confidential.pdf | grep -i "Author"
# /Author (YWNhZGVteXtwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV8yZDk0NzM4NX0\075)
```
(el `\075` al final es la notación octal de PDF para el carácter `=`, típico relleno de Base64).

Decodifiqué directo:
```python
import base64
base64.b64decode('YWNhZGVteXtwdXp6bDNkX20zdGFkYXRhX2YwdW5kIV8yZDk0NzM4NX0=').decode()
# academy{puzzl3d_m3tadata_f0und!_2d947385}
```

# NOTAS ADICIONALES:
El PDF fue generado con `PyPDF2` (se ve en `/Producer`), probablemente con un script que mete la flag directo en el campo de autor del documento. No hizo falta ninguna herramienta especial — `strings` + `grep` sobre los metadatos del PDF es suficiente cuando se sabe que la pista "está en los metadatos".

# REFERENCIAS:
https://webshell.cylabacademy.org/
