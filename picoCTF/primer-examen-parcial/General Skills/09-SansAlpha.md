# Descripción
The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.`ssh -p 49440 ctf-player@mimas.picoctf.net`Use password: `6dd28e9b`
Hints:
1. Where can you get some letters?
# Solución
- Nos conectamos al servidor usando ssh
- si tratamos de usar algún comando podremos notar que nos muestra un mensaje
```
SansAlpha$ ls
SansAlpha: Unknown character detected
SansAlpha$ cat
SansAlpha: Unknown character detected
SansAlpha$
```
- Entonces la única forma de entrar será usando números y otros símbolos
- Usaremos "* " para ver el directorio en el que nos encontramos
```
SansAlpha$ *
bash: blargh: command not found
```
- También podremos encontrar un archivo "flag.txt"
```
SansAlpha$ */*
bash: blargh/flag.txt: Permission denied
```
- Trataremos de usar base64 para imprimir nuestro archivo
- Para ello usaremos * para directorios y ? para comandos
```
SansAlpha$ /*/???[!_]64 */????.*
cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV8xNDUyNTZlY30=
```
- Lo que hacemos en este comando es especificar el archivo que queremos para que no coincida con algún otro. En este caso decimos que está dentro de un directorio con * y / el nombre con ? dependiendo del número de caracteres del nombre del archivo \[!_ ] para especificar que no queremos que contenga " _ " los números los lee igual así que los ponemos exactamente en la posición que van
- Con esto obtendremos el resultado de abrir el archivo con base64
- Esto nos devuelve el resultado en base64, solamente usamos cyberchef para convertir y obtendremos nuestra bandera
```
Input: cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV8xNDUyNTZlY30
Receipe: From Base64
Output: return 0 picoCTF{7h15_mu171v3r53_15_m4dn355_145256ec}

picoCTF{7h15_mu171v3r53_15_m4dn355_145256ec}
```
# Notas adicionales
# Referencias