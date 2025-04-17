# Descripción
Connect to this PostgreSQL server and find the flag!`psql -h saturn.picoctf.net -p 57456 -U postgres pico`Password is `postgres`
Hints:
1. What does a SQL database contain?
# Solución
- Entramos al servidor usando el comando y contraseña que nos dan
- Usamos /? para ver las diferentes ramas
- Usamos \l para ver el contenido de la base de datos
- Vemos que hay una tabla pico
- Usamos \c pico para seleccionar la tabla pico
- Usamos \dt para las otras tablas
- Veremos que hay una tabla llamada flags
- Buscaremos como listar tablas en psql
- Haremos "select * from flags;"
- Obtendremos la bandera
```
picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
```
# Notas adicionales
# Referencias