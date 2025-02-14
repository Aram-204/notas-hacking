# Descripción
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.

Hints:
What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)
# Solución 1
Con python
```
amv204-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 4427 > datos
^C
amv204-picoctf@webshell:~$ ls
README.txt  datos  file  flag
amv204-picoctf@webshell:~$ cat datos| grep pico
picoCTF{digital_plumb3r_5ea1fbd7}

 picoCTF{digital_plumb3r_5ea1fbd7}
```
# Notas adicionales
- Guardamos los datos en un archivo para después extraer la bandera (flag)
# Referencias
https://webshell.picoctf.org/