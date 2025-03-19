# Descripción
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/77/challenge.zip)
Hints:
1. Version control can help you recover files if you change or lose them!
2. Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control)Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control)
3. You can 'checkout' commits to see the files inside them
# Solución
```
amv204-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c_titan/77/challenge.zip
--2025-03-19 02:17:49--  https://artifacts.picoctf.net/c_titan/77/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19199 (19K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                                              100%[=======================================================================================================================================>]  18.75K  --.-KB/s    in 0.005s  

2025-03-19 02:17:49 (3.40 MB/s) - 'challenge.zip' saved [19199/19199]

amv204-picoctf@webshell:~$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/96/
 extracting: drop-in/.git/objects/96/f7309de67d785ec0b93b8766ff2882bef5c3ef  
   creating: drop-in/.git/objects/8c/
 extracting: drop-in/.git/objects/8c/1d254e2da6713e33acd6d622fc1dae357ec3c6  
   creating: drop-in/.git/objects/3d/
 extracting: drop-in/.git/objects/3d/5ec8a26ee7b092a1760fea18f384c35e435139  
   creating: drop-in/.git/objects/d5/
 extracting: drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7  
   creating: drop-in/.git/objects/0c/
 extracting: drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03  
   creating: drop-in/.git/objects/e1/
 extracting: drop-in/.git/objects/e1/237df82d2e69f62dd53279abc1c8aeb66f6d64  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
 extracting: drop-in/message.txt     
amv204-picoctf@webshell:~$ cat message.txt
cat: message.txt: No such file or directory
amv204-picoctf@webshell:~$ git log
fatal: not a git repository (or any parent up to mount point /)
Stopping at filesystem boundary (GIT_DISCOVERY_ACROSS_FILESYSTEM not set).
amv204-picoctf@webshell:~$ ls
README.txt  challenge.zip  drop-in
amv204-picoctf@webshell:~$ cd drop-in
amv204-picoctf@webshell:~/drop-in$ git log

amv204-picoctf@webshell:~/drop-in$ git checkout 87b85d7dfb839b077678611280fa023d76e017b8
fatal: reference is not a tree: 87b85d7dfb839b077678611280fa023d76e017b8
amv204-picoctf@webshell:~/drop-in$ git log
amv204-picoctf@webshell:~/drop-in$ git checkout e1237df82d2e69f62dd53279abc1c8aeb66f6d64
Note: switching to 'e1237df82d2e69f62dd53279abc1c8aeb66f6d64'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at e1237df remove sensitive info
amv204-picoctf@webshell:~/drop-in$ cat message.txt
TOP SECRET
amv204-picoctf@webshell:~/drop-in$ git log
amv204-picoctf@webshell:~/drop-in$ git checkout 3d5ec8a26ee7b092a1760fea18f384c35e435139
Previous HEAD position was e1237df remove sensitive info
HEAD is now at 3d5ec8a create flag
amv204-picoctf@webshell:~/drop-in$ cat message.txt
picoCTF{s@n1t1z3_30e86d36}
amv204-picoctf@webshell:~/drop-in$ 
```
# Notas adicionales
# Referencias