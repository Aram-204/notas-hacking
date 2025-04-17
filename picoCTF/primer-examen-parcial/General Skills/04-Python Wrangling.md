# Descripción
Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/ende.py) using [this password](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/pw.txt) to get [the flag](https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/flag.txt.en)?
Hints:
1. Get the Python script accessible in your shell by entering the following command in the Terminal prompt: `$ wget https://mercury.picoctf.net/static/8e33ede04d02f3765b8c6a6e24d72733/ende.py`
2. $ man python
# Solución
- Descargamos los archivos que nos dan
- entramos a ver el archivo pw.txt
- Copiamos la bandera
- Ejecutamos el programa, este nos pedirá la contraseña, la pegamos y obtenemos la bandera
```
┌──(kali㉿kali)-[~/hacking]
└─$ python3 ende.py -d flag.txt.en
Please enter the password:aa821c16aa821c16aa821c16aa821c16
picoCTF{4p0110_1n_7h3_h0us3_aa821c16}

picoCTF{4p0110_1n_7h3_h0us3_aa821c16}
```
# Notas adicionales
# Referencias