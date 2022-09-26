# Where are the robots

## Descripción
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/15796/` ([link](https://jupiter.challenges.picoctf.org/problem/15796/)) or http://jupiter.challenges.picoctf.org:15796
## Solución
- Se inspecciona al elemento y en las tablas de Storage, se busca al usuario de Admin, se cambia el valor false por true, recarga la página y aparecerá la bandera.

picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}