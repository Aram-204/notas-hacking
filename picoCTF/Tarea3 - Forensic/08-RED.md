# Descripción
RED, RED, RED, REDDownload the image: [red.png](https://challenge-files.picoctf.net/c_verbal_sleep/831307718b34193b288dde31e557484876fb84978b5818e2627e453a54aa9ba6/red.png)
Hints:
1. The picture seems pure, but is it though?
2. Red?Ged?Bed?Aed?
3. Check whatever Facebook is called now.
# Solución
- Descargamos el archivo
- Usamos file y veremos que es un archivo png
- Si usamos un strings veremos que está guardado el bit menos significativo
- Si vemos los metadatos encontraremos el mismo poema que con stings
- Veremos LSB usando sudo su
- Usaremos zsteg para extraer lsb, en mi caso para ser más especifico pediremos el canal rgba
- Nos dará eun texto en base64
- Lo convertimos a texto y obtendremos la bandera
```
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
```
# Notas adicionales
# Referencias