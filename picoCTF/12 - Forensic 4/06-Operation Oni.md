# Descripción
Download this disk image, find the key and log into the remote machine.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download disk image](https://artifacts.picoctf.net/c/71/disk.img.gz)
- Remote machine: `ssh -i key_file -p 53774 ctf-player@saturn.picoctf.net`
# Solución
- Descargamos la imagen que nos dan usando wget
- La descomprimimos usando gunzip
- Veremos las particiones con mmls
- Usamos fls para listar los directorios dentro de la imagen
- Vamos a la carpeta root
- Vamos a ssh y encontraremos la llave pública y privada
- Hacemos icat a la llave privada para obtenerla y a guardamos en un archivo
- Le daremos permisos de solo lectura para el usuario
- Nos logeamos a la instacia que nos da con la llave y ahí encontraremos la bandera
```
amv@LAPTOP-1MU6MBUF:~$ fls -o 206848 disk.img 470
r/r 2344:       .ash_history
d/d 3916:       .ssh
amv@LAPTOP-1MU6MBUF:~$ fls -o 206848 disk.img 3916
r/r 2345:       id_ed25519
r/r 2346:       id_ed25519.pub
amv@LAPTOP-1MU6MBUF:~$ icat -o 206848 disk.img 2345
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
amv@LAPTOP-1MU6MBUF:~$ icat -o 206848 disk.img 2345 > key_file
amv@LAPTOP-1MU6MBUF:~$ cat key_file
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
amv@LAPTOP-1MU6MBUF:~$ ls -la
total 235576
drwxr-xr-x 8 amv  amv       4096 May 12 19:10 .
drwxr-xr-x 3 root root      4096 Jan 29 21:08 ..
lrwxrwxrwx 1 amv  amv         23 Jan 29 21:19 .aws -> /mnt/c/Users/amv51/.aws
lrwxrwxrwx 1 amv  amv         25 Jan 29 21:19 .azure -> /mnt/c/Users/amv51/.azure
-rw------- 1 amv  amv       2614 May 12 18:52 .bash_history
-rw-r--r-- 1 amv  amv        220 Jan 29 21:08 .bash_logout
-rw-r--r-- 1 amv  amv       3771 Jan 29 21:08 .bashrc
drwx------ 3 amv  amv       4096 Apr  6 20:02 .cache
drwxr-xr-x 4 amv  amv       4096 Jan 29 21:19 .docker
drwxr-xr-x 2 amv  amv       4096 Jan 29 21:08 .landscape
drwxr-xr-x 3 amv  amv       4096 Apr  3 12:44 .local
-rw-r--r-- 1 amv  amv          0 May 12 11:17 .motd_shown
-rw-r--r-- 1 amv  amv        807 Jan 29 21:08 .profile
drwx------ 2 amv  amv       4096 Apr 15 15:03 .ssh
-rw-r--r-- 1 amv  amv          0 Apr  2 11:07 .sudo_as_admin_successful
drwxr-xr-x 6 amv  amv       4096 Apr  6 20:00 .venv
-rw-r--r-- 1 amv  amv        167 Apr  7 17:09 .wget-hsts
-rw-r--r-- 1 amv  amv  241172480 Aug  4  2023 disk.img
-rw-r--r-- 1 amv  amv        411 May 12 19:10 key_file
amv@LAPTOP-1MU6MBUF:~$ chmod 400 key_file
amv@LAPTOP-1MU6MBUF:~$ ssh -i key_file -p 53774 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:53774 ([13.59.203.175]:53774)' can't be established.
ECDSA key fingerprint is SHA256:bAr5vzQiLGB7zQsjXlfTNpzZw4qLsrE39u6WXjqMjWA.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:53774,[13.59.203.175]:53774' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

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

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt
picoCTF{k3y_5l3u7h_af277f77}

picoCTF{k3y_5l3u7h_af277f77}
```
# Notas adicionales
# Referencias