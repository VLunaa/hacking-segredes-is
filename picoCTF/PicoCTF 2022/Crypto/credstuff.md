## Descripción

We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it? Download the leak [here](https://artifacts.picoctf.net/c/534/leak.tar). The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.

## Solución
- El usuario "cultiris" se encuentra en la línea 378, por lo que su password también debería estar en la 378 "cvpbPGS{P7e1S_54I35_71Z3}", lo confirmamos ya que tiene un formado de bandera picoCTF, parece ser un cifrado caesar, sólo hay que desencriptarlo, en mi caso utilicé un decodificador online: https://www.dcode.fr/caesar-cipher


picoCTF{C7r1F_54V35_71M3}