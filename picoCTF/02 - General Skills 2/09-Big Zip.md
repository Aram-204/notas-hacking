# Descripción
Unzip this archive and find the flag.
- [Download zip file](https://artifacts.picoctf.net/c/505/big-zip-files.zip)
Hints:
1. Can grep be instructed to look at every file in a directory and its subdirectories?
# Solución
```
Primero descargamos y descomprimimos el archivo .zip
después:
amv204-picoctf@webshell:~$ ls
big-zip-files  big-zip-files.zip
amv204-picoctf@webshell:~$ grep -R picoCTF{
.python_history:'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}

picoCTF{gr3p_15_m4g1c_ef8790dc}
```
# Notas adicionales
- Este problema nos sirve para ver la capacidad de el comando "grep", este busca la cadena de caracteres que le especifiquemos 
# Referencias
- https://webshell.picoctf.org/