# Descripción
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?
Hints:
1. How can you be sure of the redaction?
# Solución
- Descargamos el archivo con wget
- Abrimos el archivo y copiamos su contenido
- Pegamos el contenido del archivo en otro lado y obtendremos la bandera
- En mi caso al copiar todo se volví visible el texto así que solamente copié la bandera
```
picoCTF{C4n_Y0u_S33_m3_fully}
```
# Notas adicionales
# Referencias