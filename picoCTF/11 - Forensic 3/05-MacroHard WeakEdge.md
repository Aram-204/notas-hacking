# Descripción
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/c0da20f29337e87ffb58ea987d8c596e/Forensics%20is%20fun.pptm)
# Solución
- Descargamos el archivo con wget
- Vemos el tipo de archivo con file, podremos ver que es un powerpoint
- Podemos ver que tiene archivos que pueden ser desempaquetados con unzip
- Hay muchas carpetas, primero intentamos con un grep y no encontraremos la bandera
- Usaremos un editor de texto, en mi caso usaré visual studio code
- Abrimos visual desde la carpeta en la que tenemos el reto
- Dentro de las carpetas encontraremos un archivo llamado hidden, dentro de este archivo podremos ver un texto aparentemente escrito en base 64 
- Lo copiamos y en la consola le borramos los espacios en blanco y lo convertimos de base64
- Obtendremos la bandera
```
┌──(kali㉿kali)-[~/hacking]
└─$ echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q" | tr -d " " | base64 -d
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5} 

picoCTF{D1d_u_kn0w_ppts_r_z1p5} 
```
# Notas adicionales
# Referencias