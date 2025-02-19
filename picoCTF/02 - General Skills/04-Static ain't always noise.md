# Descripción
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static)? This [BASH script](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh) might help!
# Solución
```
amv204-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static
--2025-02-19 01:55:35--  https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8376 (8.2K) [application/octet-stream]
Saving to: 'static'

static                       100%[=============================================>]   8.18K  --.-KB/s    in 0s      

2025-02-19 01:55:35 (260 MB/s) - 'static' saved [8376/8376]

amv204-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh
--2025-02-19 01:56:03--  https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 785 [application/octet-stream]
Saving to: 'ltdis.sh'

ltdis.sh                     100%[=============================================>]     785  --.-KB/s    in 0s      

2025-02-19 01:56:03 (403 MB/s) - 'ltdis.sh' saved [785/785]

amv204-picoctf@webshell:~$ file ltdis.sh
ltdis.sh: Bourne-Again shell script, ASCII text executable
amv204-picoctf@webshell:~$ chmod +x static
amv204-picoctf@webshell:~$ ./static
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
amv204-picoctf@webshell:~$ bash ^C
amv204-picoctf@webshell:~$ bash ltdis.sh static
Attempting disassembly of static ...
Disassembly successful! Available at: static.ltdis.x86_64.txt
Ripping strings from binary with file offsets...
Any strings found in static have been written to static.ltdis.strings.txt with file offset
amv204-picoctf@webshell:~$ ls
ltdis.sh  static  static.ltdis.strings.txt  static.ltdis.x86_64.txt
amv204-picoctf@webshell:~$ nano ltdis.sh 
amv204-picoctf@webshell:~$ cat static.ltdis.strings.txt | grep pico
   1020 picoCTF{d15a5m_t34s3r_98d35619}


picoCTF{d15a5m_t34s3r_98d35619}
```
# Notas adicionales
- None
# Referencias
- https://webshell.picoctf.org/