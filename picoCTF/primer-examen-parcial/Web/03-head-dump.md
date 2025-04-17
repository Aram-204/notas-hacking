# Descripción
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.The website is running [picoCTF News](http://verbal-sleep.picoctf.net:62048/).
Hints:
1. Explore backend development with us
2. The head was dumped.
# Solución
- Entramos a la página
- Entramos a la documentación de la API
- Buscaremos en los diferentes endpoints hasta encontrar uno que genera archivos y los alamacena
- Por el nombre del reto asumimos que es heapdump
- Lo probamos, lo ejecutamos y nos dará el link para un archivo que se genera
- Lo descargamos usando el comando que nos da junto a una extensión para que se guarde
- Le hacemos un cat junto a un grep y obtenendremos la bandera
```
amv@LAPTOP-1MU6MBUF:~$ curl -X 'GET' \
p' \
  -H 'accept: */*'>   'http://verbal-sleep.picoctf.net:62048/heapdump' \
>   -H 'accept: */*' > heapdump
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--    0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--    0     0    0     0    0     0      0      0 --:--:--  0:00:01 --:--:--    0     0    0     0    0     0      0      0 --:--:--  0:00:02 --:--:--    1 8732k    1   99k    0     0  32013      0  0:04:39  0:00:03  0:04:36 3 12 8732k   12 1086k    0     0   261k      0  0:00:33  0:00:04  0:00:29   26 8732k   26 2272k    0     0   440k      0  0:00:19  0:00:05  0:00:14   40 8732k   40 3565k    0     0   578k      0  0:00:15  0:00:06  0:00:09   54 8732k   54 4747k    0     0   662k      0  0:00:13  0:00:07  0:00:06   67 8732k   67 5896k    0     0   722k      0  0:00:12  0:00:08  0:00:04 1 82 8732k   82 7188k    0     0   784k      0  0:00:11  0:00:09  0:00:02 1 97 8732k   97 8497k    0     0   824k      0  0:00:10  0:00:10 --:--:-- 1100 8732k  100 8732k    0     0   837k      0  0:00:10  0:00:10 --:--:-- 1212k
amv@LAPTOP-1MU6MBUF:~$ cat heapdump | grep picoCTF{
picoCTF{Pat!3nt_15_Th3_K3y_388d10f7}


picoCTF{Pat!3nt_15_Th3_K3y_388d10f7}
```
# Notas adicionales
- Se puede descargar el archivo directamente desde el navegador
# Referencias