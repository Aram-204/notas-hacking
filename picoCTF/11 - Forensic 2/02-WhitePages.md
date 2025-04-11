# Descripción
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt) is all blank!
# Solución
- Descargamos el archivo con wget
- si vemos el tipo del archivo nos daremos cuenta de que es de tipo unicode
- Si mostramos en hecxadecimal lo que contiene el archivo veremos que e280 83 se repite mucho, buscamos que es y nos daremos cuenta de que es un espacio
- Lo que tenemos que hacer es convertir a 0 el espacio y que el espacio 20 sea 1 porque se puede tratar de código morse o alguna codificación donde el espacio unicode es 0 y el otro 1
- Nos apoyaremos de una librería de python que habrá que instalar
```
python3 -m pip install pwntools
```
- Creamos un archivo .py con nano
```
from pwn import *

file = open('whitepages.txt', 'rb')
data = bytearray(file.read())
data = data.replace(b'\xe2\x80\x83',b'0')
data = data.replace(b'\x20',b'1')
data = data.decode('ascii') 
data = unbits(data)

print(data)
```
- Ejecutamos el código y nos dará la bandera
```
┌──(kali㉿kali)-[~/hacking]
└─$ python exp.py 
b'\n\t\tpicoCTF\n\n\t\tSEE PUBLIC RECORDS & BACKGROUND REPORT\n\t\t5000 Forbes Ave, Pittsburgh, PA 15213\n\t\tpicoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}\n\t\t'


picoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}
```
# Notas adicionales
# Referencias