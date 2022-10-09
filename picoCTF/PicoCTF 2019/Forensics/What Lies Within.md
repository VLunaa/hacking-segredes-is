# What Lies Within

## Descripción
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

## Solución
- La esteganografía es la práctica de ocultar un mensaje secreto dentro (o incluso encima) de algo que no es secreto, por ejemplo de una imagen, como es el caso. Utilizando la herramienta "zsteg", podemos encontrar este mensaje secreto.

```
┌──(kali㉿kali)-[~/Downloads]
└─$ zsteg -a buildings.png
b1,r,lsb,xy         .. text: "^5>R5YZrG"
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
b1,abgr,msb,xy      .. file: PGP Secret Sub-key -
b2,b,lsb,xy         .. text: "XuH}p#8Iy="

```

picoCTF{h1d1ng_1n_th3_b1t5}