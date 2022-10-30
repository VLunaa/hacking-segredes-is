
## Descripción

Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/a614a27d4cb251d04c7d2f3f3f76a965/cat.jpg)

## Solución
- Cada vez que se obtiene un archivo de imagen, hay que verficar que tipo de archivo es, se ejecuta el archivo (para asegurarme de que es una imagen), binwalk (para ver si hay archivos ocultos), también hay que utilizar strings con grep, si no se ha encontrado nada, se puede abrir la imagen con un editor hexadecimal.

```
┌──(kali㉿kali)-[~/Downloads]
└─$ file cat.jpg 
cat.jpg: JPEG image data, JFIF standard 1.02, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 2560x1598, components 3
┌──(kali㉿kali)-[~/Downloads]
└─$ binwalk cat.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             JPEG image data, JFIF standard 1.02

┌──(kali㉿kali)-[~/Downloads]
└─$ strings cat.jpg | grep picoCTF{*
┌──(kali㉿kali)-[~/Downloads]
└─$ 
```

- Si la abrimos con un editor hexadecimal, se puede ver lo siguiente.

```
......JFIF......
.......0Photosho
p 3.0.8BIM......
....t..PicoCTF..
..........http:/
/ns.adobe.com/xa
p/1.0/.<?xpacket
begin='...' id=
'W5M0MpCehiHzreS
zNTczkc9d'?>.<x:
xmpmeta xmlns:x=
'adobe:ns:meta/'
x:xmptk='Image:
:ExifTool 10.80'
>.<rdf:RDF xmlns
:rdf='http://www
.w3.org/1999/02/
22-rdf-syntax-ns
#'>.. <rdf:Descr
iption rdf:about
=''.  xmlns:cc='
http://creativec
ommons.org/ns#'>
.  <cc:license r
df:resource='cGl
jb0NURnt0aGVfbTN
0YWRhdGFfMXNfbW9
kaWZpZWR9'/>. </
rdf:Description>
.. <rdf:Descript
ion rdf:about=''
.  xmlns:dc='htt
p://purl.org/dc/
elements/1.1/'>.
 <dc:rights>.
<rdf:Alt>.    <
rdf:li xml:lang=
'x-default'>Pico
CTF</rdf:li>.
</rdf:Alt>.  </d
c:rights>. </rdf
:Description>.</
rdf:RDF>.</x:xmp
meta>.
```
 Sólo hay que decodificar con `echo W5M0MpCehiHzreSzNTczkc9d | base64 -d` y obtendremos la bandera.

picoCTF{the_m3tadata_1s_modified}