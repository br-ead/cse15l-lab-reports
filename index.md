#### Before  
  ```
  static int[] reversed(int[] arr) {    
    int[] newArray = new int[arr.length];    
    for(int i = 0; i < arr.length; i += 1) {    
      newArray[i] = arr[arr.length - i - 1];    
    }    
    return arr;    
  }  
```
#### After  
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
#### Issues with the code
In the before code, the wrong value is being called for the array. It should be calling the newArray instead. There is also an issue with calling newArray[arr.length - i -1]. By calling this you are essentially only making arr[i] equal to 0. You ae basically returning an array of only 0. I made some adjustments, and returned the newArray and adjusting it to properly get the reversal.  
#### Will induce a failure with the Before code.  
```
java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ArrayTests
```
```
  @Test
  public void testReversed() {
    int[] input1 = {1, 2, 3 };
    assertArrayEquals(new int[]{ 3, 2, 1 }, ArrayExamples.reversed(input1));
  }
```
```
Admin@RN-PRO10 MINGW64 ~/Downloads/lab3-main/lab3-main
$ java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ArrayTests
JUnit version 4.13.2
.E
Time: 0.016
There was 1 failure:       
1) testReversed(ArrayTests)
arrays first differed at element [0]; expected:<3> but was:<0>
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
        at org.junit.Assert.internalArrayEquals(Assert.java:534)
        at org.junit.Assert.assertArrayEquals(Assert.java:418)
        at org.junit.Assert.assertArrayEquals(Assert.java:429)
        at ArrayTests.testReversed(ArrayTests.java:16)
        ... 30 trimmed
Caused by: java.lang.AssertionError: expected:<3> but was:<0>
        at org.junit.Assert.fail(Assert.java:89)
        at org.junit.Assert.failNotEquals(Assert.java:835)
        at org.junit.Assert.assertEquals(Assert.java:120)
        at org.junit.Assert.assertEquals(Assert.java:146)
        at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
        at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
        ... 36 more

FAILURES!!!
Tests run: 1,  Failures: 1
```
#### Will not induce a failure with the Before Code
```
  @Test
  public void testReversed() {
    int[] input1 = { 1, 1, 1};
    assertArrayEquals(new int[]{ 1, 1, 1}, ArrayExamples.reversed(input1));
  }

```
```
Admin@RN-PRO10 MINGW64 ~/Downloads/lab3-main/lab3-main
$ java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ArrayTests
JUnit version 4.13.2
.
Time: 0.006

OK (1 test)

```
#### Will not induce a failure with the After Code  
```
  public void testReversed() {
    int[] input1 = {1, 2, 3 };
    assertArrayEquals(new int[]{ 3, 2, 1 }, ArrayExamples.reversed(input1));
  }
```
![Image](Pass.PNG)   

#### Grep commands

# -c
```
grep -c "string" file.txt
```
```
Admin@RN-PRO10 MINGW64 ~/Downloads/docsearch-main/docsearch-main/technical/biomed
$ grep -c "surgery" *
1468-6708-3-1.txt:0 
1468-6708-3-10.txt:0
1468-6708-3-3.txt:1 
1468-6708-3-4.txt:0 
1468-6708-3-7.txt:0 
1471-2091-2-10.txt:0
1471-2091-2-11.txt:0
1471-2091-2-12.txt:0
1471-2091-2-13.txt:0
1471-2091-2-16.txt:0
1471-2091-2-5.txt:0 
1471-2091-2-7.txt:0 
1471-2091-2-9.txt:0 
1471-2091-3-13.txt:0
1471-2091-3-14.txt:0
1471-2091-3-15.txt:0
1471-2091-3-16.txt:0
1471-2091-3-17.txt:0
1471-2091-3-18.txt:0
1471-2091-3-22.txt:0
1471-2091-3-23.txt:0
1471-2091-3-30.txt:0
1471-2091-3-31.txt:0
1471-2091-3-4.txt:0 
1471-2091-3-8.txt:0
```
```
Admin@RN-PRO10 MINGW64 ~/Downloads/docsearch-main/docsearch-main/technical/biomed
$ grep -c "hungry" *
1468-6708-3-1.txt:0 
1468-6708-3-10.txt:0
1468-6708-3-3.txt:0 
1468-6708-3-4.txt:0 
1468-6708-3-7.txt:0 
1471-2091-2-10.txt:0
1471-2091-2-11.txt:0
1471-2091-2-12.txt:0
1471-2091-2-13.txt:0
1471-2091-2-16.txt:0
1471-2091-2-5.txt:0 
1471-2091-2-7.txt:0 
1471-2091-2-9.txt:0 
1471-2091-3-13.txt:0
```
This command will circumnavigate a file and return an integer corresponding with the number of times that string/pattern is visible in the file. Can be useful and is similar to ctrl-f  
Information taken from https://www.geeksforgeeks.org/grep-command-in-unixlinux/#  

# -i
```
grep -i "string" file.txt
```
```
Admin@RN-PRO10 MINGW64 ~/Downloads/docsearch-main/docsearch-main/technical/biomed
$ grep -i "older" 1468-6708-3-1.txt
        Older adults are frequently counseled to lose weight,      
        non-smoking older adults have investigated the association 
        in certain small subsets. A review of 13 studies of older  
        Many healthy older adults report gradual weight gain       
        number of studies of older persons is fairly small, and    
        In older adults, risk factors may have a greater effect    
        years of being healthy, in a cohort of older adults for    
        modification interventions in older adults.
          65 and older at baseline [ 11 ] . Subjects were recruited
          older men and 30-35 for older women. In Figure 1, the    
          categories could be combined for older adults. Since     
          older women could be efficient if YHL (but not YOL) was  
          interventions for older adults who were merely overweight
          evaluations should be considered critically when older   
          33 34 ] . For older adults, the risks associated with    
          outcome for a trial of weight loss in older adults       
          found for underweight older adults. Clinical trials whose
          average older adult; however, adjustment for detailed    
        older adults, especially for women. Future efforts to      
        no excess risk for older adults who would be classified as 
        obese or underweight older adults, and discouraging trials 
        that address older adults who are merely overweight.       
```
```
Admin@RN-PRO10 MINGW64 ~/Downloads/docsearch-main/docsearch-main/technical/biomed
$ grep -i "weight" 1468-6708-3-1.txt
        Older adults are frequently counseled to lose weight,      
        even though there is little evidence that overweight is    
        Many healthy older adults report gradual weight gain       
        gradual weight gain is normative and associated with the   
        weight standards be adjusted upwards for age [ 8 ] . Such  
        trials of weight modification might be more successful if  
        would yield more powerful evaluations of weight
          BMI was calculated as measured weight in kilograms       
          classifies normal weight (without reference to age) as a 
          BMI of 18.5 to 24.9; overweight as 25 to 29.9; and       
          pounds or more unintended weight loss in the year before 
          have been causally affected by the person's weight. We   
        unintended weight loss. Among blacks, gender differences   
        were significant except for 10 pounds unintended weight    
```
This command will navigate a file and return all times that the string is present and disregards casing. It will return the entire sentence in which the string was found. Would help if you need to find out all times a solo string is in a text.  
Information taken from https://www.geeksforgeeks.org/grep-command-in-unixlinux/#  

# -w

```
grep -w "string" file.txt
```
```
Admin@RN-PRO10 MINGW64 ~/Downloads/docsearch-main/docsearch-main/technical/biomed
$ grep -w "record" 1468-6708-3-4.txt
        • It is important to record and report the reasons for
```
```
Admin@RN-PRO10 MINGW64 ~/Downloads/docsearch-main/docsearch-main/technical/biomed
$ grep -w "report" 1468-6708-3-1.txt
        Many healthy older adults report gradual weight gain     
          report from the National Heart Lung and Blood Institute
          report results using only the simpler definition.
```
This command will navigate through a file, and unlike -i, it will care about casing. It will return the entire string that the searched for string is apart of. If for example, our word is blank and we have blank.txt , it will return blank.txt alongside the remaining sentence. Can be useful for finding out the number of times a string is present even when hidden in other strings.  
Information taken from https://www.geeksforgeeks.org/grep-command-in-unixlinux/#  

# -l
```
grep -l "string" *
```
```
Admin@RN-PRO10 MINGW64 ~/Downloads/docsearch-main/docsearch-main/technical/biomed
$ grep -l "ocean" *
1471-2148-3-18.txt
1471-2458-3-2.txt
1472-6793-2-5.txt
```
```
Admin@RN-PRO10 MINGW64 ~/Downloads/docsearch-main/docsearch-main/technical/biomed
$ grep -l "technology" *
1471-2091-2-12.txt
1471-2091-2-5.txt 
1471-2091-3-14.txt
1471-2105-1-1.txt
```
This command will navigate the entire directory and return all files in which the selected string is inside it. If for example, the current directory contains the files 1.txt and 2.txt, and the code is grep-l "hello" it will return 1.txt and/or 2.txt depending on if hello is within the two files. It can be useful for scanning entire chapters instead of just pages.  
Information taken from https://www.geeksforgeeks.org/grep-command-in-unixlinux/#  
