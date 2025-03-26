# Descripción
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:29649/](http://mercury.picoctf.net:29649/)
# Solución
En nuestra máquina virtual abrimos la página para ver los resultados 
- Si usamos la  opción que nos indica nos permitirá pasar pero no nos dará la bandera
- Entonces en nuestra terminal usaremos un for junto con un grep para encontrar el valor que tiene la cookie con nuestra bandera, así como también obtenerla
- Se muestra el ejemplo en lo siguiente:
```

┌──(kali㉿kali)-[~]
└─$ for i in {0..20}; do curl -s http://mercury.picoctf.net:29649/check -H "Cookie: name=$i"; done | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}</code></p>

picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}
```
# Notas adicionales
# Referencias
- https://www.youtube.com/watch?v=LseQ-XWCXVo&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=12