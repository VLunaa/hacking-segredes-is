# WhitePages

## Descripción
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt) is all blank!

## Solución
- Hay que crear un script de python para reemplazar los carácteres en blanco por código binario, posteriormente traducir este código a ascii y obtener la bandera.

Script de python:
```
from pwn import *
file = open('whitepages.txt', 'rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')
data = data.decode('ascii')
data = unbits(data)
print(data)
```

```
┌──(kali㉿kali)-[~/Downloads]
└─$ python3 exp.py
b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}\n\t\t'

```


picoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}