# Descripción
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.
Hints:
1. Try using a tool like Wireshark
2. What are streams?
# Solución
- Usamos wireshark "archivo" &
- Seleccionamos un archivo TCP o UDP
- En este caso es UDP
- Si aumentamos el número de stream encontraremos la bandera
```
picoCTF{StaT31355_636f6e6e}
```
# Notas adicionales
# Referencias