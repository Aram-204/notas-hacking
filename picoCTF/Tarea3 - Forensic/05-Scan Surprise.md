# Descripción
I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/3/challenge.zip)

The same files are accessible via SSH here:`ssh -p 63400 ctf-player@atlas.picoctf.net`Using the password `6dd28e9b`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
Hints:
1. QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.
2. Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11
3. If you don't have access to a phone, you can also use zbar-tools to convert an image to text
# Solución
- Descargamos el archivo con wget
- Lo descomprimimos con unzip
- Entramos a la carpeta que nos da junto a las que están dentro hasta encontrar el archivo flag.png
- Abrimos la imagen y nos da un código qr
- Usamos una página para que nos de el texto y obtendremos la bandera
```
picoCTF{p33k_@_b00_a81f0a35}
```
# Notas adicionales
# Referencias
- https://scanqr.org/