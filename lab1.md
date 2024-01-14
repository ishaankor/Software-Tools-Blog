# Lab Report 1 - Remote Access and FileSystem

<ul>
  
## 1. The `cd` Command
  
<ul>
  
### - Analyzing the `cd` command with **NO** argument

<ul>

```
[user@sahara ~]$ cd
[user@sahara ~]$
```

</ul>

### - Analyzing the `cd` command with a **DIRECTORY PATH** argument

<ul>

``` 
[user@sahara ~]$ cd /home/lecture1
[user@sahara ~/lecture1]$ 
```

</ul>

### - Analyzing the `cd` command with a **FILE PATH** argument

<ul>

```
[user@sahara ~]$ cd /home/lecture1/README
bash: cd: /home/lecture1/README: Not a directory
```

</ul></ul>

## 2. Analyzing the `ls` command

<ul>

### - Analyzing the `ls` command with **NO** argument

<ul>

```
[user@sahara ~]$ ls
lecture1
```

</ul>

### - Analyzing the `ls` command with a **DIRECTORY PATH** argument

<ul>

```
[user@sahara ~]$ ls /home/lecture1
Hello.class  Hello.java  messages  README
```

</ul>

###  - Analyzing the `ls` command with a **FILE PATH** argument

<ul>

```
[user@sahara ~]$ ls /home/lecture1/README
/home/lecture1/README
```

</ul></ul>


## 3. Analyzing the `cat` command

<ul>

### - Analyzing the `cat` command with **NO** argument

<ul>

```
[user@sahara ~]$ cat

```

</ul>

### - Analyzing the `cat` command with a **DIRECTORY PATH** argument

<ul>

```
[user@sahara ~]$ cat /home/lecture1
cat: /home/lecture1: Is a directory
```

</ul>

###  - Analyzing the `cat` command with a **FILE PATH** argument

<ul>

```
[user@sahara ~]$ cat /home/lecture1/README
To use this program:

javac Hello.java
java Hello messages/en-us.txt
```

</ul></ul></ul>


