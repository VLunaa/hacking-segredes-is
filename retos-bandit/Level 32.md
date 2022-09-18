# Level 32

## Objetivo
- When connecting to the server, you will enter the "UPPERCASE SHELL", find a way to get the password for bandit33.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit32
- Password: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y

## Solución
```
WELCOME TO THE UPPERCASE SHELL
>> ls
sh: 1: LS: not found
>> whoami
sh: 1: WHOAMI: not found
>> $0
$ whoami
bandit33
$ cat /etc/bandit_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
$
```
## Notas adicionales
- 