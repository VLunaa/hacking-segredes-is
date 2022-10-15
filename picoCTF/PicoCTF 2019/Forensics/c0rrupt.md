## Descripción
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

## Solución
- La imagen está corrupta, algunos chunks están mal. Los bytes deben coincidir con el tamaño y tipo del chun. En la cabecera están mal y en algunas otras partes también, hay que utilizar un editor hexadecimal para abrir la imagen y cambiar estos valores, una vez cambiados, la imagen ya se podrá abrir y encontrará la bandera.

picoCTF{c0rrupt10n_1847995}