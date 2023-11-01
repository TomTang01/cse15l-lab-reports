#  Lab report for lab1
##  Tom Tang A02

```
# cd
[user@sahara ~]$ cd
[user@sahara ~]$ cd lecture1
[user@sahara ~/lecture1]$ cd README
bash: cd: README: Not a directory
```
The cd command with no arguement was ran from the default directory. No arguement means to set the directory to default. 
Putting a directory as an arguement will reset the current directory of the terminal to the corresponding directory. In this case, the terminal directory is lecture1 from now on.
Putting a filepath or file as the arguement will result in an error (the only error) since a filepath or file is not a directory.
```
# ls
[user@sahara ~]$ ls
lecture1
[user@sahara ~]$ ls lecture1
Hello.class  Hello.java  messages  README
[user@sahara ~]$ ls lecture1/README
lecture1/README
```
The ls command with no arguement was ran from the default directory, same with the latter 2. It will read all the file and directory names within the default directory.
Putting a directory as the arguement tells the terminal to list the directory and file names from that corresponding directory.
Putting a filepath as the arguement just tells the terminal to print out the filepath again because it is a file thus no file underneath it to be listed.
```
# cat
[user@sahara ~]$ cat
print stuff
print stuff
yeah
yeah
^C
[user@sahara ~]$ cat lecture1
cat: lecture1: Is a directory
[user@sahara ~]$ cat lecture1/README
To use this program:

javac Hello.java
java Hello messages/en-us.txt
```
The cat command with no arguement was ran from the default directory, same with the latter 2. The cat command will print the content of the corresponding path.
Thus no arguement means to tell the terminal to read whatever is printed next in the terminal by the user.
A directory as the arguement tells the terminal to read the directory, which has no text within so returns Is a directory.
A filepath as the arguement tells the terminal to read the contents in the file.

Passed!
