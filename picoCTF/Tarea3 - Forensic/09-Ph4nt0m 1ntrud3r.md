# Descripción
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/a917f567b9cc0f1a730a7801b309955df4d2234a8114326857b9759e9e5d0453/myNetworkTraffic.pcap) and try to get the flag.
Hints:
1. Filter your packets to narrow down your search.
2. Attacks were done in timely manner.
3. Time is essential
# Solución
- Descargamos el archivo con wget
- Usaremos wireshark para ver el tráfico de mensajes
- Si vemos algunos paquetes veremos que su contenido está en base64 y en otros no tiene sentido convertirlos
- Filtramos los paquetes por longitud 12 o 4
- Como en las pistas nos dice que el tiempo es esencial las vamos a ordenar por tiempo
- Copiaremos la cadena de cada paquete y la convertiremos de base64 usando cyberchef
- Obtendremos la bandera
```
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_959f50d3}
```
# Notas adicionales
# Referencias