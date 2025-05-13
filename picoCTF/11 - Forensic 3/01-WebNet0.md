# Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.
Hints:
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?
# Solución
- Descargamos los archivos que se nos da usando wget
- Usamos wireshark para abrir la captura de paquetes
- Según las pistas debemos de buscar en el TLS
- Si tratamos de seguir el stream no podremos verlo porque está encriptado
- Vamos a cargar la llave privada en "edición/preferencias/protocolos/TLS"
- Agregamos la llave RSA
- Una vez que la hayamos agregado se desencripta el tráfico, así que ahora si podemos seguir el stream TLS
- Para facilitar la búsqueda nos vamos a "edicion/Find/packet details/string"
- Encontramos la bandera, la copiamos y la habremos obtenido
```
Pico-Flag: picoCTF{nongshim.shrimp.crackers}
```
# Notas adicionales
# Referencias