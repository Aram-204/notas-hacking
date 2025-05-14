# Descripción
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.

Additional details will be available after launching your challenge instance.
Hinta:
1. Experiment with different shell syntax
# Solución
```
amv204-picoctf@webshell:~$ ssh -p 62334 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:62334 ([13.59.203.175]:62334)' can't be established.
ED25519 key fingerprint is SHA256:tJ0wuU5yBvNO/FrkHmR9iY36VJClMhKV+Hq2sxqKFmg.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:62334' (ED25519) to the list of known hosts.
ctf-player@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

Special$ ls
Is 
sh: 1: Is: not found
Special$ Is
Is 
sh: 1: Is: not found
Special$ ls -la
Is la 
sh: 1: Is: not found
Special$ help
Help 
sh: 1: Help: not found
Special$ Help
Help 
sh: 1: Help: not found
Special$ HELP
HELP 
sh: 1: HELP: not found
Special$ (echo "Prueba subshell")
Why go back to an inferior shell?
Special$ ls && echo "Comando exitoso"
Is i echo commando exitoso" 
sh: 1: Syntax error: Unterminated quoted string
Special$ ls | grep 'algo'
Is | grew algo 
sh: 1: Is: not found
sh: 1: grew: not found
Special$ cat pico
Cat pico 
sh: 1: Cat: not found
Special$ 'ls'
Also 
sh: 1: Also: not found
Special$ Ls
Is 
sh: 1: Is: not found
Special$ LS
Als 
sh: 1: Als: not found
Special$ Alias
Alias 
sh: 1: Alias: not found
Special$ alias
Alias 
sh: 1: Alias: not found
Special$ sudo cat pico
Judo cat pico 
sh: 1: Judo: not found
Special$ type ls
Type is 
sh: 1: Type: not found
Special$ ms
Is 
sh: 1: Is: not found
Special$ cd
Ad 
sh: 1: Ad: not found
Special$ dc
Do 
sh: 1: Do: not found
Special$ is
Is 
sh: 1: Is: not found
Special$ IS
IS 
sh: 1: IS: not found
Special$ Is
Is 
sh: 1: Is: not found
Special$ Ds
Is 
sh: 1: Is: not found
Special$ Cs
Is 
sh: 1: Is: not found
Special$ cls
Cos 
sh: 1: Cos: not found
Special$ clear
Clear 
sh: 1: Clear: not found
Special$ lS
Is 
sh: 1: Is: not found
Special$ $(ls)
$(ls) 
sh: 1: blargh: not found
Special$ \c\a\t \b\l\a\r\g\/\f\l\a\g\.\t\x\t
\c\a\t \b\l\a\r\g\/\f\l\a\g\.\t\x\t 
cat: blarg/flag.txt: No such file or directory
Special$ \c\a\t \b\l\a\r\g\h\/\f\l\a\g\.\t\x\t
\c\a\t \b\l\a\r\g\h\/\f\l\a\g\.\t\x\t 
picoCTF{5p311ch3ck_15_7h3_w0r57_a60bdf40}Special$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.

picoCTF{5p311ch3ck_15_7h3_w0r57_a60bdf40}
```
# Notas adicionales
- Intentamos con la sintaxis normal, al ver que no funciona utilizamos caracteres de escape y comandos interpolados
# Referencias