# Descripción
Can you get the real meaning from this file.Download the file [here](https://artifacts.picoctf.net/c_titan/3/enc_flag).
Hints:
1. Engaging in various decoding processes is of utmost importance
# Solución
- Descargamos el archivo que contiene la bandera encriptada
- Si usamos file veremos que es un texto en ASCII
- Usaremos base64 para que nos de el texto en dicho formato
- Llevamos ese texto a cyberchef con sus respectivas rectas
- Obtendremos la bandera
```
amv@LAPTOP-1MU6MBUF:~$ wget https://artifacts.picoctf.net/c_titan/3/enc_flag
--2025-05-16 13:17:38--  https://artifacts.picoctf.net/c_titan/3/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.225.222.105, 13.225.222.120, 13.225.222.28, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.225.222.105|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 73 [application/octet-stream]
Saving to: ‘enc_flag’

enc_flag                 100%[===============================>]      73  --.-KB/s    in 0s

2025-05-16 13:17:42 (5.63 MB/s) - ‘enc_flag’ saved [73/73]

amv@LAPTOP-1MU6MBUF:~$ file enc_flag
enc_flag: ASCII text
amv@LAPTOP-1MU6MBUF:~$ base64 -d enc_flag
b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ=='


Cyberchef
Input: d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2kyMDRoa2o2fQ==
Receipe: From base64 y ROT 13 con 19 rotaciones
Output: picoCTF{caesar_d3cr9pt3d_b204adc6}

picoCTF{caesar_d3cr9pt3d_b204adc6}
```
# Notas adicionales
# Referencias