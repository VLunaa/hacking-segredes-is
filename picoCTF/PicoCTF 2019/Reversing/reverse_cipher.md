## Descripción
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/7aa5f383ec616fe9d72c2ffe1fabd0d9/rev_this). Can you reverse the flag.

## Solución
- Hay que abrir el binario con Ghidra, para poder analizar el archivo binario. Una vez analizado, hay que aplicar ingeniería inversa. Se creo el script para utilizar reversing en un compilador de python online.

```
cifrado = 'picoCTF{w1{1wq84fb<1>49}'
flag = ''
for i in range(8, len(cifrado)-1):
    if i & 1 == 0:
        flag += chr( ord(cifrado[i]) -5)
    else:
        flag += chr( ord(cifrado[i]) +2)
    
print(flag)
```

```
r3v3rs36ad73964
> 
```