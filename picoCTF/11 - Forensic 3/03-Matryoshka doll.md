# Descripción
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/b6205dd933ec01c022c4e6acbdf11116/dolls.jpg)
Hints:
1. Wait, you can hide files inside files? But how do you find them?
2. Make sure to submit the flag as picoCTF{XXXXX}
# Solución
- Descargamos el archivo con wget
- Si hacemos strings podremos darnos cuenta de que hay otra imagen dentro de la imagen
- Usamos la herramienta "binwalk" para confirmar que si hay otra imagen dentro de la imagen
- Extraemos la imagen con binwalk
- Si abrimos la imagen que extrajimos podremos ver a una Matryoshka
- Si la hacemos binwalk a esa imagen nos daremos cuenta de que hay otra imagen dentro, así que repetimos proceso
- Si volvemos a hacer binwalk nos percataremos de que existe otro archivo
- Hacemos este proceso 34 veces y encontraremos el archivo que contiene la bandera
- Hacemos un cat sobre el archivo flag y obtendremos la bandera
```
picoCTF{4f11048e83ffc7d342a15bd2309b47de} 
```
# Notas adicionales
# Referencias