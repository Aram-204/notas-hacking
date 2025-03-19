# Descripción
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/178/challenge.zip)
Hints:
1. `git branch -a` will let you see available branches
2. How can file 'diffs' be brought to the main branch? Don't forget to `git config`!
3. Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.
# Solución
```
amv204-picoctf@webshell:~$ cd drop-in 
amv204-picoctf@webshell:~/drop-in$ git log | grep picoCTF
Author: picoCTF <ops@picoctf.com>
amv204-picoctf@webshell:~/drop-in$ git log | grep picoCTF{
amv204-picoctf@webshell:~/drop-in$ ls
flag.py
amv204-picoctf@webshell:~/drop-in$ git branch -a                  
amv204-picoctf@webshell:~/drop-in$ git checkout feature/part-1 --f
Switched to branch 'feature/part-1'
amv204-picoctf@webshell:~/drop-in$ git branch -a
amv204-picoctf@webshell:~/drop-in$ nano flag.py 
amv204-picoctf@webshell:~/drop-in$ git checkout feature/part-2 --f
Switched to branch 'feature/part-2'
amv204-picoctf@webshell:~/drop-in$ nano flag.py
amv204-picoctf@webshell:~/drop-in$ git checkout feature/part-3 --f
Switched to branch 'feature/part-3'
amv204-picoctf@webshell:~/drop-in$ nano flag.py
amv204-picoctf@webshell:~/drop-in$ 

picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_6c06cec1}
```
# Notas adicionales
- Entramos a cada rama para ver cada parte de la bandera y la unimos por nuestra cuenta
# Referencias