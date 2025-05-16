# Descripción
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 43522`.
Hints:
1. Flag is not in the usual flag format
# Solución
- Nos conectamos al puerto que nos dan
- Nos dará un mensaje  cifrado
- Es un cifrado por sustitución
- Usaremos una página para desencriptar
- copiamos el texto usando xclip
- lo pasamos a la página y nos dará el mensaje desencriptado
- Obtendremos la bandera
```
amv@LAPTOP-1MU6MBUF:~$ nc jupiter.challenges.picoctf.org 43522 | xclip -selection c

congrats here is your flag - frequency_is_c_over_lambda_ogfmaunraf

frequency_is_c_over_lambda_ogfmaunraf
```
# Notas adicionales
# Referencias