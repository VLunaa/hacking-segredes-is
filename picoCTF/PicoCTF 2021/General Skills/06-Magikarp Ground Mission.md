# Magikarp Ground Mission

## Description
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `b60940ca`
## Solución
- Entre al servidor usando ssh, posteriormente navegue con el comando "cd", lea los archivos y siga las instrucciones para encontrar la bandera.
```
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ cat 1of3.flag.txt
picoCTF{xxsh_
ctf-player@pico-chall$ cat instructions-to-2of3.txt
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cd..
-bash: cd..: command not found
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt
c1754242}
ctf-player@pico-chall$ ls -a
.  ..  .cache  .profile  .ssh  3of3.flag.txt  drop-in
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls -a
.  ..  ctf-player
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls -a
.           2of3.flag.txt  dev   instructions-to-3of3.txt  media  proc  sbin  tmp
..          bin            etc   lib                       mnt    root  srv   usr
.dockerenv  boot           home  lib64                     opt    run   sys   var
ctf-player@pico-chall$ cat 2of3.flag.txt
0ut_0f_\/\/4t3r_

```

picoCTF{xxsh_0ut_0f_\/\/4t3r_c1754242}