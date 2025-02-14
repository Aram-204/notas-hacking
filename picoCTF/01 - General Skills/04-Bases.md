# Descripción
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

Hints:
Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.
# Solución 1
Usando Cyberchef
```
Input: bDNhcm5fdGgzX3IwcDM1
Receipe: From Base64
Output: l3arn_th3_r0p35

picoCTF{l3arn_th3_r0p35}
```
# Solución 2
Con python
```
amv204-picoctf@webshell:~$ python
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import base64
>>> base64.b64decode('bDNhcm5fdGgzX3IwcDM1')
b'l3arn_th3_r0p35'
>>> 

picoCTF{l3arn_th3_r0p35}
```
# Notas adicionales
- En python se regresa la respuesta entre comillas con una b antes, solamente eliminamos esto y obtendremos la respuesta
# Referencias
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=YkROaGNtNWZkR2d6WDNJd2NETTE
https://webshell.picoctf.org/