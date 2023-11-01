#  Lab Report 3

##  Bugs
The error I choose was from the ArrayExamples class.
A failure-inducing input would be:
```
@Test 
public void testReverseInPlace2() {
    int[] input1 = { 3,2,1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1,2,3 }, input1);
}
```
An input that does not fail would be:
```

@Test 
public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
}
```
The symptom of the failure-inducing input that the element of index 2 of the actual output of the testReverseInPlace2 method is 3 when it should be 1. Here is the screenshot:
![Image](symptom1.png)
The part of the code containing the bug:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}
```
A reason why we are not getting the expected output is that the reverseInPlace method loops through the whole array. This means that even if we assume that it does swap elements, it swaps them twice hence no swap at all. In fact, the replaceInPlace method fails to swap the elements. It merely copies the element from the back and use them to replace the elements in the front half. To fix it we need to divide the arr.length in the condition statement in the for loop by 2 and create a new int variable to store the current arr[i] before copying arr[arr.length - i - 1] to arr[i]. Then copy the value in current to arr[arr.length - i - 1]. The code after the fix is:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
        int temp = arr[i];
        arr[i] = arr[arr.length - i - 1];
        arr[arr.length - i - 1] = temp;
    }
}
```
---

##  Researching Commands
The command I chose is `grep`. 4 command-line options of grep:
* -i: Ignore uppercase vs. lowercase
Ignore  case  distinctions,  so that characters that differ only in case match each other.
* -v: Invert match
Invert the sense of matching, to select non-matching lines.
* -l: --files-with-matches
Suppress  normal  output;  instead  print  the name of each input file from  which  output  would  normally  have  been printed.  The scanning will stop on the first match.
* -r, --recursive
Read all files under each directory, recursively, following symbolic  links only if they are on the command line.  Note that if no file operand is given, grep searches the working directory.  This is equivalent to the -d recurse option.
