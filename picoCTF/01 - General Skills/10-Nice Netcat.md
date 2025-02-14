# Descripción
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 43239`, but it doesn't speak English...

Hints:
1. You can practice using netcat with this picoGym problem: [what's a netcat?](https://play.picoctf.org/practice/challenge/34)
2. You can practice reading and writing ASCII with this picoGym problem: [Let's Warm Up](https://play.picoctf.org/practice/challenge/22)
# Solución
Con Cybercchef
```
Input:
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
55 
99 
48 
56 
50 
49 
102 
53 
125 
10 

Receipe: From Decimal

Output: picoCTF{g00d_k1tty!_n1c3_k1tty!_7c0821f5}

picoCTF{g00d_k1tty!_n1c3_k1tty!_7c0821f5}
```

# Notas adicionales
- También se puede hacer usando python
# Referencias
https://gchq.github.io/CyberChef/#recipe=From_Decimal('Space',false)&input=MTEyIA0KMTA1IA0KOTkgDQoxMTEgDQo2NyANCjg0IA0KNzAgDQoxMjMgDQoxMDMgDQo0OCANCjQ4IA0KMTAwIA0KOTUgDQoxMDcgDQo0OSANCjExNiANCjExNiANCjEyMSANCjMzIA0KOTUgDQoxMTAgDQo0OSANCjk5IA0KNTEgDQo5NSANCjEwNyANCjQ5IA0KMTE2IA0KMTE2IA0KMTIxIA0KMzMgDQo5NSANCjU1IA0KOTkgDQo0OCANCjU2IA0KNTAgDQo0OSANCjEwMiANCjUzIA0KMTI1IA0KMTAg&ieol=CRLF