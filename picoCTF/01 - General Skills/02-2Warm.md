# Descripción
Can you convert the number 42 (base 10) to binary (base 2)?

Hints:
1. Submit your answer in our competition's flag format. For example, if your answer was '11111', you would submit 'picoCTF{11111}' as the flag.
# Solución 1
Usando Cyberchef
```
Input: 42
Receipe: From Decimal, To Binary
Output: 101010
```
# Solución 2
Con python
```
amv204-picoctf@webshell:~$ python
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> bin(42)
'0b101010'
>>

picoCTF{101010}
```
# Notas adicionales
- En el caso de python al usar la función bin() te regresa el número en binario con el prefijo 0b, simplemente lo eliminamos para la solución y así lo ingresamos a picoCTF
# Referencias
https://gchq.github.io/CyberChef/#recipe=From_Decimal('Space',false)To_Binary('Space',8)&input=NDI