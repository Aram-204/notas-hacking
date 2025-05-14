# Descripción
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_atlas/19/challenge.zip)

`ssh -p 59879 ctf-player@atlas.picoctf.net`Using the password `1db87a14`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!
Hints:
1. Have you ever played hot or cold? Binary search is a bit like that.
2. You have a very limited number of guesses. Try larger jumps between numbers!
3. The program will randomly choose a new number each time you connect. You can always try again, but you should start your binary search over from the beginning - try around 500. Can you think of why?
# Solución
```
amv204-picoctf@webshell:~$ ssh -p 59879 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:59879 ([18.217.83.136]:59879)' can't be established.
ED25519 key fingerprint is SHA256:M8hXanE8l/Yzfs8iuxNsuFL4vCzCKEIlM/3hpO13tfQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:59879' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Higher! Try again.
Enter your guess: 750
Higher! Try again.
Enter your guess: 900
Lower! Try again.
Enter your guess: 800
Lower! Try again.
Enter your guess: 780
Higher! Try again.
Enter your guess: 790
Higher! Try again.
Enter your guess: 797
Lower! Try again.
Enter your guess: 795
Lower! Try again.
Enter your guess: 793
Lower! Try again.
Enter your guess: 792
Lower! Try again.
Sorry, you've exceeded the maximum number of guesses.
Connection to atlas.picoctf.net closed.
amv204-picoctf@webshell:~$ ssh -p 59879 ctf-player@atlas.picoctf.net
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Lower! Try again.
Enter your guess: 250
Higher! Try again.
Enter your guess: 325
Lower! Try again.
Enter your guess: 275
Higher! Try again.
Enter your guess: 290
Higher! Try again.
Enter your guess: 310
Lower! Try again.
Enter your guess: 305
Lower! Try again.
Enter your guess: 302
Lower! Try again.
Enter your guess: 297
Congratulations! You guessed the correct number: 297
Here's your flag: picoCTF{g00d_gu355_1597707f}
Connection to atlas.picoctf.net closed.

picoCTF{g00d_gu355_1597707f}
```
# Notas adicionales
- Le tenemos que atinar al número y nos da la bandera
# Referencias
