# Descripción
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/50522/` ([link](https://jupiter.challenges.picoctf.org/problem/50522/)) or http://jupiter.challenges.picoctf.org:50522
Hints:
1. You don't need to download a new web browser
# Solución
- Podemos ver en el navegador en flag que se nos pide un navegador especifico, en inspeccionar/network en el archivo flag
- En el navegador entramos a inspeccionar en la página, damos click en el botón "Flag", en inspeccionar seguimos los siguiente pasos para el navegador brave:
	- damos click en los 3 puntos en la parte superior derecha "More tools", después "Network conditions" ahí dentro en el User agent ponemos "picobrowser", recargamos la página y nos dará la bandera
```
picoCTF{p1c0_s3cr3t_ag3nt_51414fa7}
```
# Notas adicionales
# Referencias