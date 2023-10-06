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

$ ./1-listit
Applications    Documents   Dropbox Movies Pictures
Desktop Downloads   Library Music Public
$
    
  </p>
</details>

<details>
  <summary>2. There is no place like home</summary>
  <p>Write a script that changes the working directory to the user’s home directory.

You are not allowed to use any shell variables
julien@ubuntu:/tmp$ pwd
/tmp
julien@ubuntu:/tmp$ echo $HOME
/home/julien
julien@ubuntu:/tmp$ source ./2-bring_me_home
julien@ubuntu:~$ pwd
/home/julien
julien@ubuntu:~$ 
    
  </p>
</details>

<details>
  <summary>3. The long format</summary>
  <p>Display current directory contents in a long format

Example:

$ ./3-listfiles
total 40
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:19 0-current_working_directory
-rwxr-xr-x@ 1 sylvain staff 19 Jan 25 00:23 1-listit
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:29 2-bring_me_home
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:39 3-listfiles
-rwxr-xr-x@ 1 sylvain staff 18 Jan 25 00:20 README.md
    
  </p>
</details>

<details>
  <summary>4. Hidden files</summary>
  <p>Display current directory contents, including hidden files (starting with .). Use the long format.

Example:

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
    
  </p>
</details>

<details>
  <summary>5. I love numbers</summary>
  <p>Display current directory contents.

Long format
with user and group IDs displayed numerically
And hidden files (starting with .)
Example:

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
    
  </p>
</details>

<details>
  <summary>6. Welcome</summary>
  <p>Create a script that creates a directory named my_first_directory in the /tmp/ directory.

Example:

$ ./6-firstdirectory
$ file /tmp/my_first_directory/
/tmp/my_first_directory/: directory
$
    
  </p>
</details>

<details>
  <summary>7. Betty in my first directory</summary>
  <p>Move the file betty from /tmp/ to /tmp/my_first_directory.

Example:

$ ./7-movethatfile
$ ls /tmp/my_first_directory/
betty
$
    
  </p>
</details>

<details>
  <summary>8. Bye bye Betty</summary>
  <p>Delete the file betty.

The file betty is in /tmp/my_first_directory
Example:

$ ./8-firstdelete
$ ls /tmp/my_first_directory/
$
    
  </p>
</details>

<details>
  <summary>9. Bye bye My first directory</summary>
  <p>Delete the directory my_first_directory that is in the /tmp directory.

Example:

$ ./9-firstdirdeletion
$ file /tmp/my_first_directory
/tmp/my_first_directory: cannot open `/tmp/my_first_directory' (No such file or directory)
$
    
  </p>
</details>

<details>
  <summary>10. Back to the future</summary>
  <p>Write a script that changes the working directory to the previous one.

julien@ubuntu:/tmp$ pwd
/tmp
julien@ubuntu:/tmp$ cd /var
julien@ubuntu:/var$ pwd
/var
julien@ubuntu:/var$ source ./10-back
/tmp
julien@ubuntu:/tmp$ pwd
/tmp
    
  </p>
</details>

<details>
  <summary>11. Lists</summary>
  <p>Write a script that lists all files (even ones with names beginning with a period character, which are normally hidden) in the current directory and the parent of the working directory and the /boot directory (in this order), in long format.

Be careful with the /
    
  </p>
</details>

<details>
  <summary>12. File type</summary>
  <p>
    
  </p>
</details>

<details>
  <summary>13. We are symbols, and inhabit symbols</summary>
  <p>Create a symbolic link to /bin/ls, named __ls__. The symbolic link should be created in the current working directory.

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
    
  </p>
</details>

<details>
  <summary></summary>
  <p>
    
  </p>
</details>

<details>
  <summary></summary>
  <p>
    
  </p>
</details>

<details>
  <summary></summary>
  <p>
    
  </p>
</details>

<details>
  <summary></summary>
  <p>
    
  </p>
</details>

<details>
  <summary></summary>
  <p>
    
  </p>
</details>

<details>
  <summary></summary>
  <p>
    
  </p>
</details>

