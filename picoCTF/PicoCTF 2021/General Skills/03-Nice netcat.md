# Nice netcat

## Descripción
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 35652`, but it doesn't speak English...

## Solución
- Al ejectuar el comando, sale una serie de números, en la pista dice de practicar con ASCII, por lo que se intuye que es código ASCII. SImplemente hay que convertirlo a caracteres de texto.
```
┌──(kali㉿kali)-[~]
└─$ nc mercury.picoctf.net 35652
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
57 
98 
51 
98 
55 
51 
57 
50 
125 
10 
```

picoCTF{g00d_k1tty!_n1c3_k1tty!_9b3b7392}