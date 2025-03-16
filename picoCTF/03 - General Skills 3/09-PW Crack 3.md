# Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
Hints:
1. To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`
2. To exit `bvi` type `:q` and press enter.
3. The `str_xor` function does not need to be reverse engineered for this challenge.
# Solución
- Descargamos al archivo .py, la flag encriptada y el hash
- Entramos al hash para obtener la contraseña encriptada
- Utilizamos hash.com para obtener la contraseña que en este caso es 87ab
- corremos el archivo .py, ingresamos la contraseña que se nos pida y nos da la bandera
```
amv204-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.py
--2025-03-16 19:16:26--  https://artifacts.picoctf.net/c/17/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py                                                  100%[=======================================================================================================================================>]   1.31K  --.-KB/s    in 0s      

2025-03-16 19:16:26 (586 MB/s) - 'level3.py' saved [1337/1337]

amv204-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
--2025-03-16 19:16:37--  https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.92, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc                                        100%[=======================================================================================================================================>]      31  --.-KB/s    in 0s      

2025-03-16 19:16:37 (9.36 MB/s) - 'level3.flag.txt.enc' saved [31/31]

amv204-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/17/level3.hash.bin
--2025-03-16 19:18:41--  https://artifacts.picoctf.net/c/17/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.16, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin                                            100%[=======================================================================================================================================>]      16  --.-KB/s    in 0s      

2025-03-16 19:18:41 (4.29 MB/s) - 'level3.hash.bin' saved [16/16]

amv204-picoctf@webshell:~$ bvi level3.hash.bin

bvi version 1.4.0 Copyright (C) 1996-2014 by Gerhard Buergmann
amv204-picoctf@webshell:~$ python3 level3.py
Please enter correct password for flag: 87ab
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}

picoCTF{m45h_fl1ng1ng_cd6ed2eb}
```
# Notas adicionales
# Referencias
- https://webshell.picoctf.org/
- https://hashes.com/en/decrypt/hash