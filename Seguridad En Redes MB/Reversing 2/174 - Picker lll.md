# DESCRIPCIÓN:
Can you figure out how this program works to get the flag?
# SOLUCIÓN:
#### academy{7h15_15_wh47_w3_g37_w17h_u53r5_1n_ch4rg3_3e57e558}

```

┌──(mony㉿Mony)-[~/reversing2]
└─$ nc xebec.cylabacademy.net 38471
==> help

This program fixes vulnerabilities in its predecessor by limiting what
functions can be called to a table of predefined functions. This still puts
the user in charge, but prevents them from calling undesirable subroutines.

* Enter 'quit' to quit the program.
* Enter 'help' for this text.
* Enter 'reset' to reset the table.
* Enter '1' to execute the first function in the table.
* Enter '2' to execute the second function in the table.
* Enter '3' to execute the third function in the table.
* Enter '4' to execute the fourth function in the table.

Here's the current table:

1: print_table
2: read_variable
3: write_variable
4: getRandomNumber
==> 4
4
==> help

This program fixes vulnerabilities in its predecessor by limiting what
functions can be called to a table of predefined functions. This still puts
the user in charge, but prevents them from calling undesirable subroutines.

* Enter 'quit' to quit the program.
* Enter 'help' for this text.
* Enter 'reset' to reset the table.
* Enter '1' to execute the first function in the table.
* Enter '2' to execute the second function in the table.
* Enter '3' to execute the third function in the table.
* Enter '4' to execute the fourth function in the table.

Here's the current table:

1: print_table
2: read_variable
3: write_variable
4: getRandomNumber
==> 3
Please enter variable name to write: getRandomNumber
Please enter new value of variable: win
==> 4
0x61 0x63 0x61 0x64 0x65 0x6d 0x79 0x7b 0x37 0x68 0x31 0x35 0x5f 0x31 0x35 0x5f 0x77 0x68 0x34 0x37 0x5f 0x77 0x33 0x5f 0x67 0x33 0x37 0x5f 0x77 0x31 0x37 0x68 0x5f 0x75 0x35 0x33 0x72 0x35 0x5f 0x31 0x6e 0x5f 0x63 0x68 0x34 0x72 0x67 0x33 0x5f 0x33 0x65 0x35 0x37 0x65 0x35 0x35 0x38 0x7d
==>
┌──(mony㉿Mony)-[~/reversing2]
└─$
```
Convertimos de hexadecimal y saleee.

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/