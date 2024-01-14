# Lab Report 1 - Remote Access and FileSystem

<ol markdown="1">
  
  ## 1. The `cd` Command

  <ol markdown="1">
    
    ### - Analyzing the `cd` command with **NO** argument

    <ol markdown="1">
    
      ```
      [user@sahara ~]$ cd
      [user@sahara ~]$
      ```

    </ol>

  </ol>

  <ol markdown="1">

  ### - Analyzing the `cd` command with a **DIRECTORY PATH** argument

  ```
  [user@sahara ~]$ cd /home/lecture1
  [user@sahara ~/lecture1]$ 
  ```

  </ol>

  <ol markdown="1">

  ### - Analyzing the `cd` command with a **FILE PATH** argument

  ```
  [user@sahara ~]$ cd /home/lecture1/README
  bash: cd: /home/lecture1/README: Not a directory
  ```

  </ol>

  ## 2. The `ls` command

  <ol markdown="1">
    
  ### - Analyzing the `ls` command with **NO** argument
    
  ```
  [user@sahara ~]$ ls
  lecture1
  ```

  </ol>

  <ol markdown="1">

  ### - Analyzing the `ls` command with a **DIRECTORY PATH** argument

  ```
  [user@sahara ~]$ ls /home/lecture1
  Hello.class  Hello.java  messages  README
  ```

  </ol>

  <ol markdown="1">

  ### - Analyzing the `ls` command with a **FILE PATH** argument

  ```
  [user@sahara ~]$ ls /home/lecture1/README
  /home/lecture1/README
  ```

  </ol>

  ## 3. The `cat` command

  <ol markdown="1">
    
  ### - Analyzing the `cat` command with **NO** argument
    
  ```
  [user@sahara ~]$ cat
  
  ```

  </ol>

  <ol markdown="1">

  ### - Analyzing the `cat` command with a **DIRECTORY PATH** argument

  ```
  [user@sahara ~]$ cat /home/lecture1
  cat: /home/lecture1: Is a directory
  ```

  </ol>

  <ol markdown="1">

  ### - Analyzing the `cat` command with a **FILE PATH** argument

  ```
  [user@sahara ~]$ cat /home/lecture1/README
  To use this program:
  
  javac Hello.java
  java Hello messages/en-us.txt
  ```

  </ol>

</ol>
  




