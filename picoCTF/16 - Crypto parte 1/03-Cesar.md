# Descripción
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext).
Hints:
1. caesar cipher [tutorial](https://learncryptography.com/classical-encryption/caesar-cipher)
# Solución
- Descargamos el texto
- Le hacemos cat y veremos que es la la bandera encriptada
- En nuestro caso usaremos cyberchef para rotar cierto número de veces el mensaje ya que así funciona el algoritmo caesar
- En nuestro caso se rotó 30 veces el texto, esto lo sabemos porque al rotarlo ese número de veces podremos encontrar un texto que tiene sentido
- Así obtendremos la bandera
```
picoCTF{crossingtherubiconvfhsjkou}
```
# Notas adicionales
- También podemos hacer un programa que rote el texto automáticamente
# Referencias
