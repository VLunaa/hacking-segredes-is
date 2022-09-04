# Level 16

## Objetivo
- The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit16
- Password: JQttfApK4SeyHwDlI9SXGR50qclOAil1

## Solución
- Find the open ports among the range.. "nmap localhost -p 31000-32000"
```
bandit16@bandit:~$ nmap localhost -p 31000-32000
Starting Nmap 7.80 ( https://nmap.org ) at 2022-09-04 14:59 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00022s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.07 seconds
bandit16@bandit:~$
```
- As we can see, there are 3 open ports. 31046, 31518, 31691, 31790, 31960, try ssl to connect to these untill you find the right one. Put the actual password.
```
bandit16@bandit:~$ openssl s_client -connect localhost:31790 -ign_eof
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  3 23:40:42 2022 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  3 23:40:42 2022 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  3 23:39:42 2022 GMT; NotAfter: Sep  3 23:40:42 2022 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEPBAeDzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjIwOTAzMjMzOTQyWhcNMjIwOTAzMjM0MDQyWjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDJ
oaGloiCj5rvCVLShjf7nTU9pTzioKE5KGG7ac3eq6yO+3wHqMTwCFvqrNB4ZjcLD
Kbttx2enLnHU3ncVxb42sf+vez3L6nfnXYcEyRRB2Cmq5ndVxhDCfMXd0jQVkzF+
388rJNbfEr5xSR7YznfHllQLGLV08G92mmjsPv7+adPyEZ5M6/2gC8OdOmr3J1lE
CD9M7DcYz9zeAZ5ri0l7IF/hghbiuRNVywVFe9jRLCoaGs1a4eWvUe4qwAvuZ9Dt
38Fix1XaaHZK6BOUkelh7lP/ZDQdEck2W7/8V+hHR0cd7ZJb7Emn8WdaXf04786b
n721Grcm2HXIbpZaAHrNAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQCK
REInXE2/tbk1lkCo8B/79Ckpq3sX/gHB+Q8aXuQNqlTTTUMwiHRdnnuC2imoqoq9
dHYOuhWpAoqKhAyezQkj7WtTjTXfT8ViNWzxPQcPUki1ERlQIRgZc/IGgW6jbzzg
PEfJiuIKr56lC/zFQkL7L9iusSopSGQGvz8rJz9YsOIHDycWhFQaJFFnpySQJOp1
RjSfZvKWuWloSCxyLrp0RdAWHpfshUh3UZQxqP5NzbNR6hCXh5o/1WqCS9RHkviS
LY3tn2wUJPX2DexmpAh+NzfimKN4UMKijnvmIRNF1Kd6TEidT8cZRvXnUnNkm/qg
LzdmlimtXnifHPGCsmXp
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 8C12E9556014E4F9DD00833A5C2B6A2FC2DE93B2C9B7E95F0AF6718477D3FEF0
    Session-ID-ctx:
    Resumption PSK: 45056F8A4580DD01CA1082F3C05CAF5AE374F8DE301EDC0496947B8E695CE87961B459CA036BA53A2D12867E9F597F62
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - fb 34 dc b1 cc 2b c6 d3-52 56 11 ae 76 76 80 c3   .4...+..RV..vv..
    0010 - 6f 27 98 7f 02 15 99 50-b3 d8 ed 91 a7 d3 d7 60   o'.....P.......`
    0020 - 67 44 90 b5 ca 84 07 7d-15 07 54 9a a3 18 76 9a   gD.....}..T...v.
    0030 - 69 d1 17 32 25 39 23 d6-68 8e e6 df b1 91 28 1b   i..2%9#.h.....(.
    0040 - 52 41 77 b6 7b 65 c6 6b-53 af cc e6 ec 0d 63 34   RAw.{e.kS.....c4
    0050 - e9 70 5a 3a 4c 2d 29 67-6c e5 80 e2 a7 a2 e2 ce   .pZ:L-)gl.......
    0060 - 81 f0 3a 56 67 8d 35 b2-9f 57 b0 af e9 41 99 77   ..:Vg.5..W...A.w
    0070 - 2f 33 3c c7 69 4b 2d a4-f8 da 9b 25 f3 31 5e c5   /3<.iK-....%.1^.
    0080 - d4 7b f1 18 d2 1e dd 3e-cc 9c 63 3b de 9a 75 a2   .{.....>..c;..u.
    0090 - c9 b9 c4 47 60 e0 e2 ec-31 b9 89 1b 97 9f 1c 1a   ...G`...1.......
    00a0 - 8e a7 7d a1 c1 72 7c e5-6e 08 7b 5a e6 a2 da 36   ..}..r|.n.{Z...6
    00b0 - 20 38 83 7b 5b 10 13 10-49 09 48 6b 51 28 1f 37    8.{[...I.HkQ(.7
    00c0 - 46 da 98 bb f6 12 4c 85-aa 78 fb 2c ad 1f 30 85   F.....L..x.,..0.

    Start Time: 1662304035
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 1977648DCD3C718BA1C972486823B62129FE5F6271A037F9A43BE7A7676ECA17
    Session-ID-ctx:
    Resumption PSK: 9AD9C3BDF0707E53156EDBF4897878198515188890CB9256765AFAF7F2F28165D002F0D1C75849EFC01E2A753010F993
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - fb 34 dc b1 cc 2b c6 d3-52 56 11 ae 76 76 80 c3   .4...+..RV..vv..
    0010 - d1 7d a8 15 35 c7 20 3d-e6 9b 3a 32 60 81 7a a4   .}..5. =..:2`.z.
    0020 - d0 83 8b 30 e9 2a 22 04-f8 9f c0 8e c5 11 41 92   ...0.*".......A.
    0030 - 52 5e 67 a3 66 eb ec e0-c6 c5 d4 2d c2 4d b2 34   R^g.f......-.M.4
    0040 - e9 54 a4 64 44 0a e2 95-d7 65 72 53 e4 13 4f c8   .T.dD....erS..O.
    0050 - a8 e7 23 f5 e3 e8 43 5d-df 3e 65 80 b6 3b 1b b3   ..#...C].>e..;..
    0060 - 8d 58 6a aa 11 63 b3 12-7c 6a 13 e6 ae 1a c4 35   .Xj..c..|j.....5
    0070 - 0f 52 23 f0 a3 33 31 bd-e4 0e 7a 41 cc ae be 88   .R#..31...zA....
    0080 - fb 18 7d 13 6b 40 5c a9-9e 01 a2 7f dc 75 02 21   ..}.k@\......u.!
    0090 - 88 c9 f5 e9 6c b8 35 32-39 c3 3a d6 1d 96 f8 a8   ....l.529.:.....
    00a0 - ff f5 e4 a0 21 f7 83 71-f0 5d c5 42 ea d9 da 8c   ....!..q.].B....
    00b0 - f7 13 75 96 84 3c 94 7b-c9 89 64 be 7d f5 ce e8   ..u..<.{..d.}...
    00c0 - b8 44 fa a4 a2 53 b1 24-d2 aa 8d cf 97 20 56 82   .D...S.$..... V.

    Start Time: 1662304035
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
bandit16@bandit:~$
```

## Notas adicionales
- You can use the nmap command to scan ports.
