# Descripción
The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:53931/) out.
# Solución
- Entramos a la página que nos da
- Vemos el código fuente de la página ahí encontraremos un comentario curioso que nos dice "Aquí no estpa la bandera sigue cavando"
- Por el nombre del problema nos daremos cuenta de que se puede tratar de ver los archivo robots.txt
- Entonces agregamos /robots.txt al link de la página
- Ahí encontraremos un texto un poco curioso que parece estar en base64 
- Usamos cyberchef para ver que es y nos daremos cuenta de que es una dirección que podemos agregar al link para obtener algo
- Entonces nos dará ahí la bandera
```
picoCTF{Who_D03sN7_L1k5_90B0T5_032f1c2b}
```
# Notas adicionales
# Referencias