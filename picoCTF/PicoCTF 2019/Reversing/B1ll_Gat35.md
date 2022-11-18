## Descripción
Can you reverse this [Windows Binary](https://jupiter.challenges.picoctf.org/static/0ef5d0d6d552cd5e0bd60c2adbddaa94/win-exec-1.exe)?

## Solución
- Para este reto usé un debugger de windows, llamado WinDbg.

```
D:\Users\DarkV\Descargas>win-exec-1.exe
Input a number between 1 and 5 digits: 1
Initializing...
Enter the correct key to get the access codes: The key is: 4253360
Correct input. Printing flag: PICOCTF{These are the access codes to the vault: 1063340}
D:\Users\DarkV\Descargas>
```

Debugger:
```
eax=00f87228 ebx=00d90000 ecx=00effa84 edx=00000063 esi=0072cf8c edi=00f86408
eip=006b7f85 esp=00effa5c ebp=00effa6c iopl=0         nv up ei pl zr na pe nc
cs=0023  ss=002b  ds=002b  es=002b  fs=0053  gs=002b             efl=00000246
win_exec_1+0x7f85:
006b7f85 e89896ffff      call    win_exec_1+0x1622 (006b1622)
0:000> da eax
00f87228  "The key is: 4253360"
```

![[Pasted image 20221118143741.png]]

PICOCTF{These are the access codes to the vault: 1063340}