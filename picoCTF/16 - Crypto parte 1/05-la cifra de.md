# Descripción
I found this cipher in an old book. Can you figure out what it says? Connect with `nc jupiter.challenges.picoctf.org 58295`.
Hints:
1. There are tools that make this easy.
2. Perhaps looking at history will help
# Solución
- Nos conectamos al puerto que nos dan
- Nos dará un texto que parece estar encriptado con vigenere
- Necesitamos la llave, habrá que buscarla
- Como no sabemos la llave haremos un ataque de fuerza bruto usando una página
- Lo ingresamos en la página, nos decodificará el texto y obtendremos la bandera
```
picoCTF{b311a50_0r_v1gn3r3_c1ph3ra966878a}
```
# Notas adicionales
# Referencias