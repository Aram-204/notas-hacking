# Descripción
A group of underground hackers might be using this legit site to communicate. Use your forensic techniques to uncover their messageTry it [here](http://standard-pizzas.picoctf.net:54274/)!
Hints:
1. In the country that doesn't exist, the flag persists
# Solución
- Entramos a la página que nos dan
- Descargamos la imagen cuya bandera no existe
- Si usamos file veremos que en efecto es una imagen
- Usamos exiftool y veremos que tiene divisiones grandes
- Si usamos strings tampoco será tan fácil encontrar la bandera
- Si usamos zsteg veremos que el buffer no es suficiente
- Si usamos eog notaremos que es una imagen muy grande
- Descargamos el editor de imagenes gimp
- Jugamos con el contraste y  no encontraremos nada así que habrá que usar otra cosa
- Descargamos stepic
- Leeremos la imagen para decodificarla con stepic -i -d y obtendremos la bandera
```
picoCTF{fl4g_h45_fl4g3e22f365}
```
# Notas adicionales
# Referencias