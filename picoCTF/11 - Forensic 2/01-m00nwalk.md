# Descripción
Decode this [message](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) from the moon.
Hints:
1. How did pictures from the moon landing get sent back to Earth?
2. What is the CMU mascot?, that might help select a RX option
# Solución
- Descargamos el archivo usando wget
- En la pista nos dice que investiguemos como llegaron las fotos de la luna a la tierra
- Si buscamos encontraremos que se envía en un audio de forma codificada
- Buscamos un decodificador en línea
- En las pistas también nos decía que teníamos que usar algo llamado Scottie
- Nos movemos a la carpeta opt y clonamos un repositorio que encontramos en línea
```
amv@LAPTOP-1MU6MBUF:~$ cd /opt
amv@LAPTOP-1MU6MBUF:/opt$ sudo git clone https://github.com/colaclanth/sstv.git
amv@LAPTOP-1MU6MBUF:/opt$ cd sstv/
amv@LAPTOP-1MU6MBUF:/opt/sstv$ sudo python3 setup.py install
```
- Nos vamos a la carpeta donde tenemos el archivo y decodificamos
```
sstv -d message.wav -o result.png
```
- Abrimos la imagen
- Nos daremos cuenta de que está invertida
- La invertiremos con la interfaz gráfica de kali y obtendremos la bandera
```
picoCTF{beep_boop_im_in_space}
```
# Notas adicionales
# Referencias