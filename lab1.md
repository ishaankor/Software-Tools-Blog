# Lab Report 1 - Remote Access and FileSystem

1. ## The *`cd`* Command
   
   - ### Analyzing the `cd` command with ***NO*** arguments
     
     - Given that the current `working directory` (checked by running `pwd`) is `/home`, the `cd` command with **NO** arguments simply outputs no changes in the `working directory`. To have no arguments, the `cd` command              changes the current `working directory` to its `parent directory`. The output - while it can be misleading - is indeed **not** an error because there is no `parent directory` to the `root directory`. 
       
       ```
       [user@sahara ~]$ cd
       [user@sahara ~]$
       ```
       
     - In this instance, the current `working directory` is `/home/lecture1` where the `messages` folder and three files (`Hello.class`, `Hello.java`, and `README`) are located at. By running the `cd` command with **NO**              arguments in this `working directory`, it outputs the change from the `working directory` to the `parent directory` which is the `root directory` (or `/home`). This is **not** an error because it correctly changed the          `working directory` to its `parent directory`, much like in the prior example.

       ```
       [user@sahara ~/lecture1]$ cd
       [user@sahara ~]$
       ```
 
       
   - ### Analyzing the `cd` command with a ***DIRECTORY PATH*** argument
     
     - When providing a `directory path` argument to the `cd` command, the terminal changes the current `working directory` to the given argument (if it exists). At the `root directory`, the `cd` command with the argument             (`/home/lecture1`) outputs the change in `working directory` by moving from the `root directory` to `/home/lecture1`. As a result, this output is **not** an error. 
       
       ```
       [user@sahara ~]$ cd /home/lecture1
       [user@sahara ~/lecture1]
       ```
       
   - ### Analyzing the `cd` command with a ***FILE PATH*** argument
     
     - However, using the `cd` command with the argument (`/home/lecture1/README`) in the `root directory` will **raise** an error due to the nature of the command - it only works by changing the current *`working directory`*,        not `file(s)`. A `file path` lists the path to a specific file while a `directory path` lists the path to a specific directory. The terminal **cannot** change its `working directory path` to that of a `file path`, as           shown in the code below where `lecture1`'s `README` was not recognized as a `directory`. 
       
       ```
       [user@sahara ~]$ cd /home/lecture1/README
       bash: cd: /home/lecture1/README: Not a directory
       ```
       
1. ## The *`ls`* command
   
   - ### Analyzing the `ls` command with ***NO*** arguments
     
     - Much like the previous test cases, the current `working directory` was in the `root directory`. This filesystem has `lecture1`, a directory that is compromised of other files (`Hello.class`, `Hello.java`, and `README`)         and a folder (`messages`). Just by running the `ls` command with **no** arguments, the terminal should list out the entries of of the current `working directory`. The terminal, in this case, outputted `lecture1` as it          was a `subdirectory` in the `root directory` and is therefore **not** an error.

       ```
       [user@sahara ~]$ ls
       lecture1
       ```
       
   - ### Analyzing the `ls` command with a ***DIRECTORY PATH*** argument
     
     - With the argument (`/home/lecture1`), the `ls` command lists the `'messages' directory` and the three `files` that are present within the argument. It is important to note unlike the `cd` command, the `ls` command seems        to ignore the current `working directory` (`root directory`) as it only looks for an argument (if provided) to parse through and list its entries. Nonetheless, the terminal correctly outputs the entries of the                  given `directory` (`lecture1`) and is **not** an error.
       
       ```
       [user@sahara ~]$ ls /home/lecture1
       Hello.class  Hello.java  messages  README
       ```
       
   - ### Analyzing the `ls` command with a ***FILE PATH*** argument
     
     - If a `file path` was the given argument for the `ls` command, the terminal should print out the given argument as there is no further entries to be displayed. By putting the `/home/lecture1/README` as the                       argument, the terminal prints out the `file path` regardless of the current `working directory` (in this case, it was the `root directory`). This makes sense as there are no entries within that file and is why                  `directories` are the best arguments for this command - the output is **not** an error.
       
       ```
       [user@sahara ~]$ ls /home/lecture1/README
       /home/lecture1/README
       ```
       
5. ## The *`cat`* command
   
   - ### Analyzing the `cat` command with ***NO*** arguments
     
     -  Starting at the `root directory`, the `cat` command with **no** arguments outputs keyboard input as there are no files within the filesystem - just the `lecture1 directory`.  Similarly to the `ls` command, the `cat`            command relies on the argument as it provides the necessary `file path` to print its content. From first glance, this seems like an error when it really is **not**. The terminal is defaulting to reading the standard         input as there are **no** arguments.

        ```
        [user@sahara ~]$ cat
        (terminal copies keyboard inputs)
        ```
       
   - ### Analyzing the `cat` command with a ***DIRECTORY PATH*** argument
     
     - Trying the `cat` command with the argument (`/home/lecture1`) will **raise** an error - for a good reason. Because the `cat` command wants to read the content of a specific `file`, this command (if it worked) would effectively copy what the `ls` command does. The `/home/lecture1` argument has no specific file to read its contents - that's the point of the `cat` command.
       
       ```
       [user@sahara ~]$ cat /home/lecture1
       cat: /home/lecture1: Is a directory
       ```
   
   - ### Analyzing the `cat` command with a ***FILE PATH*** argument
     
     - Having a `file path` argument for the `cat` command should allow the terminal to output the specified `file's` content. The `cat` command is similar to the `ls` command where the current `filesystem` (`root directory`) is not used in the command and rather looks for a `file path` to read from. Using `/home/lecture1/README` as the `file path` argument, the terminal successfully prints out what is inside `README` - this is why the output is **not** an error. 
       
       ```
       [user@sahara ~]$ cat /home/lecture1/README
       To use this program:

       javac Hello.java
       java Hello messages/en-us.txt
       ```
  
