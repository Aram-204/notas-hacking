# Descripción
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/137/disk.flag.img.gz)
# Solución
- Descargamos la imagen y la descomprimimos
- Si intentamos buscar la bandera con srch_strings nos daremos cuenta de que no nos la dará
- Usamos mmls para ver las particiones
- usamos fls "nombre" -o partición
- Nos dará el nombre de un archivo, así que buscamos el archivo flag
- Ahora usamos icat para desplegar el contenido y obtendremos la bandera
```
amv@LAPTOP-1MU6MBUF:~$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)
amv@LAPTOP-1MU6MBUF:~$ fls disk.flag.img -o 360448
d/d 11: lost+found
d/d 12: boot
d/d 1985:       etc
d/d 1986:       proc
d/d 1987:       dev
d/d 1988:       tmp
d/d 1989:       lib
d/d 1990:       var
d/d 3969:       usr
d/d 3970:       bin
d/d 1991:       sbin
d/d 451:        home
d/d 1992:       media
d/d 1993:       mnt
d/d 1994:       opt
d/d 1995:       root
d/d 1996:       run
d/d 1997:       srv
d/d 1998:       sys
d/d 2358:       swap
V/V 31745:      $OrphanFiles
amv@LAPTOP-1MU6MBUF:~$ fls disk.flag.img -o 360448 1995
r/r 2363:       .ash_history
d/d 3981:       my_folder
amv@LAPTOP-1MU6MBUF:~$ fls disk.flag.img -o 360448 3981
r/r * 2082(realloc):    flag.txt
r/r 2371:       flag.uni.txt
amv@LAPTOP-1MU6MBUF:~$ icat disk.flag.img -o 360448 2371
picoCTF{by73_5urf3r_adac6cb4}

picoCTF{by73_5urf3r_adac6cb4}
```
# Notas adicionales
# Referencias