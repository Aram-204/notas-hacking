# Descripción
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/160/challenge.zip)
Hints:
1. The `cat` command will let you read a file, but that won't help you here!
2. Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).
3. When committing a file with git, a message can (and should) be included.
# Solución
```
amv204-picoctf@webshell:~$ ls
README.txt  challenge.zip  drop-in
amv204-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/160/challenge.zip
--2025-03-19 02:53:21--  https://artifacts.picoctf.net/c_titan/160/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.16, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17740 (17K) [application/octet-stream]
Saving to: 'challenge.zip.1'

challenge.zip.1                                            100%[=======================================================================================================================================>]  17.32K  --.-KB/s    in 0.006s  

2025-03-19 02:53:21 (2.90 MB/s) - 'challenge.zip.1' saved [17740/17740]

amv204-picoctf@webshell:~$ unzip^C
amv204-picoctf@webshell:~$ unzip challenge.zip.1
Archive:  challenge.zip.1
replace drop-in/message.txt? [y]es, [n]o, [A]ll, [N]one, [r]ename: y  
  inflating: drop-in/message.txt     
replace drop-in/.git/description? [y]es, [n]o, [A]ll, [N]one, [r]ename: y
  inflating: drop-in/.git/description  
replace drop-in/.git/hooks/applypatch-msg.sample? [y]es, [n]o, [A]ll, [N]one, [r]ename: y
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
replace drop-in/.git/hooks/commit-msg.sample? [y]es, [n]o, [A]ll, [N]one, [r]ename: y
  inflating: drop-in/.git/hooks/commit-msg.sample  
replace drop-in/.git/hooks/fsmonitor-watchman.sample? [y]es, [n]o, [A]ll, [N]one, [r]ename: y
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
replace drop-in/.git/hooks/post-update.sample? [y]es, [n]o, [A]ll, [N]one, [r]ename: A
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
  inflating: drop-in/.git/info/exclude  
 extracting: drop-in/.git/refs/heads/master  
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
 extracting: drop-in/.git/objects/89/d296ef533525a1378529be66b22d6a2c01e530  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
  inflating: drop-in/.git/logs/HEAD  
  inflating: drop-in/.git/logs/refs/heads/master  
amv204-picoctf@webshell:~$ git log
fatal: not a git repository (or any parent up to mount point /)
Stopping at filesystem boundary (GIT_DISCOVERY_ACROSS_FILESYSTEM not set).
amv204-picoctf@webshell:~$ cd drop-in
amv204-picoctf@webshell:~/drop-in$ git log
amv204-picoctf@webshell:~/drop-in$ 

picoCTF{t1m3m@ch1n3_186cd7d7}
```
# Notas adicionales
# Referencias