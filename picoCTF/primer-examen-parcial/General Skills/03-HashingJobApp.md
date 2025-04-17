# Descripción
If you want to hash with the best, beat this test!`nc saturn.picoctf.net 51686`
Hints:
1. You can use a commandline tool or web app to hash text
2. Press Ctrl and c on your keyboard to close your connection and return to the command prompt.
# Solución
- Nos conectamos a la máquina que nos dan
- Nos pide que ingresemos un texto en md5, así que usamos una página para convertirlo
- Al ingresar nos pide lo mismo pero con otro texto, hacemos lo mismo hasta que nos de la bandera
```
┌──(kali㉿kali)-[~/hacking]
└─$ nc saturn.picoctf.net 51686     
Please md5 hash the text between quotes, excluding the quotes: 'cleaning the bathroom'
Answer: 
0c8acab58314dbcf54dbc158470a8047
0c8acab58314dbcf54dbc158470a8047
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'Count Dracula'
Answer: 
aff1b17cdcbc3b40afd42d5fe00297da
aff1b17cdcbc3b40afd42d5fe00297da
Correct.
Please md5 hash the text between quotes, excluding the quotes: 'construction workers'
Answer: 
00ae932c1c12ee89427c3efeeecf9533
00ae932c1c12ee89427c3efeeecf9533
Correct.
picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}

picoCTF{4ppl1c4710n_r3c31v3d_674c1de2}
```
# Notas adicionales
# Referencias
- https://www.md5hashgenerator.com/