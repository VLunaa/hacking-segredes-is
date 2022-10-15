## Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Solución
- La bandera se encuentra oculta entre varios paquetes, más especificamente, se encuentra escondida en el puerto origen, hay que hacer un script de python para iterar entre estos puertos y hacer la respectiva conversión a ascii.

Script:
```
from scapy.all import *
packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
	if UDP in p and p[UDP].dport == 22:
		if p[UDP].sport > 5000:
			flag+= chr(p[UDP].sport - 5000)

print(flag)

```

picoCTF{p1LLf3r3d_data_v1a_st3g0}