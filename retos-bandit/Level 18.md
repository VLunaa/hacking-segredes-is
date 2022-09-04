# Level 18

## Objetivo
- You have to get the password stored in the home directory, but someone has modified .bashrc, so that when you log in the session is closed. Find a way to prevent this from happening and get the password.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit18
- Password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

## Solución
- If you combine the cat command, you can get the password before you disconnect. This looks like a little trick
```
C:\Users\darkv\OneDrive\Escritorio\IS -7\Seg Redes\notas-hacking-is\retos-bandit>ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password:
awhqfNnAbc1naukrpqDYcF95h7HoMTrC

C:\Users\darkv\OneDrive\Escritorio\IS -7\Seg Redes\notas-hacking-is\retos-bandit>
```

## Notas adicionales
- 