# Glitch Cat

## Description
Our flag printing service has started glitching! `$ nc saturn.picoctf.net 51109`

## Solución

```
┌──(kali㉿kali)-[~/Downloads]
└─$ nc saturn.picoctf.net 51109
'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ python3                    
Python 3.10.7 (main, Sep  8 2022, 14:34:29) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print('picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
... )
picoCTF{gl17ch_m3_n07_bda68f75}
>>> 

```

picoCTF{gl17ch_m3_n07_bda68f75}