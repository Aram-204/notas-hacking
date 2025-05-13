# Descripción
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/213/disk.flag.img.gz)
# Solución
- Descargamos el archivo usando wget
- Descomprimimos el archivo que descargamos 
- Si vemos el tipo de archivo usando file veremos que es un boot sector
- leeremos las particiones del archivo usando mmls
- Crearemos una carpeta en tmp y ahí montaremos las particiones del archivo
- Como tendremos que entrar al directorio root tendremos que hacer sudo su y normalmente el usuario no tiene los privilegios de entrar
- hacemos ls -alps pare ver los archivo en el root
- hacemos un cat al .ash_history
- Veremos que el usuario ha creado la bandera 
- Veremos que le metió algo y después lo encriptó
- Nosotros ya contamos con la bandera, ya que la optuvimos al hacer el cat
- Ahora ya podemos desencriptarlo con openssl
- Una vez desenciptado le haremos cat y obtendremos la bandera
```
amv@LAPTOP-1MU6MBUF:/tmp/foo$ ls
bin   dev  home  lost+found  mnt  proc  run   srv   sys  usr
boot  etc  lib   media       opt  root  sbin  swap  tmp  var
amv@LAPTOP-1MU6MBUF:/tmp/foo$ sudo su
root@LAPTOP-1MU6MBUF:/tmp/foo# cd root
root@LAPTOP-1MU6MBUF:/tmp/foo/root# ls
flag.txt.enc
root@LAPTOP-1MU6MBUF:/tmp/foo/root# ls -alps
total 4
1 drwx------  2 root root 1024 Oct  6  2021 ./
1 drwxr-xr-x 22 root root 1024 Oct  6  2021 ../
1 -rw-------  1 root root  202 Oct  6  2021 .ash_history
1 -rw-r--r--  1 root root   64 Oct  6  2021 flag.txt.enc
root@LAPTOP-1MU6MBUF:/tmp/foo/root# cat .ash_history
touch flag.txt
nano flag.txt
apk get nano
apk --help
apk add nano
nano flag.txt
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
root@LAPTOP-1MU6MBUF:/tmp/foo/root# openssl aes256 -d -in flag.txt.enc -out decrypt.txt
enter aes-256-cbc decryption password:
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
140293920052544:error:06065064:digital envelope routines:EVP_DecryptFinal_ex:bad decrypt:../crypto/evp/evp_enc.c:610:
root@LAPTOP-1MU6MBUF:/tmp/foo/root# ls
decrypt.txt  flag.txt.enc
root@LAPTOP-1MU6MBUF:/tmp/foo/root# cat decrypt.txt
picoCTF{h4un71ng_p457_5113beab}

picoCTF{h4un71ng_p457_5113beab}
```
# Notas adicionales
# Referencias