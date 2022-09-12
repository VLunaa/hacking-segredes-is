# Level 25

## Objetivo
- Logging in to bandit26 from bandit25 should be fairly easy The shell for user ban-  
dit26 is not /bin/bash, but something else. Find out what it is, how it works and  
how to break out of it.
## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit25
- Password: p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

## Solución
- Log in to level 26 using the ssh key, then minimize the command window to a small size, this will stop the login process from loading, so you won't be kicked out of the level. Once on that screen, read the level 26 password.

```
bandit25@bandit:~$ ssh bandit26@localhost -p 2220 -i bandit26.sshkey
...
...
...

c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
~                                                                                                                      "/etc/bandit_pass/bandit26" [readonly] 1L, 33B                                                        1,1           All
```
## Notas adicionales
- 