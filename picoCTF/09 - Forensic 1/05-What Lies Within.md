# Descripción
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?
Hints:
1. There is data encoded somewhere... there might be an online decoder.
# Solución
- Descargamos el archivo con wget
- Podemos ver que es un archivo con extension .png
- Instalamos un paquete
```
sudo gem install zsteg 
```
- Usamos lo que instalamos para que nos busque bits escondidos en la png
```
zsteg -a buildings.png 

b1,r,lsb,xy         .. text: "^5>R5YZrG"
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
```
- Y nos da la bandera
```
picoCTF{h1d1ng_1n_th3_b1t5}
```
# Notas adicionales
- LBS: Se incrustan datos en archivos como imagenes, audios, videos, etc.
# Referencias