## Descripción
Can you find the flag? [shark1.pcapng](https://mercury.picoctf.net/static/b44842413a0834f4a3619e5f5e629d05/shark1.pcapng).

## Solución
- Abrí shark1.pcapng con Wireshark. después seguí los paquetes por TCP Stream.
- Stream 5 (tcp.stream eq 5) contenía algo que parecía prometedor:

     Gur synt vf cvpbPGS{c33xno00_1_f33_h_qrnqorrs}

Después de decodificar eso con ROT13, se reveló la bandera.

picoCTF{p33kab00_1_s33_u_deadbeef}