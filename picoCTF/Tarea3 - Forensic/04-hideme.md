# Descripción
Every file gets a flag.The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/256/flag.png).
# Solución
- Descargamos el archivo con wget
- Hacemos strings al archivo y no veremos nada
- Usaremos binwalk y encontraremos que hay archivos dentro
- Extraeremos los archivo que están dentro usando binwalk
- Entramos a la carpeta que extrajimos hasta encontrar el archivo flag.png
- Descargaremos la imagen flag usando sz
- Abrimos la imagen y obtendremos la bandera
```
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_85e04ab8}
```
# Notas adicionales
# Referencias