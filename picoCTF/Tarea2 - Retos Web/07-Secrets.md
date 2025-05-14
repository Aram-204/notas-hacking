# Descripción
We have several pages hidden. Can you find the one with the flag?The website is running [here](http://saturn.picoctf.net:63294/).
Hints:
1. folders folders folders
# Solución
- Entramos a la página
- Vemos el código fuente de la página y encontraremos que hay una carpeta llamada secret
- Entramos a la carpeta y nos llevará a una página que dice que estamos cercas de la bandera
- Encontraremos que hay otra carpeta "hidden"
- Agregamos al link para verla
- Veremos una página para logeo, así que inspeccionamos el código fuente
- Encontraremos que hay otro archivo "superhidden"
- Entramos y encontraremos la bandera
```
picoCTF{succ3ss_@h3n1c@10n_790d2615}
```
# Notas adicionales
# Referencias