# Lab Report 1 - Remote Access and FileSystem

1. ## The *`cd`* Command
   
   - ### Analyzing the `cd` command with ***NO*** arguments
     
     - Given that the current `working directory` (checked by running `pwd`) is `/home`, the `cd` command with **NO** arguments simply outputs nothing as no change is made. To have          no arguments, the `cd` command changes the current `working directory` to its `parent directory`. The output - while it can be misleading - is indeed **not** an error because
       there is no `parent directory` to the `root directory`. 
       
       ```
       [user@sahara ~]$ cd
       [user@sahara ~]$
       ```
       
     - In this instance, the current `working directory` is `/home/lecture1` where the `messages` folder and three files (`Hello.class`, `Hello.java`, and `README`) are located at.
       By running the `cd` command with **NO** arguments in this `working directory`, it outputs the change from the `working directory` to the `parent directory` which is the `root
       directory` (or `/home`). This is **not** an error because it correctly changed the `working directory` to its `parent directory`, much like in the prior example.

       ```
       [user@sahara ~/lecture1]$ cd
       [user@sahara ~]$
       ```
 
       
   - ### Analyzing the `cd` command with a ***DIRECTORY PATH*** argument
     
     - TESTING!
       
       ```
       [user@sahara ~]$ cd /home/lecture1
       [user@sahara ~/lecture1]
       ```
       
   - ### Analyzing the `cd` command with a ***FILE PATH*** argument
     
     - TESTING!
       
       ```
       [user@sahara ~]$ cd /home/lecture1/README
       bash: cd: /home/lecture1/README: Not a directory
       ```
       
1. ## The *`ls`* command
   
   - ### Analyzing the `ls` command with ***NO*** arguments
     
     - TESTING!
       
       ```
       [user@sahara ~]$ ls
       lecture1
       ```
       
   - ### Analyzing the `ls` command with a ***DIRECTORY PATH*** argument
     
     - TESTING!
       
       ```
       [user@sahara ~]$ ls /home/lecture1
       Hello.class  Hello.java  messages  README
       ```
       
   - ### Analyzing the `ls` command with a ***FILE PATH*** argument
     
     - TESTING!
       
       ```
       [user@sahara ~]$ ls /home/lecture1/README
       /home/lecture1/README
       ```
       
5. ## The *`cat`* command
   
   - ### Analyzing the `cat` command with ***NO*** arguments
     
     - TESTING!
       
       ```
       [user@sahara ~]$ cat
       (terminal copies keyboard inputs)
       ```
       
   - ### Analyzing the `cat` command with a ***DIRECTORY PATH*** argument
     
     - TESTING!
       
       ```
       [user@sahara ~]$ cat /home/lecture1
       cat: /home/lecture1: Is a directory
       ```
   
   - ### Analyzing the `cat` command with a ***FILE PATH*** argument
     
     - TESTING!
       
       ```
       [user@sahara ~]$ cat /home/lecture1/README
       To use this program:

       javac Hello.java
       java Hello messages/en-us.txt
       ```
  
