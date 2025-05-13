# Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.
Hints:
1. Try using a tool like Wireshark.
2. How can you decrypt the TLS stream?
# Solución
- Descargamos los archivos con wget
- Usamos wireshark para tener acceso a los paquetes y nos daremos cuenta de que los TLS están encriptados
- Vamos a preferencias/protocolos/TLS y cargamos la llave que tenemos para desencriptar los paquetes
- Veremos que hay una imagen que se está descargando la extraemos para examinarla
- Le hacemos un strings y obtendremos la bandera
- 
```
picoCTF{honey.roasted.peanuts}
```
# Notas adicionales
# Referencias