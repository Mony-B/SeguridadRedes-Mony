# DESCRIPCIÓN:
**Timeline 1** — Forensics (Medium) — by LT 'syreal' Jones · picoCTF 2026

Igual que Timeline 0: imagen de disco (`timeline-1-partition4.img.gz`), hay que encontrar la flag y envolverla en `academy{}`. Esta vez los hints apuntan a mirar los timestamps **recientes** (no los viejos), cerca de una acción anti-forense, filtrando por líneas con las 4 banderas `macb` juntas.

# SOLUCIÓN:
#### academy{573417h13r_7h4n_7h3_1457_58527bb222}

1. Mismo proceso de siempre con Sleuthkit:
   ```bash
   gunzip timeline-1-partition4.img.gz
   fls -r -m "/" timeline-1-partition4.img > body1.txt
   mactime -b body1.txt > timeline1.txt
   grep "macb" timeline1.txt | tail -30
   ```
2. En las últimas entradas con `macb` (las más recientes), dos archivos saltan a la vista entre puros archivos de sistema normales (certificados SSL, symlinks de `busybox`, etc.):
   - `/etc/chat` (49 bytes) — nombre que no corresponde a ningún archivo estándar de Alpine/Linux.
   - `/root/.ash_history` (solo **9 bytes**, contenido `poweroff`) — un historial de shell casi vacío es la señal clásica de que alguien borró su historial (**acción anti-forense**) y solo quedó el último comando que alcanzó a correr antes de limpiarlo.
3. Extraje el contenido de `/etc/chat` por su inodo (32716):
   ```bash
   icat timeline-1-partition4.img 32716
   # NTczNDE3aDEzcl83aDRuXzdoM18xNDU3XzU4NTI3YmIyMjIK
   ```
4. Era Base64:
   ```python
   import base64
   base64.b64decode('NTczNDE3aDEzcl83aDRuXzdoM18xNDU3XzU4NTI3YmIyMjIK').decode()
   # 573417h13r_7h4n_7h3_1457_58527bb222
   ```
5. Envolví en el formato pedido: `academy{573417h13r_7h4n_7h3_1457_58527bb222}`

# NOTAS ADICIONALES:
`/root/.ash_history` con solo `poweroff` adentro fue la pista de contexto: confirma que hubo una sesión de shell real en esa máquina (probablemente del atacante), y que se limpió el historial después de dejar caer el archivo `/etc/chat` — de ahí el hint de "revisar timestamps cerca de una acción anti-forense". El archivo con la flag en sí (`/etc/chat`) no tenía nada de especial en su timestamp, pero su *ubicación y nombre* fuera de lugar fue suficiente para identificarlo entre el ruido de archivos legítimos del sistema.

# REFERENCIAS:
https://webshell.cylabacademy.org/
