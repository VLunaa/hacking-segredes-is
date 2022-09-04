# Level 19

## Objetivo
- To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit19
- Password: awhqfNnAbc1naukrpqDYcF95h7HoMTrC

## Solución
- The file bandit20_do has the permissions that allow the user bandit19 to execute commands on behalf of bandit20, so use that file and get the password.
```
bandit19@bandit:~$ ls
bandit20-do
bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Sep  1 06:30 .
drwxr-xr-x 49 root     root      4096 Sep  1 06:30 ..
-rwsr-x---  1 bandit20 bandit19 14872 Sep  1 06:30 bandit20-do
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
bandit19@bandit:~$ ./bandit20-do id
uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```
## Notas adicionales
- Setuid or Set User ID is a type of file permission setting in Linux operating system that allows a user to execute a file or program using root privileges. This tool is used to elevate a user's privileges, that is, it allows the person running a setuid program to do so as if they were the user who owns the file.