# Descripción
Can you get the flag?Go to this [website](http://saturn.picoctf.net:52536/) and see what you can discover.
Hints:
1. How is the password checked on this website?
# Solución
- Entramos a la página que nos da
- Vemos el código fuente de la página
- Nos daremos cuenta de que el formulario se envía a un archivo .php mediante el método post
- Si en el link ponemos /login.php nos dará un mensaje "Log in failed"
- Ahora si entramos a ver el código fuente de esa página encontraremos que el archivo envía el formulario a otro archivo "admin.php"
- También encontraremos que hay un archivo "secure.js"
- Si entramos a dicho archivo veremos que válida la contraseña la contraseña del admin, ahí nosotros obtendremos la contraseña para entrar al sistema con el usuario admin, la contraseña es "strongPassword098765"
- Si entramos a la página con el usuario admin y usamos la contraseña que encontramos en el . js podremos entrar y nos dará la bandera
```
picoCTF{j5_15_7r4n5p4r3n7_05df90c8}
```
# Notas adicionales
# Referencias