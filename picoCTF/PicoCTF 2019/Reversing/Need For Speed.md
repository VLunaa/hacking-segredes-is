## Descripción
The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/27dd5548b14661f65ce3ac6a8a8f575b/need-for-speed).

## Solución
- Gnu Project Debugger es una herramienta que permite depurar varios lenguajes, por lo que podemos correr la función de imprimir la bandera saltándonos el timer.

```
Breakpoint 1, 0x000055555540091e in main ()

(gdb) disassemble main

Dump of assembler code for function main:

   0x000055555540091a <+0>:     push   rbp

   0x000055555540091b <+1>:     mov    rbp,rsp

=> 0x000055555540091e <+4>:     sub    rsp,0x10

   0x0000555555400922 <+8>:     mov    DWORD PTR [rbp-0x4],edi

   0x0000555555400925 <+11>:    mov    QWORD PTR [rbp-0x10],rsi

   0x0000555555400929 <+15>:    mov    eax,0x0

   0x000055555540092e <+20>:    call   0x5555554008d8 <header>

   0x0000555555400933 <+25>:    mov    eax,0x0

   0x0000555555400938 <+30>:    call   0x55555540082f <set_timer>

   0x000055555540093d <+35>:    mov    eax,0x0

   0x0000555555400942 <+40>:    call   0x55555540087d <get_key>

   0x0000555555400947 <+45>:    mov    eax,0x0

   0x000055555540094c <+50>:    call   0x5555554008ac <print_flag>

   0x0000555555400951 <+55>:    mov    eax,0x0

   0x0000555555400956 <+60>:    leave  

   0x0000555555400957 <+61>:    ret    

End of assembler dump.

(gdb) call (int) get_key()

Creating key...

  

Finished

$1 = 9

(gdb)

Creating key...

Finished

$2 = 9

(gdb) call (int) print_flag()

Printing flag:

PICOCTF{Good job keeping bus #1f2ac4ec speeding along!}

$3 = 56

(gdb)
```

