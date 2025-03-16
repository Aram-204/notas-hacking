# Descripción
Find the flag in the Python script![Download Python script](https://artifacts.picoctf.net/c/36/serpentine.py)
Hints:
1. Try running the script and see what happens
2. In the webshell, try examining the script with a text editor like `nano`
3. To exit `nano`, press Ctrl and x and follow the on-screen prompts.
4. The `str_xor` function does not need to be reverse engineered for this challenge.
# Solución
- Descargamos los archivos utilizando wget
- Si corremos el programa podemos ver que si queremos imprimir la bandera nos muestra un mensaje en lugar de mostrar la contraseña
- Entramos a ver el codigo .py y mandamos a llamar la función print_flag()
- Volvemos a correr el programa y ahora nos muestra la bandera
```
amv204-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/36/serpentine.py
--2025-03-16 19:28:41--  https://artifacts.picoctf.net/c/36/serpentine.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.128, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2550 (2.5K) [application/octet-stream]
Saving to: 'serpentine.py'

serpentine.py                                              100%[=======================================================================================================================================>]   2.49K  --.-KB/s    in 0s      

2025-03-16 19:28:41 (1.15 GB/s) - 'serpentine.py' saved [2550/2550]

amv204-picoctf@webshell:~$ python3 serpentine.py

    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~

Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b

Oops! I must have misplaced the print_flag function! Check my source code!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) c
amv204-picoctf@webshell:~$ nano serpentine.py
amv204-picoctf@webshell:~$ python3 serpentine.py

    Y
  .-^-.
 /     \      .- ~ ~ -.
()     ()    /   _ _   `.                     _ _ _
 \_   _/    /  /     \   \                . ~  _ _  ~ .
   | |     /  /       \   \             .' .~       ~-. `.
   | |    /  /         )   )           /  /             `.`.
   \ \_ _/  /         /   /           /  /                `'
    \_ _ _.'         /   /           (  (
                    /   /             \  \
                   /   /               \  \
                  /   /                 )  )
                 (   (                 /  /
                  `.  `.             .'  /
                    `.   ~ - - - - ~   .'
                       ~ . _ _ _ _ . ~

Welcome to the serpentine encourager!


a) Print encouragement
b) Print flag
c) Quit

What would you like to do? (a/b/c) b
picoCTF{7h3_r04d_l355_7r4v3l3d_aa2340b2}
a) Print encouragement
b) Print flag
c) Quit

picoCTF{7h3_r04d_l355_7r4v3l3d_aa2340b2}
```
# Notas adicionales
# Referencias
- https://webshell.picoctf.org/