# Descripción
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/e5825f58ef798fdd1af3f6013592a971/cat.jpg)
Hints:
1. Look at the details of the file
2. Make sure to submit the flag as picoCTF{XXXXX}
# Solución
- Obtenemos el archivo usando wget
- Veremos la información del archivo usando exiftool
- Veremos que hay una licencia que para estar escrito en base64
- Le haremos un grep a license, extraeremos el texto en base64 y lo convertiremos a texto normal
- Ahí encontraremos la bandera
```
amv@LAPTOP-1MU6MBUF:~$ exiftool cat.jpg
ExifTool Version Number         : 11.88
File Name                       : cat.jpg
Directory                       : .
File Size                       : 858 kB
File Modification Date/Time     : 2021:03:15 12:24:46-06:00
File Access Date/Time           : 2025:05:12 19:23:27-06:00
File Inode Change Date/Time     : 2025:05:12 19:23:27-06:00
File Permissions                : rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
amv@LAPTOP-1MU6MBUF:~$ exiftool cat.jpg | grep License | sed -e 's/.*: //' | base64 -d
picoCTF{the_m3tadata_1s_modified}

picoCTF{the_m3tadata_1s_modified}
```
# Notas adicionales
# Referencias