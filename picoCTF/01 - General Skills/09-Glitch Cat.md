# Descripción
Our flag printing service has started glitching!

Additional details will be available after launching your challenge instance.

Hints:
1. ASCII is one of the most common encodings used in programming
2. We know that the glitch output is valid Python, somehow!
3. Press Ctrl and c on your keyboard to close your connection and return to the command prompt.
# Solución 1

Con Python
```
amv204-picoctf@webshell:~$ nc saturn.picoctf.net 63985
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'
^C
amv204-picoctf@webshell:~$ python
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'

'picoCTF{gl17ch_m3_n07_9c42a45d}'
```
# Notas adicionales
- Nos conectamos al puerto, y recibimos una cadena
- Luego nos pasamos a Python y pegamos la cadena
# Referencias
