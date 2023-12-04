### git clone https://github.com/ucsd-cse15l-s23/lab7 or git@github.com:ucsd-cse15l-s23/lab7.git
```
[cs15lfa23sd@ieng6-201]:lab7w:229$ bash test.sh
JUnit version 4.13.2
..E
Time: 0.671
There was 1 failure:
1) testMerge2(ListExamplesTests)
org.junit.runners.model.TestTimedOutException: test timed out after 500 milliseconds
        at java.base/java.util.Arrays.copyOf(Arrays.java:3512)
        at java.base/java.util.Arrays.copyOf(Arrays.java:3481)
        at java.base/java.util.ArrayList.grow(ArrayList.java:237)
        at java.base/java.util.ArrayList.grow(ArrayList.java:244)
        at java.base/java.util.ArrayList.add(ArrayList.java:454)
        at java.base/java.util.ArrayList.add(ArrayList.java:467)
        at ListExamples.merge(ListExamples.java:42)
        at ListExamplesTests.testMerge2(ListExamplesTests.java:19)

FAILURES!!!
Tests run: 2,  Failures: 1
```
## vim ListExamples.java
## j x10 to navigate to the selected line
## l x 62 to navigate to text
## x x 2 to delete text
## i
## "checker"
## <esc>
## j x3 
## h x 19
## x x 2
## i 
## "checker" 
## <esc> 
## j x 13
## l x 12
## i <r arrow key >
## <enter>
## “system.out.printf(%d,%d,index1,index2);"
## <esc>
## :wq
## vim ListExamplesTests.java
## <ctrl>+c 
## j x 21
## <ctrl>+v
## j x 5
## x x 25
## k x 3
## x x 5
## k x 1
## x x 8
## j x 3
## x x 12
## l x 63
## x 
## l x 4
## x 
## k 
## x
## h x 3
## x 
## j x 3
## h x 30
## x x 30
## :wq
```
[cs15lfa23sd@ieng6-201]:lab7w:267$ bash test.sh
JUnit version 4.13.2
...
Time: 0.147

OK (3 tests)

[cs15lfa23sd@ieng6-201]:lab7w:268$
```
## git add .
## git commit
## "Revisions"
## git push

