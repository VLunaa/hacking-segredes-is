# Level 12

## Objetivo
- Find the password in the data.txt file, which is a hexdump of a file that has been repeatedly compressed.

## Datos de acceso
- Host: bandit.labs.overthewire.org
- Port: 2220
- User: bandit12
- Password: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv 

## Solución
- Use different methods to decompress to a readable ascii file.
- We can see that de file is compressed, so we have to decompress it, it is a bzip2 file, so you have to use bzip2.

```
bandit12@bandit:/$ cd /tmp/hellog0d
bandit12@bandit:/tmp/hellog0d$ xxd -r ~/data.txt data.txt
bandit12@bandit:/tmp/hellog0d$ zcat data.txt > data2.bin
bandit12@bandit:/tmp/hellog0d$ file data2.bin
data2.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/hellog0d$ ls
data2.bin  data2.bin.out  data4.bin  data5.bin  data6.bin.out  data8.bin  data9.bin  data.txt
bandit12@bandit:/tmp/hellog0d$ bzip2 -d data2.bin
bzip2: Can't guess original name for data2.bin -- using data2.bin.out
bzip2: Output file data2.bin.out already exists.
bandit12@bandit:/tmp/hellog0d$ file data2.bin.out
data2.bin.out: gzip compressed data, was "data4.bin", last modified: Thu Sep  1 06:30:09 2022, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/hellog0d$ zcat data2.bin.out > data4.bin
bandit12@bandit:/tmp/hellog0d$
```
- Then you have a tar file, decompress it.

```
bandit12@bandit:/tmp/hellog0d$ file data4.bin
data4.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/hellog0d$ tar -xvf data4.bin data5.bin
data5.bin
bandit12@bandit:/tmp/hellog0d$ ls
data2.bin  data2.bin.out  data4.bin  data5.bin  data6.bin.out  data8.bin  data9.bin  data.txt
bandit12@bandit:/tmp/hellog0d$
```

- data5.bin is another POSIX file, use tar again. You have to be checking the file and its compression type to choose the right command, do the steps until you have a readable file with the password.

```
bandit12@bandit:/tmp/hellog0d$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/hellog0d$ tar -xvf data5.bin data6.bin
data6.bin
bandit12@bandit:/tmp/hellog0d$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/hellog0d$ file data6.bin.out
data6.bin.out: POSIX tar archive (GNU)
bandit12@bandit:/tmp/hellog0d$ bzip -d data6.bin
Command 'bzip' not found, but there are 20 similar ones.
bandit12@bandit:/tmp/hellog0d$ bzip2 -d data6.bin
bzip2: Can't guess original name for data6.bin -- using data6.bin.out
bzip2: Output file data6.bin.out already exists.
bandit12@bandit:/tmp/hellog0d$ tar -xvf data6.bin.out
data8.bin
bandit12@bandit:/tmp/hellog0d$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Sep  1 06:30:09 2022, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/hellog0d$ zcat data8.bin > data9.bin
bandit12@bandit:/tmp/hellog0d$ file data9.bin
data9.bin: ASCII text
bandit12@bandit:/tmp/hellog0d$ cat data9.bin
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:/tmp/hellog0d$
```

## Notas adicionales
