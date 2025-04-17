# Descripción
Help us test the form by submiting the username as `test` and password as `test!`The website running [here](http://saturn.picoctf.net:62165/).
Hints:
1. any redirections?
# Solución
- Entramos a la página que nos da
- Hacemos login con el usuario test y la contraseña test!
- Esto nos redireccionará a otra página en la cual hay un campo de texto que dice que busquemos la bandera
- Si vemos los datos network mientras avanzamos o regresamos de la página encontraremos un código base64 que sería el id de la página así que usaremos cyberchef para convertirlo a algo más legible
- Obtendremos la bandera
```
picoCTF{proxies_all_the_way_3d9e3697}
```
# Notas adicionales
# Referencias