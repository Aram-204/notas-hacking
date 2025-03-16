# Descripción
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29221`.

Hints:
1. I hear python can convert things.
2. It might help to have multiple windows open.
# Solución 1
Usando cyberchef

```
amv204-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 29221
Let us see how data is stored
lamp
Please give the 01101100 01100001 01101101 01110000 as a word.
...
you have 45 seconds.....
Input:
lamp
NOTA:
En este caso la conversión se hace de binario a palabra, aquí mismo se nos da

Please give me the  141 156 151 155 141 164 151 157 156 as a word.
Input:
animation
NOTA:
Para este caso la conversión es de Octal a palabra, usamos cyberchef con lo siguiente:
Input:141 156 151 155 141 164 151 157 156
Recipe: From Octal
Output: animation

Please give me the 736f636b6574 as a word.
Input:
socket
NOTA:
En este caso la conversión es de Hexadecimal a palabra, usamos cyberchef con lo siguiente:
Input: 736f636b6574
Recipe: From Hex
Output: socket

You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_00a975ff}
NOTA:
Al final se nos da la bandera

picoCTF{learning_about_converting_values_00a975ff}
```
# Notas adicionales
- Este ejercicio sirve para conocer las diferente conversiones que se pueden hacer en este ejemplo se usa Octal, Hexadecimal y binario

# Referencias
- https://webshell.picoctf.org/
- https://gchq.github.io/CyberChef/#recipe=From_Octal('Space'/disabled)From_Hex('None')&input=NzM2ZjYzNmI2NTc0