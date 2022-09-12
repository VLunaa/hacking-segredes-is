# Level 27

## Objetivo
- There is a git repository at ssh://bandit27-git@localhost/home/bandit27-git/repo. The password for the user bandit27-git is the same as for the user bandit27.
 - Clone the repository and find the password for the next level.
## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit27
- Password: YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS

## Solución
- Clone the given repository, you need to use port 2220, otherwise you won't get it. Enter the password (It is the same as the current level).
```
bandit27@bandit:/tmp/reptmp$ git clone "ssh://bandit27-git@localhost:2220/home/bandit27-git/repo"
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

!!! You are trying to log into this SSH server on port 2220 on localhost.
!!! Please log out and log in again instead.

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/reptmp$ ls
repo
bandit27@bandit:/tmp/reptmp$ cd repo
bandit27@bandit:/tmp/reptmp/repo$ ls
README
bandit27@bandit:/tmp/reptmp/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
bandit27@bandit:/tmp/reptmp/repo$
```
## Notas adicionales
- 