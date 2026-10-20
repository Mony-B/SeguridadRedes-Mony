# DESCRIPCIÓN:
What happens if you have a small exponent? There is a twist though, we padded the plaintext so that (M∗∗e)(M∗∗e) is just barely larger than NN. Let's decrypt this: [values](https://challenge-files.cylabacademy.net/library/568f784f6a8067666d8f19287a5fbdb399950c8ce77edd5194c1ca539a39be03/values)

Hints:
RSA [tutorial](https://en.wikipedia.org/wiki/RSA_%28cryptosystem%29)
How could having too small of an ee affect the security of this key?
Make sure you don't lose precision, the numbers are pretty big (besides the ee value)
You shouldn't have to make _too_ many guesses
`academy` is in the decrypted message, but not at the beginning

# SOLUCIÓN:
####  academy{e_sh0u1d_b3_lArg3r_35f26e1a}

```
import gmpy2

c=570972017502631784194450516633218277941976003111543221556342590187562005279160816339875029730427788649553736779300628>

m, exacta = gmpy2.iroot(c,3)

if exacta :
        flag =  bytes.fromhex(hex(m)[2:]).decode()

print(flag)
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/