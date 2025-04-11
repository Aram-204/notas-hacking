# Descripción
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.
Hints:
1. Try fixing the file header
# Solución
- Descargamos el archivo con wget
- Si vemos el encabezado del archivo podemos ver que hay indicios de quesea un archivo png y
- Podemos observar que los bytes que deben de estar en la cabecera no están bien, así que usaremos un editor hexadecimal para eso
```
┌──(kali㉿kali)-[~/hacking]
└─$ hexeditor mystery   
```
- Hacemos las modificaciones necesarias para que en el encabezado nos quede 89 50 4E 47 0D 0A 1A 0A
- Guardamos y veremos que aún no es reconocido como un archivo valido
- Después del encabezado vienen los chuncks que pueden ser varios
- Generalmente se conforman de 4 partes:
	- Longitud
	- tipo
	- Datos
	- Bytes de redundancia cíclica que nos ayuda a corroborar que los bytes de datos corresponde al tamaño adecuado del chunck
- Después del encabezado viene un chunck crítico que se debe de llamar IHDR
- En nuestro caso no tiene el nombre que debería, así que vamos a editar de nuevo con el editor hexadecimal para corregir eso poniendo las letra IHDR en hexadecimal, es decir, 49 48 44 52
- Volvemos a checar y esta vez si nos reconoce que es png
- Pero si lo abrimos nos daremos cuenta de que aún existen errores en el archivo que impiden que el editor nos pueda abrir
- Instalaremos un software que nos va a ayudar en la tarea
```
┌──(kali㉿kali)-[~/hacking]
└─$ sudo apt install pngcheck  
```
- Esta herramienta checa la integridad de los archivos png, en este caos nos ayudará a verificar que es lo que está mal
```
┌──(kali㉿kali)-[~/hacking]
└─$ pngcheck -v mystery 
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in mystery
```
- Como podemos ver hay un error de redundancia cíclica en el chunck pHYs, nos genera números muy altos, así que iremos al editor hexadecimal nuevamente
- Según la documentación este chunck contiene la resolución de la imagen
- Lo modificamos para una imagen cuadrada que sería poner los valores 00 en lugar de AA
- Volveremos a checar
```
┌──(kali㉿kali)-[~/hacking]
└─$ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in mystery
```
- Como podemos ver hay un error con el siguiente chunck
- Entramos de nuevo al editor
- Sigue el chunck IDAT pero en nuestra imagen tiene el nombre DETx
- Pondremos el nombre correcto con el editor
- Volvemos a verificar
```
┌──(kali㉿kali)-[~/hacking]
└─$ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in mystery
```
- Nos sigue diciendo que el chunck es muy grande, entramos al editor para cambiar la longitud
- Podremos ver que es muy grande y generalmente con solo 2 bytes es suficiente para la longitud
- Volvemos a verificar
```
┌──(kali㉿kali)-[~/hacking]
└─$ pngcheck -v mystery
zlib warning:  different version (expected 1.2.13, using 1.3.1)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  chunk IDAT at offset 0x00057, length 65445
    zlib: deflated, 32K window, fast compression
  chunk IDAT at offset 0x10008, length 65524
  chunk IDAT at offset 0x20008, length 65524
  chunk IDAT at offset 0x30008, length 6304
  chunk IEND at offset 0x318b4, length 0
No errors detected in mystery (9 chunks, 96.3% compression).
```
- Nos dice que no hay errores
- Abrimos la imagen con open "nombreArchivo" y obtendremos la bandera
```
picoCTF{c0rrupt10n_1847995}
```
# Notas adicionales
# Referencias