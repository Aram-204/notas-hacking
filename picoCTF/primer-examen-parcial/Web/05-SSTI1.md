# Descripción
I made a cool website where you can announce whatever you want! Try it out!I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:65380/)!
Hints:
1. Server Side Template Injection
# Solución
- Entramos a la página que nos da, veremos que hay campo de texto
- Si ponemos algún texto dentro de doble corchete veremos que las acciones que ponemos se ejecutan
- Entramos a una página para poder hacer una inyección por medio de la vulnerabilidad que encontramos
- Nosotros usaremos la siguiente inyección
```
{{request.application.__globals__.__builtins__.__import__('os').popen('id').read()}}
```
- Al ejecutarlo podremos ver id´s como se verían en un comando de linux
- Ahora que vemos que este "payload" funciona lo único que haremos es quitar el comando id y usaremos ls para ver el contenido del direcctorio
- Veremos que hay un archivo llamado flag, así que le haremos un cat y obtendremos la bandera
```
# picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_73c99823}
```
# Notas adicionales
# Referencias
- https://www.onsecurity.io/blog/server-side-template-injection-with-jinja2/
