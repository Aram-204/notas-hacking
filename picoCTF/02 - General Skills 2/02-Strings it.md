# Descripción
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?
Hints:
1. [strings](https://linux.die.net/man/1/strings)
# Solución
```
amv204-picoctf@webshell:~$ wget https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings
--2025-02-19 01:38:17--  https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings                      100%[=============================================>] 757.84K  1.86MB/s    in 0.4s    

2025-02-19 01:38:17 (1.86 MB/s) - 'strings' saved [776032/776032]

amv204-picoctf@webshell:~$ ls
README.txt  datos  file  flag  hola  strings
amv204-picoctf@webshell:~$ file strings
strings: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=94ec6b5e9cef175e834e0f7fcaedeaa167603c90, not stripped
amv204-picoctf@webshell:~$ strings strings | grep pico
picoCTF{5tRIng5_1T_d66c7bb7}

picoCTF{5tRIng5_1T_d66c7bb7}
```
# Notas Adicionales
- Este reto es para aprender a usar el comando "strings", curiosamente coincide con el nombre del archivo que descargamos
# Referencias
- https://webshell.picoctf.org/