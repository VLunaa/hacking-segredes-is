# Level 9

## Objetivo
- Find the password, which is in home directory in the file data.txt. The password its in a human-readable string, after severall "=".

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit9
- Password: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

## Solución
- Combine different commands, using " | " so that a "filter" can be made: "cat data.txt | strings | grep == "

## Notas adicionales
- Use pipes to chain the execution of programs " | ".