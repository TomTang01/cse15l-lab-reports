#  Lab 8&9 Report
## Part 1
**Student Post:** 
```
Hi, I am currently having some issues with the grade.sh in lab6. When I run the code with
the correct methods, it shows a compile error. Here is a screenshot:
```
![Image](https://github.com/TomTang01/cse15l-lab-reports/blob/main/labreport5/output.png)
```
The error messages mean that they cannot find the junit package. But I did `javac` and `java`
with junit as needed. Here is a screenshot of running the Test code:
```
![Image](http://url/a.png)


---
## Part 2
I learnt a lot of new skills in debugging. `JDB` was something I did not know of and I think it is one of the best ways of debugging 
because you can look at all of the local variables at a given time thus easy to see where the bug is.
A more specific thing I learnt is that the bash commands `javac -cp $CPATH *.java` `java -cp $CPATH org.junit.runner.JUnitCore TestListExamples` (CPATH stored as a variable before hand) 
doesn't work if the java files that I want to test are in another directory. I put pathnames before the java files but it still doesn't work. 
Yet when I changed directory into the directory of the java files, the command works just fine.
