# DESCRIPCIÓN:
How about some hide and seek?

Download this file [here](https://challenge-files.cylabacademy.net/library/db9453955f3bd6e863102fd10b5c3b1e6ce0517e7c648b76d86172eed079e028/unknown.zip).

How can you view the information about the picture?

If something isn't in the expected form, maybe it deserves attention?

# SOLUCIÓN:
#### academy{ME74D47A_HIDD3N_a81d9431}

```

┌──(mony㉿Mony)-[~/forensic]
└─$ unzip unknown.zip
Archive:  unknown.zip
  inflating: ukn_reality.jpg

┌──(mony㉿Mony)-[~/forensic]
└─$ ls
academy.flag.png  challenge.zip  _flag.png.extracted  unknown.zip
cat.jpg           flag.png       ukn_reality.jpg

┌──(mony㉿Mony)-[~/forensic]
└─$ explorer.exe ukn_reality.jpg

┌──(mony㉿Mony)-[~/forensic]
└─$ exiftool ukn_reality.jpg
ExifTool Version Number         : 13.55
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2026:09:22 23:17:47-06:00
File Access Date/Time           : 2026:10:17 20:09:11-06:00
File Inode Change Date/Time     : 2026:10:17 20:08:32-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 12.76
Attribution URL                 : YWNhZGVteXtNRTc0RDQ3QV9ISUREM05fYTgxZDk0MzF9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4

┌──(mony㉿Mony)-[~/forensic]
└─$ echo "YWNhZGVteXtNRTc0RDQ3QV9ISUREM05fYTgxZDk0MzF9Cg" | base64 -d
academy{ME74D47A_HIDD3N_a81d9431}
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/