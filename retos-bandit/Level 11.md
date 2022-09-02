# Level 11

## Objetivo
- Find the password in the data.txt file, which has an encryption where the letters are shifted 13 positions, using lowercase and uppercase.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit11
- Password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solución
- Use cat to read and tr to unencrypt. cat data.txt | tr 'n-za-mN-ZA-M' 'a-zA-Z'

## Notas adicionales
- The tr command is a Linux command-line utility that translates or deletes characters from standard input ( stdin ) and writes the result to standard output ( stdout ).