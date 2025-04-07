# Descripción
I found a web app that can help process images: PNG images only!

Additional details will be available after launching your challenge instance.

# Solución
- Entramos a la página que nos da
- Podemos ver que solamente se nos permite subir archivos con extensión .png que contenga los bytes mágicos (Son los que van al inicio)
- Si vemos los archivos robots.txt podemos ver que hay una carpeta uploads
- Para hacer una inserción creamos un webshell con extensión .php que le pediremos a chatgpt
- Para engañar a la página le ponemos la extensión .png a nuestro archivo
- Para que tenga los magic Bytes ponemos PNG al inicio del archivo
- Podremos subir el archivo con esto
- Entonces nos podremos mover mediante el link
- Podremos entrar a la careta uploads y desde ahí pasamos el parámetro cmd y ls
- Podemos ver en que carpeta estamos usando el comando pwd
- Para movernos atrás ponemos ls ..
- Podemos ver un archivo extraño
- Le haceos cat a ese archivo y ahí podremos encontrar la bandera
```
picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_ab0ece03}
```
# Notas adicionales
# Referencias
- https://www.youtube.com/watch?v=co8MZmviC1U