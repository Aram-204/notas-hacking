# Descripción
This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/fb851c1858cc762bd4eed569013d7f00/flag).
# Solución 1
Con python
```
amv204-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/fb851c1858cc762bd4eed569013d7f00/flag
--2025-02-13 18:35:07--  https://mercury.picoctf.net/static/fb851c1858cc762bd4eed569013d7f00/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                                                       100%[=======================================================================================================================================>]      34  --.-KB/s    in 0s      

2025-02-13 18:35:07 (14.1 MB/s) - 'flag' saved [34/34]

amv204-picoctf@webshell:~$ cat flag
picoCTF{s4n1ty_v3r1f13d_28e8376d}
```
# Notas adicionales
- Solamente existe la solución que implementamos que es usando python
# Referencias
https://webshell.picoctf.org/