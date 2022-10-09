# So Meta

## Descripción
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/89b371a46702a31aa9931a2a2b12f8bf/pico_img.png).

## Solución
- Hay que observar los metadatos de la imagen, si la abrimos con un nano los podemos ver, pero son demasiados, así que.

picoCTF{s0_m3ta_eb36bf44}

```
┌──(kali㉿kali)-[~/Downloads]
└─$ strings pico_img.png | grep "pico"       
picoCTF{s0_m3ta_eb36bf44}
                                                                                                  
┌──(kali㉿kali)-[~/Downloads]
└─$ 
```
