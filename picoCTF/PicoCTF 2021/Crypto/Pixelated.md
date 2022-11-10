## Descripción
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/c9593d1d2ac9d850da95bffe0ac3b6c6/scrambled2.png)

## Solución
-  Utilicé una librería de Pillow llamada Image, para "fusionar" las dos imágenes dadas y obtener la imagen con la banderea.

```
┌──(kali㉿kali)-[~/Downloads]

└─$ python3

Python 3.10.7 (main, Sep  8 2022, 14:34:29) [GCC 12.2.0] on linux

Type "help", "copyright", "credits" or "license" for more information.

>>> from PIL import Image

>>> img1 = Image.open("scrambled1.png")

>>> img2 = Image.open("scrambled2.png")

>>> pixels1 = img1.load()

>>> pixels2 = img2.load()

>>> flag = Image.new("RGB",img1.size)

>>> flagpix = flag.load()

>>> for row in range(img1.size[1]):

...      for col in range(img1.size[1]):

...              flagpix[col,row]=(

...                      (pixels1[col,row][0]+pixels2[col,row][0])&256,

...                      (pixels1[col,row][1]+pixels2[col,row][1])&256,

...                      (pixels1[col,row][2]+pixels2[col,row][2])&256)

...

>>> flag.save("flag.png")
```

![[Pasted image 20221109182746.png]]