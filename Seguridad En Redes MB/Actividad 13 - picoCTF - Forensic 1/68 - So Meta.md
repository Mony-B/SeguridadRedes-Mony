# DESCRIPCIÓN:
Find the flag in this [picture](https://challenge-files.cylabacademy.net/library/7ed1ce00a2228a823941d5586923914d39f3085ee0a9a432555322b8dfa9f92e/pico_img.png).

Hints:
What does meta mean in the context of files?
Ever heard of metadata?

# SOLUCIÓN: 
#### academy{s0_m3ta_b52e28f5}

Usamos el comando exiftool, en el apartado de artist encontraremos la flag
```
┌──(mony㉿Mony)-[~]
└─$ exiftool pico_img.png
ExifTool Version Number         : 13.55
File Name                       : pico_img.png
Directory                       : .
File Size                       : 109 kB
File Modification Date/Time     : 2026:09:22 19:49:10-06:00
File Access Date/Time           : 2026:09:29 08:55:50-06:00
File Inode Change Date/Time     : 2026:09:29 08:55:50-06:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Artist                          : academy{s0_m3ta_b52e28f5}
Image Size                      : 600x600
Megapixels                      : 0.360
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/