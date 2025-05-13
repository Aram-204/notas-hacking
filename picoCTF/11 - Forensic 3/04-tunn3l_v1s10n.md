# Descripción
We found this [file](https://mercury.picoctf.net/static/06a5e4ab22ba52cd66a038d51a6cc07b/tunn3l_v1s10n). Recover the flag.
Hints:
1. Weird that it won't display right...
# Solución
- Descargamos el archivo con wget
- Preguntamos su tipo con file, veremos que son datos
- En las pistas nos dice que está rebuscado
- Vemos el encabezado en hexadecimal
- Veremos que es un archivo bitmap hecho en windows
-  Abrimos el archivo con un editor hexadecimal, pero ante cambiamos la extensión
- Si investigamos encontraremos que el tamaño del encabezado debe de ser de 40 bytes o 28 en hexadecimal y debe de ir en la posición 0E
- Cambiamos lo que se encuentra ahí por 28
- También de modificar el 0A porque ahí debe de tener 28 también
- Después de estas modificaciones podremos abrir la imagen pero no encontraremos la bandera aún
- Usaremos exiftool para ver los metadatos
- Veremos que el alto es poco, así que lo modificaremos
- Si abrimos la imagen ahora podremos ver la bandera
```
picoCTF{qu1t3_a_v13w_2020}
```
# Notas adicionales
# Referencias