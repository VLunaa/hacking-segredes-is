# PW Crack3

## Description
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/23/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/23/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/23/level3.hash.bin) in the same directory too. There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Solución
- Se probaron los diferentes passwords dentro del archivo lvl3.py hasta encontrar el correcto.

```
└─$ python3 level3.py
Please enter correct password for flag: 4e66
That password is incorrect
                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 level3.py
Please enter correct password for flag: f0ac
That password is incorrect
                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 level3.py
Please enter correct password for flag: ec27
That password is incorrect
                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 level3.py
Please enter correct password for flag: 4b17    
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}
                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ 
                            
```

picoCTF{m45h_fl1ng1ng_2b072a90}