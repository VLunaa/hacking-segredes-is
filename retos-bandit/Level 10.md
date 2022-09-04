# Level 10

## Objetivo
- Find the password in the data.txt file, which contains base 64 encoded data.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit10
- Password: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
- G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

## Solución
- We can use cat and -- decode to unencrypt the password. 

bandit10@bandit:~$ cat data.txt | base64 --decode
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$
## Notas adicionales
--decode to unencrypt