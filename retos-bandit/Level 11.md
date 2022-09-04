# Level 11

## Objetivo
- Find the password in the data.txt file, which has an encryption where the letters are shifted 13 positions, using lowercase and uppercase.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit11
- Password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

## Solución
- If we try to read the password, we will see that is encrypted, you have to reverse the rotation.. Use cat to read and tr to unencrypt. cat data.txt | tr 'n-za-mN-ZA-M' 'a-zA-Z'.

```
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr 'n-za-mN-ZA-M' 'a-zA-Z'
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$
```


## Notas adicionales
- The tr command is a Linux command-line utility that translates or deletes characters from standard input ( stdin ) and writes the result to standard output ( stdout ).