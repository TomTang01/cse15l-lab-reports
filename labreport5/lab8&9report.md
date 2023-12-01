#  Lab 8&9 Report
## Part 1
**Student Post:** 
Hi, I am currently having some issues with the grade.sh in lab6. When I run the code with
the correct methods, it shows a compile error. My failure inducing input is `bash grade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected`. 
Here is a screenshot:

![Image](https://github.com/TomTang01/cse15l-lab-reports/blob/main/labreport5/output.png)

The error messages mean that they cannot find the junit package. But I did `javac` and `java`
with junit as needed. CPATH was declared as `CPATH='.;/lib/hamcrest-core-1.3.jar;/lib/junit-4.13.2.jar'`. 
I tried running junit in the terminal outside of the `grade.sh` file and it works fine, so this means that my `ListExamples.java` and `TestLestExamples.java` are both correct. Here is a screenshot of how I ran the Test code in `grade.sh`:

![Image](https://github.com/TomTang01/cse15l-lab-reports/blob/main/labreport5/code.png)



**TA Response:**

It seems that the directory you are running the grade.sh is not the same directory as the Test java files, which if I am not mistaken are in the subdirectory `grading-area`. In this case I would reccommend changing directory into `grading-area` before running `javac -cp $CPATH *.java` and `java -cp $CPATH org.junit.runner.JUnitCore TestListExamples`. As I have written here, the java files do not contain the pathnames. Remember to change CPATH to the relative location of the `grading-area` instead of `LIST-EXAMPLES-GRADER`.



**Student Reply:**
It worked! Thank you so much!

![Image](labreport5/coutput.png)

The java file names after the `javac` and `java` commands calling junit cannot contain pathnames. You have to change directory to make it work.

---

## Part 2
I learnt a lot of new skills in debugging. `JDB` was something I did not know of and I think it is one of the best ways of debugging 
because you can look at all of the local variables at a given time thus easy to see where the bug is.
A more specific thing I learnt is that the bash commands `javac -cp $CPATH *.java` `java -cp $CPATH org.junit.runner.JUnitCore TestListExamples` (CPATH stored as a variable before hand) 
doesn't work if the java files that I want to test are in another directory. I put pathnames before the java files but it still doesn't work. 
Yet when I changed directory into the directory of the java files, the command works just fine.
