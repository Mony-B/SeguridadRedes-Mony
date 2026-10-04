# DESCRIPCIÓN:
BookShelf Pico, my premium online book-reading service.

I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book! Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/8735cd07fe79316e7baf620ba224e3c344ec8ad124aefcbfffddf98786555747/bookshelf-pico.zip).

Website can be accessed [here!](http://chatelaine.cylabacademy.net:35748/).

Maybe try to find the JWT Signing Key ("secret key") in the source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?

The 'role' and 'userId' fields in the JWT can be of interest to you!

The 'controllers', 'services' and 'security' java packages in the given source code might need your attention. We've provided a README.md file that contains some documentation.

Upgrade your 'role' with the _new_ (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.

# SOLUCIÓN:
#### academy{w34k_jwt_n0t_g00d_5e81272f}

Entré con `user/user` y revisé el Local Storage con F12. Vi que mi usuario tenía el rol `Free`. Luego revisé el código y encontré que la clave del JWT era `"1234"`, así que modifiqué el token para poner el rol como `Admin` y poder intentar acceder al libro `Flag`.
![[Pasted image 20261004003555.png]]

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/