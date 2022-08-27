# Level 1

## Objetivo
- Read the "-" file, which is in the current directory (home) to get the next level password.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit1
- Password: boJ9jbbUNNfktd78OOpsqOltutMc3MY1

## Solución
- Read the file using cat ./"filename".


## Notas adicionales
This type of approach has a lot of misunderstanding because using **-** as an argument refers to STDIN/STDOUT i.e dev/stdin or dev/stdout. So if you want to open this type of file you have to specify the full location of the file such as ./- 

