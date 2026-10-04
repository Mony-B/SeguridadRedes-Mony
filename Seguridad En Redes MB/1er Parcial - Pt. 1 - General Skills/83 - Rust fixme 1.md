# DESCRIPCIÓN:
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!

Download the Rust code [here](https://challenge-files.cylabacademy.net/library/b9cfc84c442958b8ac848ddc0692bed9ef01a15877b8d37f36afbe68b5849acc/fixme1.tar.gz).

Cargo is Rust's package manager and will make your life easier. See the getting started page [here](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html)
[println!](https://doc.rust-lang.org/std/macro.println.html)

Rust has some pretty great compiler error messages. Read them maybe?

# SOLUCIÓN:
#### academy{4r3_y0u_4_ru$t4c30n_n0w?}

Primero, descargué el archivo con `wget` y me moví a la carpeta `src`. Después, abrí el código con `nano main.rs` para corregir unos errores: agregué un `;` al final de la línea 5, completé la palabra `return` en la línea 18, y puse unas llaves `{}` adentro de las comillas en la línea 25. Ya con los cambios guardados, usé el comando `cargo build` y, por último, ejecuté `cargo run` para que me soltara la bandera.

```
┌──(mony㉿Mony)-[~/fixme1]
└─$ cargo run
   Compiling rust_proj v0.1.0 (/home/mony/fixme1)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 1.39s
     Running `target/debug/rust_proj`
academy{4r3_y0u_4_ru$t4c30n_n0w?}
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/