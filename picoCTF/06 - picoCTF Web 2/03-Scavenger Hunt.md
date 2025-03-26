# Descripción
There is some interesting information hidden around this site [http://mercury.picoctf.net:44070/](http://mercury.picoctf.net:44070/). Can you find it?
Hints:
1. You should have enough hints to find the files, don't run a brute forcer.
# Solución
- Tenemos el link que se nos da: 
	- http://mercury.picoctf.net:44070/
	- En ese link agregamos las siguientes extensiones para poder acceder a los diferentes archivos ocultos y en cada parte de estos podremos encontrar partes de la bandera, también tendremos que buscar en el código fuente de la página, así como archivos .CSS o .js
```
Ejemplo:
http://mercury.picoctf.net:44070/robots.txt

robots.txt
.htaccess
.DS_Store
picoCTF{th4ts_4_l0t_0f_pl4c3s_2_lO0k_7a46d25d}
```
# Notas adicionales
# Referencias
- https://www.youtube.com/watch?v=E2gN3AGHirc&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=13