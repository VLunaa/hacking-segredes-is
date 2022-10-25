# 

## Descripción

I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/52da699e0f203321c7c90ab56ea912d8/Forensics is fun.pptm)

## Solución
- De nuevo se utilizó binwalk para los archivos ocultos.

Si ejecutamos binwalk "Forensics is fun.pptm", veremos que hay un montón de archivos .zip. Podemos extraerlo usando binwalk -e "Forensics is fun.pptm" (-e o --extract para extraer)

Enontraremos una carpeta que se puede explorar con 7zip y podemos manejar por ella en la terminal.

Se extrajo "0.zip" y se navegó en la terminal.

Al llegar a la raíz, se usó el comando -D tree|grep hiddenm, que devolvió:

./ppt/slideMasters/hidden

Nos dirijimos a  cat ./ppt/slideMasters/hidden


```
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q
```

Se podrían eliminar los espacios con un script, en mi caso lo hice manualmente.

"ZmxhZzogcGljb0NURntEMWRfdV9rbjB3X3BwdHNfcl96MXA1fQ" Está en base 64, sólo hay que utilizar un decodificador para obtener la bandera.

picoCTF{D1d_u_kn0w_ppts_r_z1p5}