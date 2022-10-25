## Descripción
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag. Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

-   [Download disk image](https://artifacts.picoctf.net/c/114/disk.img.gz)
-   Access checker program: `nc saturn.picoctf.net 52279`

## Solución

Simplemente hay que descargar el archivo y descomprimirlo con gzip -d disk.img.gz

Luego, hay que encontrar el tamaño del disco con mmls.

mmls disk.img
Encontramos que el tamaño/longitud está en: 202752

Por úlitimo hay que conectarse al servidor usando netcat, se pone el tamaño y se obtiene la bandera: picoCTF{mm15_f7w!}