# Lab Report 1 - Remote Access and FileSystem

<ul>
  
## 1. The `cd` Command

</ul>

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Analyzing the `cd` command with **NO** argument

<ul><ul><ul>
  
```
[user@sahara ~]$ cd
[user@sahara ~]$
```

</ul></ul></ul>

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Analyzing the `cd` command with a **DIRECTORY PATH** argument

<ul><ul><ul>

``` 
[user@sahara ~]$ cd /home/lecture1
[user@sahara ~/lecture1]$ 
```

</ul></ul></ul>

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Analyzing the `cd` command with a **FILE PATH** argument

<ul><ul><ul>

```
[user@sahara ~]$ cd /home/lecture1/README
bash: cd: /home/lecture1/README: Not a directory
```

</ul></ul></ul>

## &nbsp;&nbsp;&nbsp;&nbsp; 2. Analyzing the `ls` command

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Analyzing the `ls` command with **NO** argument

<ul><ul><ul>

```
[user@sahara ~]$ ls
lecture1
```

</ul></ul></ul>

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Analyzing the `ls` command with a **DIRECTORY PATH** argument

<ul><ul><ul>

```
[user@sahara ~]$ ls /home/lecture1
Hello.class  Hello.java  messages  README
```

</ul></ul></ul>

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Analyzing the `ls` command with a **FILE PATH** argument

<ul><ul><ul>

```
[user@sahara ~]$ ls /home/lecture1/README
/home/lecture1/README
```

</ul></ul></ul>

## 3. Analyzing the `cat` command

### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Analyzing the `cat` command with **NO** argument


```
[user@sahara ~]$ cat

```
