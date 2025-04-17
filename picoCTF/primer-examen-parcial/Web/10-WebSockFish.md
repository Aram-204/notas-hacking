# Descripción
Can you win in a convincing manner against this chess bot? He won't go easy on you!You can find the challenge [here](http://verbal-sleep.picoctf.net:54668/).
Hints:
1. Try understanding the code and how the websocket client is interacting with the server
# Solución
- Entramos a la página que nos dan
- Vemos el código fuente, ahpi encontraremos que hay un websocket
- Usamos el inspector y vemos la consola
- mandamos un mensaje mate con un número muy grande y veremos que no pasa
- Haremos lo mismo con un eval y nos dará la bandera
```
picoCTF{c1i3nt_s1d3_w3b_s0ck3t5_50441bef}
```
# Notas adicionales
- Websocket: es una forma de interactuar con un servidor
# Referencias