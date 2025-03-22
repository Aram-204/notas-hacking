# Descripción
Can you break into this super secure portal? `https://jupiter.challenges.picoctf.org/problem/6353/` ([link](https://jupiter.challenges.picoctf.org/problem/6353/)) or http://jupiter.challenges.picoctf.org:6353
Hints:
1. What is obfuscation?
# Solución
- Entramos a ver el código fuente de la página, podemos ver que hay código enfucado
- Para desenfuscar el código usamos una página [Ref1], al tener el código desenfuscado y podemos ver que hay un arreglo con la bandera, la podemos construir con intuición eliminando las partes que tienen espacio o que pueden ser fracciones del códigoy de esa forma la obtenemos
```
picoCTF{not_this_again_50a029}
```
# Notas adicionales
# Referencias
- http://jsnice.org/