# DESCRIPCIÓN:
**Enhance!** — Forensics (Medium) — by LT 'syreal' Jones · picoCTF 2022

Dan un archivo `drawing.flag.svg` (una imagen vectorial de Inkscape). Hay que encontrar la flag dentro.

# SOLUCIÓN:
#### academy{3nh4nc3d_001f8059}

Al revisar el SVG como texto plano no aparece `academy{` directo, pero tiene varios elementos `<tspan>` con texto. El detalle está en que el `font-size` de ese texto es **`0.00352781`** — microscópico, invisible a simple vista o incluso con zoom normal (de ahí el nombre "Enhance!", como el meme de zoomear una imagen pixeleada).

Extraje el contenido de todos los `<tspan>` con una expresión regular:
```python
import re
content = open('drawing.flag.svg').read()
tspans = re.findall(r'<tspan[^>]*>(.*?)</tspan>', content, re.S)
for t in tspans:
    print(repr(t))
```
Resultado (cada letra/carácter de la flag viene en un `tspan` separado, con espacios sueltos entre letras):
```
'a ' 'c ' 'a ' 'd ' 'e ' 'm ' 'y { 3 n h 4 n ' 'c 3 d _ 0 0 1 f 8 0 5 9 }'
```

Concatenando todo y quitando los espacios queda la flag completa:
```python
flag = ''.join(tspans).replace(' ', '')
# academy{3nh4nc3d_001f8059}
```

# NOTAS ADICIONALES:
No fue necesario renderizar/abrir la imagen ni hacer zoom visual — como un SVG es texto plano (XML), el contenido de cada `<text>`/`<tspan>` se puede leer directo del código fuente sin importar qué tan chiquito se vea el texto al renderizarlo.

# REFERENCIAS:
https://webshell.cylabacademy.org/
