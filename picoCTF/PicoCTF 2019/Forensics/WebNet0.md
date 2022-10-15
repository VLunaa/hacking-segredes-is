## Descripción


We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.

## Solución
- Se tienen lo paquetes TLS encripados, hay que abrir wireshark, ir a preferencias y agregar la llave que el reto nos proporciona, una vez agregada, los paquetes serán desencriptados y podremos seguir alguno para obtener la llave.

picoCTF{nongshim.shrimp.crackers}