# Lab Report 1 - Remote Access and FileSystem

1. ## The *`cd`* Command
   
   - ### Analyzing the `cd` command with ***NO*** arguments
     
     - TESTING!
       
       ```
       [user@sahara ~]$ cd
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
       
2. ## The *`ls`* command
   
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
  
