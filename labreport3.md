# Lab Report 3 - Bugs and Commands (Week 5)

1. ## Part 1 - Bugs:
   - ### **Array Methods - `ArraryExamples.java`**:
     - Failure-inducing `JUnit` test inputs for `reversed()` and `reverseInPlace()`:
       - `reversed()`:
         ```
         @Test
         public void secondTestReversed() {
           int[] input2 = { 1, 2, 3 };
           assertArrayEquals(new int[]{ 3, 2, 1 }, ArrayExamples.reversed(input2));
         }
         ```
       - `reverseInPlace()`:
         ```
         @Test
         public void secondTestReverseInPlace() {
           int[] input2 = { 1, 2, 3 };
           ArrayExamples.reverseInPlace(input2);
           assertArrayEquals(new int[]{ 3, 2, 1 }, input2);
         }
         ```
     - Success-inducing `JUnit` test inputs for `reversed()` and `reverseInPlace()`:
       - `reversed()`:
         ```
         @Test
         public void testReversed() {
           int[] input1 = { };
           assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
         }
         ```
       - `reverseInPlace()`:
         ```
         @Test
         public void testReverseInPlace() {
           int[] input1 = { 3 };
           ArrayExamples.reverseInPlace(input1);
           assertArrayEquals(new int[]{ 3 }, input1);
         }
         ```
     - `Symptom` of running the `JUnit` tests:
    
       ![image](https://github.com/ishaankor/cse15l-lab-reports/assets/113160688/53476e47-2180-4e25-be9f-f8e19f4941eb)

       - `reversed()`:

         ![image](https://github.com/ishaankor/cse15l-lab-reports/assets/113160688/a6d8a213-e175-4b08-b608-040e40ac276d)

       - `reverseInPlace()`:
       
         ![image](https://github.com/ishaankor/cse15l-lab-reports/assets/113160688/aaa16abb-78d1-40bb-af6e-064f6a2c9d32)
  
     - `Bug` shown in before-and-after code changes:
    
       ![image](https://github.com/ishaankor/cse15l-lab-reports/assets/113160688/ecdbf8a5-315a-47c6-b8d2-6938ab286227)

       - `reversed()`:
         - Before:
           ```
           static int[] reversed(int[] arr) {
             int[] newArray = new int[arr.length];
             for(int i = 0; i < arr.length; i += 1) {
               arr[i] = newArray[arr.length - i - 1];
             }
             return arr;
           }
           ```
         - After:
           ```
           static int[] reversed(int[] arr) {
             int[] newArray = new int[arr.length];
             for(int i = 0; i < arr.length; i += 1) {
               newArray[i] = arr[arr.length - i - 1];
             }
             return newArray;
           }
           ```
         - This fix addresses the issue...
       - `reverseInPlace()`:
         - Before:
           ```
           static void reverseInPlace(int[] arr) {
             for(int i = 0; i < arr.length; i += 1) {
               arr[i] = arr[arr.length - i - 1];
             }
           }
           ```
         - After:
           ```
           static void reverseInPlace(int[] arr) {
             int[] arrCopy = arr.clone();
             for(int i = 0; i < arrCopy.length; i += 1) {
               arr[i] = arrCopy[arrCopy.length - i - 1];
             }
           }
           ```
         - This fix addresses the issue...
           
3. ## Part 2 - Researching Commands:
   - 
