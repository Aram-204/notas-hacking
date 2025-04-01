# Descripción
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?
Hints:
1. How do operating systems know what kind of file it is? (It's not just the ending!
2. Make sure to submit the flag as picoCTF{XXXXX}
# Solución
- Descargamos la imagen con wget
- Usamos file "archivo" para que nos diga el tipo de archivo que es
- Cambiamos la extension del archivo y la abrimos:
```
┌──(kali㉿kali)-[~/Documents]
└─$ mv flag.txt flag.png
                                                                     
┌──(kali㉿kali)-[~/Documents]
└─$ open flag.png 

```
- En la imagen está la bandera
```
picoCTF{now_you_know_about_extensions}
```
# Notas adicionales
# Referencias