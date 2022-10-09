# m00nwalk

## Descripción
Decode this [message](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) from the moon.

## Solución
- El archvo de audio SSTV, se puede convertir en una imagen, puede utilizar diversas estas herramientas para decodificar "message.wav" en una imagen, en este caso se utilizó una herramienta llamada "QSSTV".

```
┌──(kali㉿kali)-[~/Downloads]
└─$ paplay -d virtual-cable message.wav 
```

La herramienta comenzará a decodificar y se obtendrá la imagen con la bandera.

picoCTF{beep_boop_im_in_space}