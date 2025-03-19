# Descripción
How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 54454`
# Solución
```
amv204-picoctf@webshell:~$ nc titan.picoctf.net 54454

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 11110010
Binary Number 2: 11011100


Question 1/6:
Operation 1: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 000111001110
Correct!

Question 2/6:
Operation 2: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 1 1110 0100

Incorrect input. Provide the right input
Enter the binary result: 1 1110 010^Z       
[1]+  Stopped                 nc titan.picoctf.net 54454
amv204-picoctf@webshell:~$ nc titan.picoctf.net 54454

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 11111100
Binary Number 2: 11010001


Question 1/6:
Operation 1: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11010000
Correct!

Question 2/6:
Operation 2: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 111111000
Correct!

Question 3/6:
Operation 3: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 1100110110111100
Correct!

Question 4/6:
Operation 4: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 1101000
Correct!

Question 5/6:
Operation 5: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 11111101
Correct!

Question 6/6:
Operation 6: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 111001101
Correct!

Enter the results of the last operation in hexadecimal: 1CD

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_d9a7ddd2}

picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_d9a7ddd2}
```
# Notas adicionales
- Usamos la calculadora de windows para realizar las operaciones con los números binarios, también para convertir de binario a hexadecimal
# Referencias