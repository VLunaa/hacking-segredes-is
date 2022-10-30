## Descripción
- Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 9422`.

## Solución
- Parece que el método de encriptación es código morse, alguna vez lo vi en películas. Es de los más conocidos, por lo que fue fácil encontrar una herramienta online para desencriptarlo, de igual forma que los demás, este también se puede desencriptar de forma manual, siguiendo algunos pasos (un algoritmo).

```
┌──(kali㉿kali)-[~/Downloads]

└─$ nc jupiter.challenges.picoctf.org 9422

.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..--- ....- -.... .---- ----- }
```

Usé esta herramienta para desencriptar ambas partes de la bandera: http://www.unit-conversion.info/texttools/morse-code/

picoctf{m0rs3c0d31sfun2683824610}