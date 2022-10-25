## Descripción
Figure out how they moved the [flag](https://mercury.picoctf.net/static/b686a99ec088f10b324cfe963bd32dab/tftp.pcapng).

## Solución
Mirando el nombre del desafío, probablemente esté enviando datos usando TFTP. Importamos el .pcap a wireshark y vemos que, de hecho, hay tráfico TFTP en curso.
Método

Podemos extraer objetos usando wireshark y si seleccionamos TFTP, vemos que wireshark detectó un par de archivos. instrucciones, plano, programa y 3 fotos. 

Ejecutar archivo en el archivo de programa nos muestra que es un archivo .deb y está instalando steghide. Esto significa que la bandera está oculta en las imágenes usando steghide.

El plan y las instrucciones no se parecían en nada, pero después de un tiempo me di cuenta de que es solo un código. Pasarlo a través de un cracker en línea o, en mi caso, el comando caesar desde la línea de comandos hizo el trabajo.
Recuperamos la frase de contraseña para el steghide, todo lo que tenemos que hacer es extraer los datos.

picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}