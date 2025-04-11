# Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
# Solución
- Descargamos el documento con wget
- Captura de paquetes es el tráfico de red que viaja en una fuente cliente servidor
- Vamos a usar whireshark para la apertura de paquetes
- Podemos ver que hay más paquetes UDP que otros, así que abriremos uno de los primeros paquetes
- Nos vamos a mover entre streams para ver si podemos encontrar señales de la bandera
- Si seguimos avanzando entre paquetes llegaremos al 60 donde encontraremos un texto "end", este y el primero comparten el puerto destino
- Vamos a filtrar los paquetes cuyo puerto destino sea el 22 y encontraremos un patrón en el puerto de salida
- Si usamos la función de python chr y ponemos el número de puerto menos 5000 nos daremos cuenta de que ahí está la bandera
- Como son muchos paquetes lo vamos a automatizar con python usando una librería de python "scapy"
- Usaremos un exploit
```
┌──(kali㉿kali)-[~/hacking]
└─$ nano exp.py
```

```
from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:          
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)
print(flag)
```
- corremos nuestro código y obtendremos la bandera
```
┌──(kali㉿kali)-[~/hacking]
└─$ python3 exp.py 
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```
# Notas adicionales
# Referencias