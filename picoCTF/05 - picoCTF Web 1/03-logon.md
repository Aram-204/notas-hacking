# Descripción
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? `https://jupiter.challenges.picoctf.org/problem/15796/` ([link](https://jupiter.challenges.picoctf.org/problem/15796/)) or http://jupiter.challenges.picoctf.org:15796
Hints:
1. Hmm it doesn't seem to check anyone's password, except for Joe's?
# Solución
Entramos a la página que nos da
- En dicha página entramos a inspeccionar, si nos logeamos con cualquier usuario que no sea Joe podemos ver en las cookies que hay una variable llamada admin que se encuentra como false
- Si cambiamos la variable admin a True y recargamos la página podremos ver la bandera
```
picoCTF{th3_c0nsp1r4cy_l1v3s_6edb3f5f}
```
# Notas adicionales
# Referencias