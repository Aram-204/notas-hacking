# Descripción
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)
Hints:
1. On the webshell, use `ls` to see if both files are in the directory you are in
2. The `str_xor` function does not need to be reverse engineered for this challenge.
# Solución
```
amv204-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/code.py
--2025-03-15 20:33:10--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.128, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                                                    100%[=======================================================================================================================================>]   1.25K  --.-KB/s    in 0s      

2025-03-15 20:33:10 (550 MB/s) - 'code.py' saved [1278/1278]

amv204-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/3/codebook.txt
--2025-03-15 20:33:23--  https://artifacts.picoctf.net/c/3/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.92, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                                               100%[=======================================================================================================================================>]      27  --.-KB/s    in 0s      

2025-03-15 20:33:23 (1.55 MB/s) - 'codebook.txt' saved [27/27]

amv204-picoctf@webshell:~$ ls
code.py  codebook.txt
amv204-picoctf@webshell:~$ cat codebook.txt
azbycxdwevfugthsirjqkplomn
amv204-picoctf@webshell:~$ python3 code.py
picoCTF{c0d3b00k_455157_197a982c}
```
# Notas adicionales
- Solamente descargamos los archivos con extensión .txt y .py en el mismo directorio y después ejecutamos el archivo .py
# Referencias
- https://webshell.picoctf.org/