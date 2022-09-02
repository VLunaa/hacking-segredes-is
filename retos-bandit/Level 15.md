# Level 15

## Objetivo
- find the password that can be obtained by submitting the password of the current level to port 30001 on localhost using SSL encryption.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit15
- Password: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Solución
- With openSSL you can make a command that helps you connect to port 30001, then put the actual password and you will get the next one. "openssl s_client -connect localhost:30001 -ign_eof"

## Notas adicionales
