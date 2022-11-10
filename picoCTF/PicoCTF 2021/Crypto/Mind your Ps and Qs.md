## Descripción
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/3cfeb09681369c26e3f19d886bc1e5d9/values)

## Solución
- Es parecido a los retos anteriores de RSA, en este caso, utilicé una herramienta llamada RsaCtfTool.

```
┌──(kali㉿kali)-[~/Desktop/RsaCtfTool]

└─$ python3 RsaCtfTool.py -n 769457290801263793712740792519696786147248001937382943813345728685422050738403253 -e 65537 --uncipher 8533139361076999596208540806559574687666062896040360148742851107661304651861689

private argument is not set, the private key will not be displayed, even if recovered.

  

[*] Testing key /tmp/tmpfxdiazny.

attack initialized...

[*] Performing smallq attack on /tmp/tmpfxdiazny.

[*] Performing factordb attack on /tmp/tmpfxdiazny.

[*] Attack success with factordb method !

  

Results for /tmp/tmpfxdiazny:

  

Unciphered data :

HEX : 0x7069636f4354467b736d6131315f4e5f6e305f67306f645f34353336393338377d

INT (big endian) : 13016382529449106065927291425342535437996222135352905256639629442503647501498237

INT (little endian) : 14498987658303720244605374829370395583378376448083098194788817536789828969130352

utf-8 : picoCTF{sma11_N_n0_g0od_45369387}

STR : b'picoCTF{sma11_N_n0_g0od_45369387}'

HEX : 0x007069636f4354467b736d6131315f4e5f6e305f67306f645f34353336393338377d

INT (big endian) : 13016382529449106065927291425342535437996222135352905256639629442503647501498237

INT (little endian) : 3711740840525752382618975956318821269344864370709273137865937289418196216097370112

utf-8 : picoCTF{sma11_N_n0_g0od_45369387}

utf-16 : 瀀捩䍯䙔獻慭ㄱ也湟弰で摯㑟㌵㤶㠳紷

STR : b'\x00picoCTF{sma11_N_n0_g0od_45369387}'

┌──(kali㉿kali)-[~/Desktop/RsaCtfTool]

└─$
```

picoCTF{sma11_N_n0_g0od_45369387}