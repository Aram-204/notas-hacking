# Descripción
Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer.`ssh -p 54740 ctf-player@saturn.picoctf.net`. The password is `483e80d4`
Hints:
1. What programs do you have access to?
# Solución
- Entramos al servidor que nos da
- Usamos ls para ver que archivos tenemos y nos daremos cuenta de que no encuentra el comando, entonces tendremos que usar otra forma para movernos
- Usamos pwd para ver nuestro directorio y lo encontraremos
- Si tratamos de usar cat también nos dirá que no se reconoce el comando
- Tratamos con echo y veremos que si funciona
- Tratamos con help y veremos que funciona
- Buscaremos alguna forma de mostrar los datos el contenido de un archivo usando echo
- Encontraremos la siguiente sintaxis:
```
echo "$(<my_file.txt)"
```
- Así que lo usaremos con un * para que nos muestre los archivos con los que contamos
```
Specialer$ echo *
abra ala sim
```
- Abriremos cada uno de los archivos con la sintaxis que encontramos
- Nos daremos cuenta de que no se muestra nada, tal vez son directorios
- Así que usaremos la misma sintaxis con cierto juego de palabra para poder encontrar algo
```
Specialer$ echo "$(<abra/cadabra.txt)"
Nothing up my sleeve!
Specialer$ echo "$(<abra/kazam.txt)"
-bash: abra/kazam.txt: No such file or directory

Specialer$ echo "$(<ala/kazam.txt)"
return 0 picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_d5ef8b71}
Specialer$

picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_d5ef8b71}
```
- Y obtendremos la bandera
# Notas adicionales
# Referencias
- https://unix.stackexchange.com/questions/63658/redirecting-the-content-of-a-file-to-the-command-echo