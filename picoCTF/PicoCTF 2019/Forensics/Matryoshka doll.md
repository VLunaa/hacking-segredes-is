## Descripción
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/f6cc2560a70b1ea811c151accba5390f/dolls.jpg)

## Solución
- El reto nos da un enlace para descargar una imagen llamada dolls.jpg. Tomando una pista del nombre del desafío "Matryoshka Doll", podemos suponer que hay archivos ocultos dentro de este archivo. Para extraerlos usamos binwalk.
```  
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 exp.py binwalk -e dolls.jpg

DECIMAL HEXADECIMAL DESCRIPTION  
--------------------------------------------------------------------------------  
0 0x0 PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced  
3226 0xC9A TIFF image data, big-endian, offset of first image directory: 8  
272492 0x4286C Zip archive data, at least v2.0 to extract, compressed size: 378955, uncompressed size: 383936, name: base_images/2_c.jpg  
651613 0x9F15D End of Zip archive, footer length: 22  
```

Después de seguir usando binwalk para extraer los archivos ocultos, obtendremos la bandera.

picoCTF{ac0072c423ee13bfc0b166af72e25b61}