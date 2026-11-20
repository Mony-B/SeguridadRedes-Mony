# DESCRIPCIÓN:
Can you get the flag? Download this binary (gdbme).
Instrucciones de test drive:
* $ chmod +x gdbme
* $ gdb gdbme
* (gdb) layout asm
* (gdb) break *(main+99)
* (gdb) run
* (gdb) jump *(main+104)

# SOLUCIÓN:
#### academy{d3bugg3r_dr1v3_ff5329f1}

1. Dar permisos de ejecución al binario: `chmod +x gdbme`
2. Abrir con gdb: `gdb gdbme`
3. Poner un breakpoint justo antes de la llamada a `sleep`: `break *(main+99)`
4. Correr el programa: `run`
5. Al llegar al breakpoint, saltar la instrucción de `sleep` directo a la siguiente: `jump *(main+104)`
6. El programa continúa su ejecución normal (desencripta el string guardado en el stack con `rotate_encrypt` y lo imprime), mostrando la flag en pantalla sin esperar el `sleep(100000)`.

```
(gdb) break *(main+99)
Breakpoint 1 at 0x132a
(gdb) run
Breakpoint 1, 0x000055555555532a in main ()
(gdb) jump *(main+104)
academy{d3bugg3r_dr1v3_ff5329f1}
[Inferior 1 (process 163) exited normally]
```

# NOTAS ADICIONALES:
Al desensamblar `main` se ve que en `main+99` hay un `call sleep@plt` con `edi = 0x186a0` (100000 segundos ≈ 27.7 horas). Sin el `jump`, habría que esperar ese tiempo para ver la flag. El salto evita por completo esa instrucción.

# REFERENCIAS:
N/A
