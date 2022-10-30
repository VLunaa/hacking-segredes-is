
## Descripción

Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it. Download the data [here](https://artifacts.picoctf.net/c/296/anthem.flag.txt).

## Solución
- Simplemente usé un grep para encontrar la bandera.

```
┌──(kali㉿kali)-[~/Downloads]
└─$ grep -i "pico" anthem.flag.txt 
      we think that the men of picoCTF{gr3p_15_@w3s0m3_2116b979}
```

picoCTF{gr3p_15_@w3s0m3_2116b979}