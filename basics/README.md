# Shell, basics

 - What is the **shell** ?
 - What is the difference between a **terminal** and a **shell** ?
 - What is a **shell prompt** ?
 - How to use the **history** ?

## Objective

This project is dedicated to understand and learn the **shell**. The idea is to **create files** using the shell and manage to **write and test some little scripts**.

### Commands I used

>- cd
>- ls
>- pwd
>- less
>- file
>- ln
>- cp
>- mv
>- rm
>- mkdir
>- type
>- man
>>- ls -l
>>- ls -a
>> - cp -u
>>- rm -f
>- #!
 
## Requirements

- Allowed editors: `vi`, `vim`, `emacs`
- All your scripts will be tested on Ubuntu 20.04 LTS
- All your scripts should be exactly two lines long (`$ wc -l file` should print 2)
- All your files should end with a new line (why?)
- The first line of all your files should be exactly `#!/bin/bash`
- A `README.md` file at the root of the repo, containing a description of the repository
- A `README.md` file, at the root of the folder of this project, describing what each script is doing
- You are not allowed to use backticks, `&&`, `||` or `;`
- All your scripts must be executable. To make your file executable, use the ==chmod== command: ==chmod u+x file==. Later, we’ll learn more about how to utilize this command. 

## Tasks

<details>
<summary>0.Where am I ?</summary>
<p>Write a script that prints the absolute path name of the current working directory.

Example :
```
$ ./0-current_working_directory
/basics
$
```
</p>
</details>

<details>
  <summary>1. What’s in there?</summary>
  <p>Display the contents list of your current directory.

Example:
```
$ ./1-listit
Applications    Documents   Dropbox Movies Pictures
Desktop Downloads   Library Music Public
$
```    
  </p>
</details>

<details>
  <summary>2. There is no place like home</summary>
  <p>Write a script that changes the working directory to the user’s home directory.

- You are not allowed to use any shell variables
```
julien@ubuntu:/tmp$ pwd
/tmp
julien@ubuntu:/tmp$ echo $HOME
/home/julien
julien@ubuntu:/tmp$ source ./2-bring_me_home
julien@ubuntu:~$ pwd
/home/julien
julien@ubuntu:~$ 
```    
  </p>
</details>

<details>
<summary>3. The long format</summary>
<p> Display current directory contents in a long format

Example:
```
$ ./3-listfiles
total 40
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 sylvain staff 19 Jan 25 00:23 1-listit
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:39 3-listfiles
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:20 README.md
```    
  </p>
</details>

<details>
  <summary>4. Hidden files</summary>
  <p>Display current directory contents, including hidden files (starting with .). Use the long format.

Example:
```
$ ./4-listmorefiles
total 48
drwxr-xr-x@ 6 sylvain staff 204 Jan 25 00:29 .
drwxr-xr-x@ 43 sylvain staff 1462 Jan 25 00:19 ..
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 sylvain staff 19 Jan 25 00:23 1-listit
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:39 3-listfiles
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:41 4-listmorefiles
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:20 README.md
$
```    
  </p>
</details>

<details>
  <summary>5. I love numbers</summary>
  <p>Display current directory contents.

Long format
with user and group IDs displayed numerically
And hidden files (starting with .)
Example:
```
$ ./5-listfilesdigitonly
total 56
drwxr-xr-x@ 6 501 20 204 Jan 25 00:29 .
drwxr-xr-x@ 43 501 20 1462 Jan 25 00:19 ..
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:23 1-listfiles
-rwxr-xr-x@ 1 501 20 19 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 501 20 20 Jan 25 00:39 3-listfiles
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:41 4-listmorefiles
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:43 5-listfilesdigitonly
-rwxr-xr-x@ 1 501 20 18 Jan 25 00:20 README.md
$
```    
  </p>
</details>

<details>
  <summary>6. Welcome</summary>
  <p>Create a script that creates a directory named my_first_directory in the /tmp/ directory.

Example:
```
$ ./6-firstdirectory
$ file /tmp/my_first_directory/
/tmp/my_first_directory/: directory
$
```    
  </p>
</details>

<details>
  <summary>7. Betty in my first directory</summary>
  <p>Move the file betty from /tmp/ to /tmp/my_first_directory.

Example:
```
$ ./7-movethatfile
$ ls /tmp/my_first_directory/
betty
$
```    
  </p>
</details>

<details>
  <summary>8. Bye bye Betty</summary>
  <p>Delete the file betty.

The file betty is in /tmp/my_first_directory
Example:
```
$ ./8-firstdelete
$ ls /tmp/my_first_directory/
$
```    
  </p>
</details>

<details>
  <summary>9. Bye bye My first directory</summary>
  <p>Delete the directory my_first_directory that is in the /tmp directory.

Example:
```
$ ./9-firstdirdeletion
$ file /tmp/my_first_directory
/tmp/my_first_directory: cannot open `/tmp/my_first_directory' (No such file or directory)
$
```    
  </p>
</details>

<details>
  <summary>10. Back to the future</summary>
  <p>Write a script that changes the working directory to the previous one.
```
julien@ubuntu:/tmp$ pwd
/tmp
julien@ubuntu:/tmp$ cd /var
julien@ubuntu:/var$ pwd
/var
julien@ubuntu:/var$ source ./10-back
/tmp
julien@ubuntu:/tmp$ pwd
/tmp
```    
  </p>
</details>

<details>
  <summary>11. Lists</summary>
  <p>Write a script that lists all files (even ones with names beginning with a period character, which are normally hidden) in the current directory and the parent of the working directory and the `/boot` directory (in this order), in long format.

Be careful with the `/`
    
  </p>
</details>

<details>
  <summary>12. File type</summary>
  <p>Write a script that prints the type of the file named `iamafile`. The file `iamafile` will be in the `/tmp` directory when we will run your script.

Example
```
ubuntu@ip-172-31-63-244:~$ ./12-file_type
/tmp/iamafile: ELF 64-bit LSB  executable, x86-64, version 1 (SYSV), dynamically linked (uses shared libs), for GNU/Linux 2.6.24, BuildID[sha1]=bd39c07194a778ccc066fc963ca152bdfaa3f971, stripped
```
Note that depending on the file, the output of your script will be different.
    
  </p>
</details>

<details>
  <summary>13. We are symbols, and inhabit symbols</summary>
  <p>Create a symbolic link to `/bin/ls`, named `__ls__`. The symbolic link should be created in the current working directory.
```
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 144
drwxrwxr-x  2 ubuntu ubuntu   4096 Sep 20 03:24 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:24 ..
ubuntu@ip-172-31-63-244:/tmp/sym$./13-symbolic_link
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 144
drwxrwxr-x  2 ubuntu ubuntu   4096 Sep 20 03:24 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:24 ..
lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
```    
  </p>
</details>

<details>
  <summary>14. Copy HTML files</summary>
  <p>Create a script that copies all the HTML files from the current working directory to the parent of the working directory, but only copy files that did not exist in the parent of the working directory or were newer than the versions in the parent of the working directory.

You can consider that all HTML files have the extension `.html`
    
  </p>
</details>

<details>
  <summary>15. Let's move</summary>
  <p>Create a script that moves all files beginning with an uppercase letter to the directory `/tmp/u`.

You can assume that the directory `/tmp/u` will exist when we will run your script
```
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 148
drwxrwxr-x  3 ubuntu ubuntu   4096 Sep 20 03:33 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:26 ..
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 My_file
lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 Elif_ym
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 random_file
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la /tmp/u
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Sep 20 03:33 .
drwxrwxr-x 3 ubuntu ubuntu 4096 Sep 20 03:33 ..
ubuntu@ip-172-31-63-244:/tmp/sym$ ./15-lets_move
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la
total 148
drwxrwxr-x  3 ubuntu ubuntu   4096 Sep 20 03:33 .
drwxrwxrwt 12 root   root   139264 Sep 20 03:26 ..
lrwxrwxrwx  1 ubuntu ubuntu      7 Sep 20 03:24 __ls__ -> /bin/ls
-rw-rw-r--  1 ubuntu ubuntu      0 Sep 20 03:32 random_file
ubuntu@ip-172-31-63-244:/tmp/sym$ ls -la /tmp/u
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Sep 20 03:33 .
drwxrwxr-x 3 ubuntu ubuntu 4096 Sep 20 03:33 ..
-rw-rw-r-- 1 ubuntu ubuntu    0 Sep 20 03:32 My_file
-rw-rw-r-- 1 ubuntu ubuntu    0 Sep 20 03:32 Elif_ym
```    
  </p>
</details>

<details>
  <summary>16. Clean Emacs</summary>
  <p>Create a script that deletes all files in the current working directory that end with the character `~`.
```
ubuntu@ip-172-31-63-244:/tmp/sym$ ls
main.c  main.c~  Makefile~
ubuntu@ip-172-31-63-244:/tmp/sym$ ./16-clean_emacs
ubuntu@ip-172-31-63-244:/tmp/emacs$ ls
main.c
ubuntu@ip-172-31-63-244:/tmp/emacs$
```    
  </p>
</details>

<details>
  <summary>17. Tree</summary>
  <p>Create a script that creates the directories `welcome/`, `welcome/to/` and `welcome/to/school` in the current directory.

You are only allowed to use two spaces (and lines) in your script, not more.
```
julien@ubuntu:/tmp/h$ ls -l
total 4
-rwxrw-r-- 1 julien julien 44 Sep 20 12:09 17-tree
julien@ubuntu:/tmp/h$ wc -l 17-tree 
2 17-tree
julien@ubuntu:/tmp/h$ head -1 17-tree 
#!/bin/bash
julien@ubuntu:/tmp/h$ tr -cd ' ' < 17-tree | wc -c # you do not have to understand this yet, but the result should be 2, 1 or 0
2
julien@ubuntu:/tmp/h$ ./17-tree 
julien@ubuntu:/tmp/h$ ls
17-tree  welcome
julien@ubuntu:/tmp/h$ ls welcome/
to
julien@ubuntu:/tmp/h$ ls -l welcome/to
total 4
drwxrwxr-x 2 julien julien 4096 Sep 20 12:11 school
julien@ubuntu:/tmp/h$ 
```    
  </p>
</details>
