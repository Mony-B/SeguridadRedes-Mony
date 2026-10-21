# DESCRIPCIÓN:
How about we take you on an adventure on exploring certificate signing requests Take a look at this CSR file [here](https://challenge-files.cylabacademy.net/library/5106e781bbd36dcc1335e6ad005b28467f171c07351768e71d06bf9cafb3c1f6/readmycert.csr).

Download the certificate signing request and try to read it.

# SOLUCIÓN:
#### academy{read_mycert_52274715}

```

┌──(mony㉿Mony)-[~/crypto]
└─$ file readmycert.csr
readmycert.csr: PEM certificate request

┌──(mony㉿Mony)-[~/crypto]
└─$ openssl req -in readmycert.csr -noout -text
Certificate Request:
    Data:
        Version: 1 (0x0)
        Subject: CN=academy{read_mycert_52274715}, name=ctfPlayer
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                Public-Key: (2048 bit)
                Modulus:
                    00:b0:20:25:63:43:15:96:04:29:83:d1:a3:23:5a:
                    1d:bc:aa:1d:44:f8:30:6a:42:15:3e:bb:76:48:c7:
                    7d:f6:be:69:8c:e6:c0:93:00:33:4c:3e:57:be:da:
                    cb:e5:bb:a4:d2:39:9b:0b:43:ee:7b:c9:59:65:96:
                    00:59:75:29:9b:7d:5f:90:23:e9:a7:69:29:cb:58:
                    8c:f3:06:c8:76:1a:ef:b8:42:1a:eb:cc:8e:6e:79:
                    dd:80:fc:2a:07:89:07:7c:ca:00:9a:53:10:40:1d:
                    7e:15:cd:98:35:2d:92:14:0d:cf:45:95:92:0b:3b:
                    be:45:25:04:be:5c:6e:4f:59:7f:e1:a0:9c:26:39:
                    c5:49:68:29:7e:4c:ee:8f:74:c4:97:e3:02:5b:c1:
                    e1:32:48:cf:25:5b:a0:17:06:f2:ac:bd:5b:8a:bc:
                    5e:2e:8d:75:59:50:68:7b:13:ae:f9:f4:43:b9:bf:
                    6f:1e:38:a1:52:ab:9b:78:7a:0c:79:21:4a:ff:3e:
                    9d:d9:d1:9b:b2:72:7b:46:a5:2c:f8:f5:e9:21:03:
                    9e:4d:7d:5c:44:25:ab:14:d8:56:83:9d:ab:3f:b4:
                    af:5a:34:fe:21:aa:45:45:78:b8:d1:bb:89:65:b7:
                    d4:63:b9:df:d5:3a:7a:c7:c4:32:c5:d6:fd:17:23:
                    b1:af
                Exponent: 65537 (0x10001)
        Attributes:
            Requested Extensions:
                X509v3 Extended Key Usage:
                    TLS Web Client Authentication
    Signature Algorithm: sha256WithRSAEncryption
    Signature Value:
        27:f8:30:6a:c4:3b:23:b3:60:43:8f:07:3a:f4:a6:3a:fe:15:
        59:35:f8:86:b4:82:df:59:10:56:49:50:13:4d:c1:7f:68:d4:
        95:77:80:13:b7:bf:bb:97:7c:c1:56:d3:7b:92:9b:8e:c9:d7:
        47:0d:ae:86:ec:e2:44:22:38:72:1e:e8:b8:b9:8f:5a:9b:e4:
        1e:ac:2b:05:d4:be:49:00:bb:06:e3:7c:81:af:54:1e:bd:16:
        6f:cb:78:aa:74:3e:99:98:a2:f6:c6:13:34:3a:37:d4:a4:c9:
        95:c3:a7:b0:0f:06:33:f6:f5:03:87:12:e1:bf:f4:29:76:fe:
        fe:21:ac:89:bb:70:c4:e1:02:70:4b:1d:22:c9:fa:58:40:44:
        60:77:66:fa:8d:86:60:19:f4:eb:66:ea:8e:8d:5b:ed:af:1c:
        fb:54:0b:b1:bc:6e:5d:fb:a9:59:a6:36:78:3c:ef:4d:00:3c:
        a5:4e:80:05:25:ee:ec:05:d8:8c:c2:75:91:5a:6a:3a:ff:7a:
        42:1d:4d:b8:fc:b2:e8:15:1b:61:38:60:07:db:b5:d1:e3:92:
        e7:f1:3c:3d:50:22:3a:16:47:5c:7b:80:2c:36:e6:e8:2a:c7:
        88:5f:28:31:aa:f4:81:c0:68:15:70:15:22:e1:64:04:ca:a1:
        d1:89:bf:c3

┌──(mony㉿Mony)-[~/crypto]
└─$
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/