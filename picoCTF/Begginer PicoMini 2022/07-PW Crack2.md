# PW Crack2

## Description
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/18/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level2.flag.txt.enc) in the same directory too.

## Solución
- Se ejecuta el archivo level2.py, pero pide una contraseña, simplemente hay que inspeccionar este archivo y detectarla, se tiene que traducir.

```
                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ nano level2.py
                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ python3          
Python 3.10.7 (main, Sep  8 2022, 14:34:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65))
39ce
>>> 
zsh: suspended  python3
                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 level2.py
Please enter correct password for flag: 39ce
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_502ec42e}
                                 
```

picoCTF{tr45h_51ng1ng_502ec42e}