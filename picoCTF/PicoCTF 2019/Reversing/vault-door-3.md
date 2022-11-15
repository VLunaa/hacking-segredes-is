## Descripción
This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/943ea40e3f54fca6d2145fa7aadc5e09/VaultDoor3.java)

## Solución
- Hay que analizar la lógica y hacer reverse, en mi caso utilicé un script de javascript en un editor online para obtener la bandera.

```
password = "jU5t_a_sna_3lpm18g947_u_4_m9r54f"

var i;

var buffer = Array(32);

for (i=0; i<8; i++) {

     buffer[i] = password.charAt(i);
}

for (; i<16; i++) {
    buffer[i] = password.charAt(23-i);
}
'n'

for (; i<32; i+=2) {
    buffer[i] = password.charAt(46-i);
}

'd'

for (i=31; i>=17; i-=2) {

    buffer[i] = password.charAt(i);
}

'g'

console.log("picoCTF{" + buffer.join("") + "}");
```

picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_79958f}