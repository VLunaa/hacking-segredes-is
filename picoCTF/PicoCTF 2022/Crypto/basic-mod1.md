## Descripción
We found this weird message being passed around on the servers, we think we have a working decryption scheme. Download the message [here](https://artifacts.picoctf.net/c/394/message.txt). Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Solución
-  Simplemente hay que crear un script en python para encontrar la bandera, se debe leer bien la descripción del reto.

```
import string
alfabeto = string.ascii_lowercase
alfabeto += "0123456789_"

flag_enc = [202,137,390,235,114,369,198,110,350,396,390,383,225,258,38,291,75,324,401,142,288,397]
flag = ""
for c in flag_enc:
    pos = c % 37
    flag += alfabeto[pos]

print(flag)
```

picoCTF{r0und_n_r0und_b6b25531}