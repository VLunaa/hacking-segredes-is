# Based

## Description
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 14291`.

## Solución
- Se vuelve a usar un grep para filtrar por palabra picoCTF

```
┌──(kali㉿kali)-[~/Downloads]
└─$ nc jupiter.challenges.picoctf.org 14291| grep picoCTF
picoCTF{digital_plumb3r_ea8bfec7}

```

