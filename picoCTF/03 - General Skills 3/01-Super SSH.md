# Descripción
Using a Secure Shell (SSH) is going to be pretty important.
Additional details will be available after launching your challenge instance.
Using a Secure Shell (SSH) is going to be pretty important.Can you `ssh` as `ctf-player` to `titan.picoctf.net` at port `59408` to get the flag?You'll also need the password `f3b61b38`. If asked, accept the fingerprint with `yes`.If your device doesn't have a shell, you can use: [https://webshell.picoctf.org](https://webshell.picoctf.org/)If you're not sure what a shell is, check out our Primer: [https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell)
Hints:
1. [https://linux.die.net/man/1/ssh](https://linux.die.net/man/1/ssh)
2. You can try logging in 'as' someone with `<user>`@titan.picoctf.net
3. How could you specify the port?
4. Remember, passwords are hidden when typed into the shell
# Solución
En el webshell usamos ssh para conectarnos a titan.picoctf.net con el nombre ctf-player y la contraseña se nos da ahí, al conectarnos se nos da la bandera
```
Hostname: titan.picoctf.net
Port:     59408
Username: ctf-player
Password: "se nos da"
```
```
amv204-picoctf@webshell:~$ ssh ctf-player@titan.picoctf.net -p 59408 
The authenticity of host '[titan.picoctf.net]:59408 ([3.139.174.234]:59408)' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:59408' (ED25519) to the list of known hosts.
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_3e293eea}
Connection to titan.picoctf.net closed.


picoCTF{s3cur3_c0nn3ct10n_3e293eea}
```
# Notas adicionales

# Referencias
- https://webshell.picoctf.org/
- [https://primer.picoctf.com/#_the_shell](https://primer.picoctf.com/#_the_shell)