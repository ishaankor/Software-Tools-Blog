# Lab Report 3 - Bugs and Commands

1. ## Part 1 - Bugs:
   - ### **Array Methods - `ArrayExamples.java`**:
     - Failure-inducing `JUnit` test inputs for `reversed()` and `reverseInPlace()`:
       - `reversed()`:
         ```java
         @Test
         public void secondTestReversed() {
           int[] input2 = { 1, 2, 3 };
           assertArrayEquals(new int[]{ 3, 2, 1 }, ArrayExamples.reversed(input2));
         }
         ```
       - `reverseInPlace()`:
         ```java
         @Test
         public void secondTestReverseInPlace() {
           int[] input2 = { 1, 2, 3 };
           ArrayExamples.reverseInPlace(input2);
           assertArrayEquals(new int[]{ 3, 2, 1 }, input2);
         }
         ```
         - These `JUnit` tests both produce failures as the functions cannot perform the necessary operations needed to return the correct return values. These `test cases` have multiple `inputs` and is the reason why the `functions` can't process with these `parameters`.
         
     - Success-inducing `JUnit` test inputs for `reversed()` and `reverseInPlace()`:
       - `reversed()`:
         ```java
         @Test
         public void testReversed() {
           int[] input1 = { };
           assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
         }
         ```
       - `reverseInPlace()`:
         ```java
         @Test
         public void testReverseInPlace() {
           int[] input1 = { 3 };
           ArrayExamples.reverseInPlace(input1);
           assertArrayEquals(new int[]{ 3 }, input1);
         }
         ```
         - As for these `JUnit` tests, they produce successes as the `inputs` are either one value or empty. Seeing how there is no need to reverse such `test cases`, it will be successful.
         
     - `Symptom` of running the `JUnit` tests:
    
       ![Untitled](https://github.com/ishaankor/cse15l-lab-reports/assets/113160688/88ea4a8f-731f-415b-bd5e-2ba2e64770a1)

       - `reversed()`:

         ![image](https://github.com/ishaankor/cse15l-lab-reports/assets/113160688/a6d8a213-e175-4b08-b608-040e40ac276d)
    
         - This `symptom` shows how the `JUnit` test case (`secondTestReversed()`) failed as it couldn't find the correct values within the positions of the object containing `ArrayExamples.reversed(input2)`. 

       - `reverseInPlace()`:
       
         ![image](https://github.com/ishaankor/cse15l-lab-reports/assets/113160688/aaa16abb-78d1-40bb-af6e-064f6a2c9d32)
       
         - This `symptom` shows how the `JUnit` test case (`secondTestReverseInPlace()`) failed as it couldn't find the correct values within the positions of the object containing `assertArrayEquals(new int[]{ 3, 2, 1 }, input2)`. 
  
     - `Bug` shown in before-and-after code changes:
    
       ![image](https://github.com/ishaankor/cse15l-lab-reports/assets/113160688/ecdbf8a5-315a-47c6-b8d2-6938ab286227)

       - `reversed()`:
         - Before:
           ```java
           static int[] reversed(int[] arr) {
             int[] newArray = new int[arr.length];
             for(int i = 0; i < arr.length; i += 1) {
               arr[i] = newArray[arr.length - i - 1];
             }
             return arr;
           }
           ```
         - After:
           ```java
           static int[] reversed(int[] arr) {
             int[] newArray = new int[arr.length];
             for(int i = 0; i < arr.length; i += 1) {
               newArray[i] = arr[arr.length - i - 1];
             }
             return newArray;
           }
           ```
           - This fix addresses the issue as it fixes the correct `ArrayList` being reversed. The `bug` lies in `arr[i] = newArray[arr.length - i - 1];` as the function aims to return a new `int ArrayList` that is a reverse of the `parameter`. By swapping `arr[i]` with `newArray[i]`, the method effectively reverses the `parameter` and returns the `ArrayList` in `newArray`.
           
       - `reverseInPlace()`:
         - Before:
           ```java
           static void reverseInPlace(int[] arr) {
             for(int i = 0; i < arr.length; i += 1) {
               arr[i] = arr[arr.length - i - 1];
             }
           }
           ```
         - After:
           ```java
           static void reverseInPlace(int[] arr) {
             int[] arrCopy = arr.clone();
             for(int i = 0; i < arrCopy.length; i += 1) {
               arr[i] = arrCopy[arrCopy.length - i - 1];
             }
           }
           ```
           - This fix addresses the issue as it fixes the recursive process of reassigning the values in `int[] arr` (the `parameter`) when parsing through it. This function wants to return a reverse of the `parameter` instead of a new `int ArrayList` - essentially, the opposite of `reversed()`. The changed code creates a copy of the `parameter`, which is then  parsed through in order to assign the correct values to `arr`.

2. ## Part 2 - Researching Commands:
   - ### The `grep` command-line options:
     - `grep --line-number`:
       - File - `1477-7819-1-10.txt`:
         ```
         ishaank@Ishaans-MacBook-Pro-2 technical % grep "bio" --line-number ./biomed/1477-7819-1-10.txt
         168:        examination or biopsy.
         187:        The technique of sentinel node biopsy is gaining
         189:        lymphatic drainage, so sentinel node biopsy is useful when
         ```
       - Directory - `./biomed`:
         ```
         ishaank@Ishaans-MacBook-Pro-2 technical % grep "java" -r --line-number ./biomed/
         ./biomed//gb-2003-4-4-r26.txt:303:          M. javanica BI324412). In
         ./biomed//gb-2003-4-4-r26.txt:315:          M. javanica isocitrate lyase ESTs
         ./biomed//gb-2003-4-4-r26.txt:586:          M. javanica, M. hapla and
         ./biomed//gb-2003-4-4-r26.txt:695:        M. javanica 5,600,
         ./biomed//gb-2003-4-4-r26.txt:1036:          M. javanica sequences). An
         ./biomed//gb-2003-4-4-r26.txt:1049:          M. javanica matches but not
         ./biomed//gb-2001-2-8-research0030.txt:381:          Meloidogyne javanica. Presumably,
         ./biomed//1471-2105-3-12.txt:299:            occurred. Please try again later java lang.NullPointer
         ./biomed//1471-2105-4-25.txt:363:          the java technology provided by the Apache Tomcat server
         ./biomed//gb-2003-4-6-r39.txt:173:        M. incognita, M. javanica and
         ./biomed//gb-2003-4-6-r39.txt:203:          M. javanica and
         ./biomed//gb-2003-4-6-r39.txt:217:          M. javanica sequences, named WMi
         ./biomed//gb-2003-4-6-r39.txt:304:          M. javanica during evolution of
         ./biomed//gb-2003-4-6-r39.txt:310:          M. javanica [ 20 ] . To examine why
         ./biomed//gb-2003-4-6-r39.txt:334:          M. javanica and
         ./biomed//gb-2003-4-6-r39.txt:484:          M. javanica with the cognate genes
         ./biomed//gb-2003-4-6-r39.txt:752:          M. javanica (WMj) sequences from
         ./biomed//gb-2003-4-6-r39.txt:758:          M. javanica datasets from NCBI (NMi
         ```
         - The `--line-number` command-line option works by finding the *PATTERN* (in this case, it was "bio" and "java" for their respective test cases) in a file and the line in which they are located in. This tends to be incredibly useful as it allows the user to quickly find the correct line to search for regarding the given *PATTERN* in any file - this saves a lot of time!
           - Source: <https://man7.org/linux/man-pages/man1/grep.1.html>
         
     - `grep --count`:
       - File - `1-3_meth_901.txt`:
         ```
         ishaank@Ishaans-MacBook-Pro-2 technical % grep --count "test" ./government/Env_Prot_Agen/1-3_meth_901.txt
         92
         ```
       - Directory - `./government/Env_Prot_Agen`:
         ```
         ishaank@Ishaans-MacBook-Pro-2 technical % grep -r --count "test" ./government/Env_Prot_Agen
         ./government/Env_Prot_Agen/multi102902.txt:18
         ./government/Env_Prot_Agen/section-by-section_summary.txt:0
         ./government/Env_Prot_Agen/jeffordslieberm.txt:0
         ./government/Env_Prot_Agen/final.txt:0
         ./government/Env_Prot_Agen/ctf7-10.txt:338
         ./government/Env_Prot_Agen/ctf1-6.txt:325
         ./government/Env_Prot_Agen/ro_clear_skies_book.txt:0
         ./government/Env_Prot_Agen/ctm4-10.txt:580
         ./government/Env_Prot_Agen/1-3_meth_901.txt:92
         ./government/Env_Prot_Agen/atx1-6.txt:307
         ./government/Env_Prot_Agen/tech_sectiong.txt:0
         ./government/Env_Prot_Agen/bill.txt:1
         ./government/Env_Prot_Agen/nov1.txt:6
         ./government/Env_Prot_Agen/tech_adden.txt:6
         ```
         - The `--count` command-line option is useful in finding out how many instances of the *PATTERN* that exists within any file - this gives the user a numerical summary of the *PATTERN* occurences. It works by counting the instances of *PATTERN* in a file and then outputs the total number per file.
           - Source: <https://man7.org/linux/man-pages/man1/grep.1.html>
         
     - `grep --before-context`:
       - File - `chapter 8.txt`:
         ```
         ishaank@Ishaans-MacBook-Pro-2 technical % grep "retaliate" --before-context=1 ./911report/chapter-8.txt
         "bring the fighting to America." After US missile strikes on his base in
         Afghanistan in 1998, Bin Ladin told followers he wanted to retaliate in
         ```
       - Directory - `./911report`:
         ```
         ishaank@Ishaans-MacBook-Pro-2 technical % grep "retaliate" -r --before-context=1 ./911report/
         ./911report//chapter-3.txt-                Center acknowledged that hitches might develop. People might be killed, and Bin
         ./911report//chapter-3.txt:                Ladin's supporters might retaliate, perhaps taking U.S. citizens in Kandahar
         --
         ./911report//chapter-6.txt-
         ./911report//chapter-6.txt:            Rice told us that there was never a formal, recorded decision not to retaliate
         --
         ./911report//chapter-8.txt-                    "bring the fighting to America." After US missile strikes on his base in
         ./911report//chapter-8.txt:                    Afghanistan in 1998, Bin Ladin told followers he wanted to retaliate in
         ```
         - The `--before-context` command-line option finds all instances of the *PATTERN* and outputs the line (context) that comes **before** each instance. This option is quite
        useful when gathering information about the *PATTERN* as it gives the user a defined number of lines that come before the *PATTERN* instance, effectively giving **context**.
           - Source: <https://man7.org/linux/man-pages/man1/grep.1.html>

     - `grep --ignore-case`:
       - File - `Advocate_for_Poor.txt`:
         ```
         ishaank@Ishaans-MacBook-Pro-2 technical % grep "poor" -r  --ignore-case ./government/Media/Advocate_for_Poor.txt
         ./government/Media/Advocate_for_Poor.txt:Advocate for Poor Has Own Obstacles
         ./government/Media/Advocate_for_Poor.txt:helping East New York's poor, he's getting booted from the bodega
         ./government/Media/Advocate_for_Poor.txt:helping the working poor navigate the legal system. Immigration,
         ```
       - Directory - `./government/Media`:
         ```
         ishaank@Ishaans-MacBook-Pro-2 technical % grep "test" -r  --ignore-case ./government/Media/
         ./government/Media//water_fees.txt:51% of property owners in the district must submit protest votes in
         ./government/Media//water_fees.txt:writing. No protest vote means approval of the price jump.
         ./government/Media//water_fees.txt:protest votes at the July 17 meeting
         ./government/Media//Unusual_Woodburn.txt:Woodburn, is a testament to the difficulty of reaching the
         ./government/Media//Few_who_need.txt:the former and avoid the latter in a one-sided contest where only
         ./government/Media//Legal_hotline.txt:David Mandel, supervising attorney, protested to federal
         ./government/Media//New_Online_Resources.txt:"We are replacing the older test site with two dynamic
         ./government/Media//Annual_Fee.txt:Most of the latest increase -- $42 -- will go to the Lawyers
         ./government/Media//predatory_loans.txt:their debts. The latest is Fieldstone Mortgage Co., which is
         ./government/Media//Working_for_Free.txt:his greatest honor comes from earning praise from his students.
         ./government/Media//Terrorist_Attack.txt:more useful test of future lawyers' potential than rote memory, and
         ./government/Media//Terrorist_Attack.txt:testy judges may feel like fish out of water in the great sea of
         ./government/Media//Poverty_Lawyers.txt:firms were saying that they were losing the best and the brightest,
         ./government/Media//Wingates_winds.txt:That was among the latest ideas suggested in a proposed study
         ./government/Media//Assuring_Underprivileged.txt:protest.
         ./government/Media//Assuring_Underprivileged.txt:The attorneys who appear before Zelon attest to the fact that
         ./government/Media//Assuring_Underprivileged.txt:Competition, a contract-negotiating contest open to first-year law
         ./government/Media//Assuring_Underprivileged.txt:Zelon faced one of the greatest challenges of her legal career,
         ./government/Media//Assuring_Underprivileged.txt:their use of hearsay testimony.
         ./government/Media//Making_a_case.txt:testimony.
         ./government/Media//Making_a_case.txt:require testimony.
         ./government/Media//Commercial_Appeal.txt:poor people it serves in four counties, according to the latest
         ./government/Media//Civil_Matters.txt:revenue estimating conference, which will give lawmakers the latest
         ./government/Media//Domestic_violence_aid.txt:testimony of the victim."
         ./government/Media//CommercialAppealMemphis2.txt:counties qualify for public legal aid, the latest census shows a
         ./government/Media//Barr_sharpening_ax.txt:LSC President John Erlenborn recently testified to Congress that
         ./government/Media//Legal_services_for_poor.txt:poverty rate declined about 3 percent under the latest Census
         ./government/Media//Understanding.txt:years. But the latest census figures and an influx of grant money
         ./government/Media//A_Perk_of_Age.txt:with the greatest financial or social needs. The federal Agency
         ./government/Media//Greedy_Generous.txt:information about the latest salary increase or layoffs is shared
         ./government/Media//Greedy_Generous.txt:generousassociates are another testament to the profession's
         ```
         - The `--ignore-case` command-line option is similar to that of `--before-context` except it only provides the exact line in which the *PATTERN* instance occured. This is useful if people are looking for the lines in which the *PATTERN* are located in regardless of case senstivity and context.
           - Source: <https://man7.org/linux/man-pages/man1/grep.1.html>
        
