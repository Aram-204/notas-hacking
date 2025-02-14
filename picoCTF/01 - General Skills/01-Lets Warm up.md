# Descripción
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

Hints:
1. Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.
# Solución 1
Con Python

```
amv204-picoctf@webshell:~$ python
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> chr(0x70)
'p'

picoCTF{p}
```
`picoCTF{p}`

# Solución 2
Usando cyberchef
```
Input: 0x70
Recipe: From hex
Output: p
```
# Notas adicionales
- Puede usarse incluso el interprete de Python para convertir de hex a ascii

# Referencias
- https://www.rapidtables.com/convert/number/hex-to-ascii.html
- https://gchq.github.io/CyberChef/
