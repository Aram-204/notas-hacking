# Descripción
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.
Hints:
1. Does that encoding look familiar?
2. The `str_xor` function does not need to be reverse engineered for this challenge.
# Solución
```
  GNU nano 6.2                                                                                                     level2.py                                                                                                               
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x34) + chr(0x65) + chr(0x63) + chr(0x39) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_2_pw_check()
```

```
amv204-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/14/level2.py
--2025-03-16 19:02:22--  https://artifacts.picoctf.net/c/14/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.92, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                                                  100%[=======================================================================================================================================>]     914  --.-KB/s    in 0s      

2025-03-16 19:02:22 (279 MB/s) - 'level2.py' saved [914/914]

amv204-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
--2025-03-16 19:02:37--  https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.16, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc                                        100%[=======================================================================================================================================>]      31  --.-KB/s    in 0s      

2025-03-16 19:02:37 (2.47 MB/s) - 'level2.flag.txt.enc' saved [31/31]

amv204-picoctf@webshell:~$ python3 level2.py
Please enter correct password for flag: flag
That password is incorrect
amv204-picoctf@webshell:~$ nano level2.py
amv204-picoctf@webshell:~$ python3 level2.py
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}

picoCTF{tr45h_51ng1ng_9701e681}
```
# Notas adicionales
- El ejercicio se resuelve igual que el PW Crack 1, la diferencia es que para obtener la bandera debemos de obtener el código que se encuentra en hexadecimal, para convertir el código de hexadecimal a decimal utilizamos cyberchef con los siguiente:

Input: 0x34 0x65 0x63 0x39
Receipe: From Hex
Output: 4ec9
# Referencias
- https://webshell.picoctf.org/
- https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHgzNCAweDY1IDB4NjMgMHgzOQ