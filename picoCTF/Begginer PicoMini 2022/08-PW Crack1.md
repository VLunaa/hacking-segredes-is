# PW Crack1

## Description
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/52/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/52/level1.flag.txt.enc) in the same directory too.

## Solución
- Se ejecuta el archivo level1.py, pero pide una contraseña, simplemente hay que inspeccionar este archivo y detectarla.

```
┌──(kali㉿kali)-[~/Downloads]
└─$ nano level1.py              
                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 level1.py
Please enter correct password for flag: 1e1e
That password is incorrect
                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 level1.py
Please enter correct password for flag: 1e1a
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_fa343060}
                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ 

```

picoCTF{545h_r1ng1ng_fa343060}