# Descripción
Try [here](http://titan.picoctf.net:63034/) to find the flag
Hints:
1. Try using burpsuite to intercept request to capture the flag.
2. Try mangling the request, maybe their server-side code doesn't handle malformed requests very well.
# Solución
- Abrimos burpsuite
- Abrimos la página que nos indica
- Activamos "Intercept on"
- En la página ingresamos los datos que se piden
- Seleccionamos el botón "register"
- En bursuite pulsamos "forward"
- Nos dejará pasar de ese formulario y nos abrirá otro
- Ingresamos lo que queramos en ese formulario
- Presionamos "submit"
- En burpsuite eliminamos lo que ingresamos en el formulario, se encontrará hasta abajo
- Nos dará la bandera
```
picoCTF{#0TP_Bypvss_SuCc3$S_2e80f1fd}
```
# Notas adicionales
# Referencias