# strings it

## Description
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?

## Solución
- Se utiliza el comando strings y un grep para buscar picoCTF.

```
┌──(kali㉿kali)-[~]
└─$ cd Downloads 
                                                                                    
┌──(kali㉿kali)-[~/Downloads]
└─$ strings strings | grep picoCTF
picoCTF{5tRIng5_1T_d66c7bb7}

```

