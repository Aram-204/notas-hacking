# Descripción
The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.
Hints:
1. Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{HELLO}' as the flag.
2. Please use all caps for the message.
# Solución
- Descargamos la tabla con wget
- La abrimos usando cat
- Buscamos one-time-path en el navegador
- Entramos a la página
- Ahí se nos pide el texto y la llave
- Nos dará la bandera
```
picoCTF{CRYPTOISFUN}
```
# Notas adicionales
# Referencias
- https://www.boxentriq.com/code-breaking/one-time-pad