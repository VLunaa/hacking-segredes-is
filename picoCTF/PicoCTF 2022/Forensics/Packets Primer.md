## Descripción

- Download the packet capture file and use packet analysis software to find the flag.

-   [Download packet capture](https://artifacts.picoctf.net/c/201/network-dump.flag.pcap)

## Solución

- Abrí el paquete con whireshark y me dirijí a TCP Stream en el stream 0, ahí es donde se enuentra la bandera, viene con espacios, yo los removí manualmente, pero se pueden remover usando python también.

picoCTF{p4ck37_5h4rk_01b0a0d6}
