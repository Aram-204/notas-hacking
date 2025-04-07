# Descripción
Do you know how to use the web inspector?Start searching [here](http://titan.picoctf.net:58649/) to find the flag
Hints:
1. Use the web inspector on other files included by the web page.
2. The flag may or may not be encoded
# Solución
- Entramos a la página que nos da
- Usamos el inspector para ver el código, no encontraremos nada en la página principal pero si nos vamos a la página "about" encontraremos un texto extraño
- Vamos a cyberchef y lo convertimos de magic para ver de que se trata
- Nos dará la bandera
```
picoCTF{web_succ3ssfully_d3c0ded_07b91c79}
```
# Notas adicionales
# Referencias