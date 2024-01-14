# Lab Report 1 - Remote Access and FileSystem

<ol markdown="1">
  
  ## 1. The `cd` Command

  <ol markdown="1">
    
  ### - Analyzing the `cd` command with **NO** argument
  
  ```
  [user@sahara ~]$ cd
  [user@sahara ~]$
  ```

  </ol>

  ### - Analyzing the `cd` command with a **DIRECTORY PATH** argument

  <ol markdown="1">

  ```
  [user@sahara ~]$ cd /home/lecture1
  [user@sahara ~/lecture1]$ 
  ```

  </ol>

  ### - Analyzing the `cd` command with a **FILE PATH** argument

  <ol markdown="1">

  ```
  [user@sahara ~]$ cd /home/lecture1/README
  bash: cd: /home/lecture1/README: Not a directory
  ```

  </ol>

  ## 2. The `ls` command

</ol>
  


> ## 2. The `ls` command


### - Analyzing the `ls` command with **NO** argument 

```
[user@sahara ~]$ ls
lecture1
```

### - Analyzing the `ls` command with a **DIRECTORY PATH** argument

```
[user@sahara ~]$ ls /home/lecture1
Hello.class  Hello.java  messages  README
```

###  - Analyzing the `ls` command with a **FILE PATH** argument

```
[user@sahara ~]$ ls /home/lecture1/README
/home/lecture1/README
```

## 3. The `cat` command

### - Analyzing the `cat` command with **NO** argument

```
[user@sahara ~]$ cat

```

### - Analyzing the `cat` command with a **DIRECTORY PATH** argument

```
[user@sahara ~]$ cat /home/lecture1
cat: /home/lecture1: Is a directory
```

###  - Analyzing the `cat` command with a **FILE PATH** argument

```
[user@sahara ~]$ cat /home/lecture1/README
To use this program:

javac Hello.java
java Hello messages/en-us.txt
```



