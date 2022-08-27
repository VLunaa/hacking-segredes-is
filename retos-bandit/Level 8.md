# Level 8

## Objetivo
- Find the password, which is in home directory in the file data.txt. The password is the only line of text that occurs only once.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit8
- Password: cvX2JJa4CFALtqS87jk27qwqGhBM9plV

## Solución
- Combine different commands, using " | " so that a "filter" can be made: "cat data.txt | sort | uniq -u"

## Notas adicionales
- Use pipes to chain the execution of programs " | ".