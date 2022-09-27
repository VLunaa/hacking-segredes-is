# first grep

## Description
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/315d3325dc668ab7f1af9194f2de7e7a/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Solución
- Se lee la fila y se usa un grep para buscar picoCTF.

```
┌──(kali㉿kali)-[~/Downloads]
└─$ cat file | grep picoCTF
picoCTF{grep_is_good_to_find_things_f77e0797}
```

