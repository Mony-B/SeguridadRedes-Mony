# DESCRIPCIÓN:
The program's source code can be downloaded [here](https://challenge-files.cylabacademy.net/library/8fffd28e5e71954eff5b80565e7f04fb0abfb5e57c7f218bc00474bf9d9ecc10/picker-IV.c). The binary can be downloaded [here](https://challenge-files.cylabacademy.net/library/8fffd28e5e71954eff5b80565e7f04fb0abfb5e57c7f218bc00474bf9d9ecc10/picker-IV).

With Python, there are no binaries. With compiled languages like C, there is source code, and there are binaries. Binaries are created from source code, they are a conversion from the human-readable source code, to the highly efficient machine language, in this case: x86_64.

How can you find the address that `win` is at?

# SOLUCIÓN:
#### academy{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_f0fec8d0}

```

┌──(mony㉿Mony)-[~/reversing2]
└─$ file picker-IV
picker-IV: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=557545489438396d48510f7d86e8a9dcd71a1601, for GNU/Linux 3.2.0, not stripped

┌──(mony㉿Mony)-[~/reversing2]
└─$ nm picker-IV
000000000040038c r __abi_tag
0000000000404068 B __bss_start
0000000000404070 b completed.0
0000000000404058 D __data_start
0000000000404058 W data_start
00000000004011d0 t deregister_tm_clones
00000000004011c0 T _dl_relocate_static_pie
0000000000401240 t __do_global_dtors_aux
0000000000403e00 d __do_global_dtors_aux_fini_array_entry
0000000000404060 D __dso_handle
0000000000403e08 d _DYNAMIC
0000000000404068 D _edata
0000000000404078 B _end
                 U exit@GLIBC_2.2.5
                 U fclose@GLIBC_2.2.5
                 U fgetc@GLIBC_2.2.5
00000000004013e0 T _fini
                 U fopen@GLIBC_2.2.5
0000000000401270 t frame_dummy
0000000000403df8 d __frame_dummy_init_array_entry
00000000004021bc r __FRAME_END__
0000000000403fe8 d _GLOBAL_OFFSET_TABLE_
                 w __gmon_start__
000000000040209c r __GNU_EH_FRAME_HDR
0000000000401000 T _init
0000000000402000 R _IO_stdin_used
                 U __isoc99_scanf@GLIBC_2.7
                 U __libc_start_main@GLIBC_2.34
0000000000401343 T main
                 U printf@GLIBC_2.2.5
0000000000401276 T print_segf_message
                 U putchar@GLIBC_2.2.5
                 U puts@GLIBC_2.2.5
0000000000401200 t register_tm_clones
                 U setvbuf@GLIBC_2.2.5
                 U signal@GLIBC_2.2.5
                 U sleep@GLIBC_2.2.5
0000000000401190 T _start
0000000000404068 B stdout@GLIBC_2.2.5
0000000000404068 D __TMC_END__
00000000004012a1 T win

┌──(mony㉿Mony)-[~/reversing2]
└─$ nc chatelaine.cylabacademy.net 22744
Enter the address in hex to jump to, excluding '0x': 00000000004012a1
You input 0x4012a1
You won!
academy{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_f0fec8d0}
```

# NOTAS ADICIONALES:

# REFERENCIAS:
https://webshell.cylabacademy.org/