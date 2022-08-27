# Level 6

## Objetivo
- Read the file, which is somewhere in the server with the following properties: 
	-   owned by user bandit7
	-   owned by group bandit6
	-   33 bytes in size

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit6
- Password: DXjZPULLxYr17uwoI01bNLQbtFemEgo7

## Solución
- Use the command find properties to find the file with the password: find / -readable -user bandit7 -group bandit6 -size 33c, then locate the file with the password and read it.


## Notas adicionales
- f is for regular files and that c after the size refers to the bytes.