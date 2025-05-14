# Descripción
How about some hide and seek?Download this file [here](https://artifacts.picoctf.net/c_titan/129/unknown.zip).
Hints:
1. How can you view the information about the picture?
2. If something isn't in the expected form, maybe it deserves attention?
# Solución
- Descargamos el archivo usando wget
- Encontraremos un archivo .jpg
- Usaremos exiftool para ver los datos del archivo
- En Atributio URL encontraremos un texto sospechoso
- Usaremos cyberchef para convertirlo de base64
- Encontraremos la bandera
```
picoCTF{ME74D47A_HIDD3N_b32040b8}
```
# Notas adicionales
# Referencias