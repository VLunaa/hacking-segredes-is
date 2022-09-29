# Irish-Name-Repo 1

## Descripción
There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!
## Solución
- Sólo hay que revisar las SQL injections, que son consideradas una de las top 10 vulnerabilidades de sistemas web, usando ' OR '1'='1 como password podemos acceder.

picoCTF{s0m3_SQL_fb3fe2ad}