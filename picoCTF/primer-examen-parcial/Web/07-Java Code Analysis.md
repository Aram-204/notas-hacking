# Descripción
BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/484/bookshelf-pico.zip).Website can be accessed [here!](http://saturn.picoctf.net:57839/).
Hints:
1. Maybe try to find the JWT Signing Key ("secret key") in the source code? Maybe it's hardcoded somewhere? Or maybe try to crack it?
2. The 'role' and 'userId' fields in the JWT can be of interest to you!
3. The 'controllers', 'services' and 'security' java packages in the given source code might need your attention. We've provided a README.md file that contains some documentation.
4. Upgrade your 'role' with the _new_ (cracked) JWT. And re-login for the new role to get reflected in browser's localStorage.
# Solución
- Entramos a la página que nos dan, descargamos el archivo que nos dan
- Observamos los archivos que descargamos
- Si nos logeamos veremos que está la bandera en la página y que solamente el admin puede acceder a ella
- Si inspeccionamos la página en la parte de Storage encontraremos el token JWT
- Usaremos una página para modificar el token
- Como en el código de java vemos que se envía 1234 como contraseña para el admin utilizaremos el decodificador para cambiar esa parte
- Cambiaremos el rol como admin
- En el inspector cambiamos el token por el que obtuvimos
- También cambiamos el id del usuario por 2 y ahora nos permitirá abrir el libro de la bandera
```
picoCTF{w34k_jwt_n0t_g00d_6e5d7df5}
```
# Notas adicionales
# Referencias
- https://jwt.io/