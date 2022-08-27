# Level 5

## Objetivo
- Read the file, which is in "inhere" directory  with the following permissions has all of the following properties: - human-readable - 1033 bytes in size - not executable, to get the next level password.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit5
- Password: koReBOKuIDDepwhWk7jZC0RTdopnAYKh

## Solución
- Use the command find properties to find the file with the password: find -type f  -size 1033c


## Notas adicionales
- f is for regular files and that c after the size refers to the bytes.