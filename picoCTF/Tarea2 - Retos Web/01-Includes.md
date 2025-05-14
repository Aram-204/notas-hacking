# Descripción
Can you get the flag?Go to this [website](http://saturn.picoctf.net:50889/) and see what you can discover.
Hints:
1. Is there more code than what the inspector initially shows?
# Solución
- Entramos a la página que se nos da, ahí veremos un texto y un botón
- Si damos click al botón veremos que dice que "este código está en un archivo separado"
- Si inspeccionamos el código fuente de la página podremos ver que hay un archivo .css y un archivo .js
- Al entrar en dichos archivo encontraremos una parte de la bandera en cada uno
```
picoCTF{1nclu51v17y_1of2_f7w_2of2_df589022}
```
# Notas adicionales
# Referencias