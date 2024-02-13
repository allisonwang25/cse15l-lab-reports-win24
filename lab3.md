# Lab Report 3: Bugs and Commands
## Part 1: Bugs
* Failure Inducing Input for ArrayExamples:
  ```java
  @Test
  public void testReverseInPlaceMultipleItemArray() {
    int[] input1 = {3,4,5};
    ArrayExamples.reverseInPlace(input1);
            assertArrayEquals(new int[]{5,4,3}, input1);
  }
  ```
* Input that Doesn't Induce Failure for ArrayExamples:
  ```java
  @Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
  ```
* Symptom:
  [Screenshot of output of tests](bugSymptoms.png)
* Bug:
    * Before Fix:
      ```java
      static void reverseInPlace(int[] arr) {
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = arr[arr.length - i - 1];
        }
      }
      ```
    * After Fix:
      ```java
      static void reverseInPlace(int[] arr) {
        int tempHold = arr[0];
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = arr[arr.length - i - 1];
        }
        arr[arr.length-1] = tempHold;
      }
      ```
## Part 2: Researching Commands - GREP
  * -r
    * example 1:
      * ```
        allisonwang@Allisons-MacBook-Pro technical % grep -r ".txt"
        ```
      * ```
        ./biomed/gb-2003-4-5-r34.txt:            20,000), and repeat the process. The Readme.txt file
        ./biomed/gb-2001-2-7-research0025.txt:        Pfam_Annotation.txt
        ./biomed/gb-2001-2-7-research0025.txt:        Protein_Annotation.txt
        ./biomed/gb-2002-3-7-research0037.txt:        README.txt contains instructions for installation and
        ./biomed/gb-2002-3-6-software0001.txt:        as .txt files (tab-delimited text, refer to the user's
        ./biomed/gb-2002-3-12-research0078.txt:          .txt extension.
        ./biomed/gb-2001-2-9-research0037.txt:          hyb2dis.txt in additional data files). More importantly,
        ./biomed/gb-2001-2-9-research0037.txt:        hyb2dis.txt: patch file that converts White's hybridize
        ./biomed/gb-2001-2-9-research0037.txt:        Training sets(GlycineMedicago.txt,Rhizobia.txt,
        ./biomed/gb-2001-2-9-research0037.txt:        Stramenopiles.txt, ZygoChytrid.txt): FASTA-formatted text
        ./biomed/gb-2001-2-9-research0037.txt:        Test sets(PsojaeHA.txt, PsojaeMY.txt, PsojaeZO.txt,
        ./biomed/gb-2001-2-9-research0037.txt:        MtRHE.txt, DSIR.txt, MHAM.txt, KV0.txt, KV2.txt, KV3.txt):
        ./biomed/gb-2001-2-9-research0037.txt:        hyb2dis.txt
        ./biomed/gb-2001-2-9-research0037.txt:        hyb2dis.txt
        ./biomed/gb-2001-2-9-research0037.txt:        GlycineMedicago.txt
        ./biomed/gb-2001-2-9-research0037.txt:        Rhizobia.txt
        ./biomed/gb-2001-2-9-research0037.txt:        Stramenopiles.txt
        ./biomed/gb-2001-2-9-research0037.txt:        ZygoChytrid.txt
        ./biomed/gb-2001-2-9-research0037.txt:        PsojaeHA.txt
        ./biomed/gb-2001-2-9-research0037.txt:        PsojaeMY.txt
        ./biomed/gb-2001-2-9-research0037.txt:        PsojaeZO.txt
        ./biomed/gb-2001-2-9-research0037.txt:        MtRHE.txt
        ./biomed/gb-2001-2-9-research0037.txt:        DSIR.txt
        ./biomed/gb-2001-2-9-research0037.txt:        KV0.txt
        ./biomed/gb-2001-2-9-research0037.txt:        KV2.txt
        ./biomed/gb-2001-2-9-research0037.txt:        KV3.txt
        ./biomed/1471-2105-2-9.txt:            of files (e.g., seq or txt files) or from a
        ./biomed/1471-2105-2-9.txt:            fasta_groups.txt output file contains the group name
        ./biomed/1471-2105-2-9.txt:            format. The fasta_groups.txt file is particularly
        ./biomed/1471-2105-2-9.txt:            output file, group_seqs.txt, contains the group name
        ./biomed/1471-2105-2-9.txt:            output file, group_files.txt, contains the group name,
        ./biomed/1471-2105-2-9.txt:            file, coverage.txt, shows how many sequences are in
        ./biomed/1471-2105-2-9.txt:            Good [ 7 ] . Finally, the infile.txt file contains all
        ./biomed/1471-2105-2-9.txt:          from the 3' end and looking at the group_seqs.txt output
        ./biomed/1471-2105-2-9.txt:          to the fasta_groups.txt file, which is ideal for Clustal
        ./biomed/gb-2002-3-12-research0071.txt:        'EtOH.txt', 'SwiSnfMin.txt'and 'SwiSnfRich.txt', and
        ./biomed/gb-2002-3-12-research0071.txt:        'Zinc.txt'.
        ./biomed/1471-2105-2-1.txt:          Also attached are a users' manual (user.txt - see
        ./biomed/1471-2105-3-6.txt:          readme.txt documentation file are also included.
        ./biomed/1471-2105-3-4.txt:          conversions of .chp (.txt) for each individual profile
        ```
    * example 2:
      * ```
        allisonwang@Allisons-MacBook-Pro biomed % grep -r ".txt"
        ```
      * ```
        ./gb-2003-4-5-r34.txt:            20,000), and repeat the process. The Readme.txt file
        ./gb-2001-2-7-research0025.txt:        Pfam_Annotation.txt
        ./gb-2001-2-7-research0025.txt:        Protein_Annotation.txt
        ./gb-2002-3-7-research0037.txt:        README.txt contains instructions for installation and
        ./gb-2002-3-6-software0001.txt:        as .txt files (tab-delimited text, refer to the user's
        ./gb-2002-3-12-research0078.txt:          .txt extension.
        ./gb-2001-2-9-research0037.txt:          hyb2dis.txt in additional data files). More importantly,
        ./gb-2001-2-9-research0037.txt:        hyb2dis.txt: patch file that converts White's hybridize
        ./gb-2001-2-9-research0037.txt:        Training sets(GlycineMedicago.txt,Rhizobia.txt,
        ./gb-2001-2-9-research0037.txt:        Stramenopiles.txt, ZygoChytrid.txt): FASTA-formatted text
        ./gb-2001-2-9-research0037.txt:        Test sets(PsojaeHA.txt, PsojaeMY.txt, PsojaeZO.txt,
        ./gb-2001-2-9-research0037.txt:        MtRHE.txt, DSIR.txt, MHAM.txt, KV0.txt, KV2.txt, KV3.txt):
        ./gb-2001-2-9-research0037.txt:        hyb2dis.txt
        ./gb-2001-2-9-research0037.txt:        hyb2dis.txt
        ./gb-2001-2-9-research0037.txt:        GlycineMedicago.txt
        ./gb-2001-2-9-research0037.txt:        Rhizobia.txt
        ./gb-2001-2-9-research0037.txt:        Stramenopiles.txt
        ./gb-2001-2-9-research0037.txt:        ZygoChytrid.txt
        ./gb-2001-2-9-research0037.txt:        PsojaeHA.txt
        ./gb-2001-2-9-research0037.txt:        PsojaeMY.txt
        ./gb-2001-2-9-research0037.txt:        PsojaeZO.txt
        ./gb-2001-2-9-research0037.txt:        MtRHE.txt
        ./gb-2001-2-9-research0037.txt:        DSIR.txt
        ./gb-2001-2-9-research0037.txt:        KV0.txt
        ./gb-2001-2-9-research0037.txt:        KV2.txt
        ./gb-2001-2-9-research0037.txt:        KV3.txt
        ./1471-2105-2-9.txt:            of files (e.g., seq or txt files) or from a
        ./1471-2105-2-9.txt:            fasta_groups.txt output file contains the group name
        ./1471-2105-2-9.txt:            format. The fasta_groups.txt file is particularly
        ./1471-2105-2-9.txt:            output file, group_seqs.txt, contains the group name
        ./1471-2105-2-9.txt:            output file, group_files.txt, contains the group name,
        ./1471-2105-2-9.txt:            file, coverage.txt, shows how many sequences are in
        ./1471-2105-2-9.txt:            Good [ 7 ] . Finally, the infile.txt file contains all
        ./1471-2105-2-9.txt:          from the 3' end and looking at the group_seqs.txt output
        ./1471-2105-2-9.txt:          to the fasta_groups.txt file, which is ideal for Clustal
        ./gb-2002-3-12-research0071.txt:        'EtOH.txt', 'SwiSnfMin.txt'and 'SwiSnfRich.txt', and
        ./gb-2002-3-12-research0071.txt:        'Zinc.txt'.
        ./1471-2105-2-1.txt:          Also attached are a users' manual (user.txt - see
        ./1471-2105-3-6.txt:          readme.txt documentation file are also included.
        ./1471-2105-3-4.txt:          conversions of .chp (.txt) for each individual profile
        ```
    * The -r command recursively searches for the given "phrase" through the contents of all of the files in the current directory as well as in any files within subdirectories that could have the specified phrase. This is useful because you can look through the entire directory without having to specify how deep in subdirectories you want to look. 

  * -l
    * example 1:
      * ```
        allisonwang@Allisons-MacBook-Pro biomed % grep -r -l ".txt"
        ```
      * ```
        ./gb-2003-4-5-r34.txt
        ./gb-2001-2-7-research0025.txt
        ./gb-2002-3-7-research0037.txt
        ./gb-2002-3-6-software0001.txt
        ./gb-2002-3-12-research0078.txt
        ./gb-2001-2-9-research0037.txt
        ./1471-2105-2-9.txt
        ./gb-2002-3-12-research0071.txt
        ./1471-2105-2-1.txt
        ./1471-2105-3-6.txt
        ./1471-2105-3-4.txt
        ```
    * example 2:
      * ```
        allisonwang@Allisons-MacBook-Pro technical % grep -r -l ".txt"
        ```
      * ```
        ./biomed/gb-2003-4-5-r34.txt
        ./biomed/gb-2001-2-7-research0025.txt
        ./biomed/gb-2002-3-7-research0037.txt
        ./biomed/gb-2002-3-6-software0001.txt
        ./biomed/gb-2002-3-12-research0078.txt
        ./biomed/gb-2001-2-9-research0037.txt
        ./biomed/1471-2105-2-9.txt
        ./biomed/gb-2002-3-12-research0071.txt
        ./biomed/1471-2105-2-1.txt
        ./biomed/1471-2105-3-6.txt
        ./biomed/1471-2105-3-4.txt
        ```
    * The -l command prints out the names of all the files that contain the key phrase rather than printing out every single time the phrase comes up in any of the files. This is useful because it gives the information about when the key phrase pops up but is potentially less expensive since it stops searching through the file once it finds first instance of the key phrase
  * -L
    * example 1: 
      * ```
        allisonwang@Allisons-MacBook-Pro biomed % grep -r -L ".txt"
        ```
      * ```
        ./1472-6807-2-2.txt
        ./1471-2350-4-3.txt
        ./1471-2156-2-3.txt
        ./1471-2156-3-11.txt
        ./1471-2121-3-10.txt
        ./1471-2172-3-4.txt
        ./gb-2002-4-1-r2.txt
        ./gb-2003-4-6-r41.txt
        ./1471-2466-1-1.txt
        ./1471-2199-2-10.txt
        ./1471-2202-2-9.txt
        ./cc991.txt
        ./1471-2369-3-9.txt
        ./bcr620.txt
        ./1476-069X-2-4.txt
        ./1472-6750-3-11.txt
        ./1471-2164-2-9.txt
        ./1471-2091-2-10.txt
        ./gb-2001-2-4-research0010.txt
        ./gb-2003-4-4-r24.txt
        ./1471-213X-2-1.txt
        ./1472-6882-3-3.txt
        ./1471-2407-2-3.txt
        ./ar331.txt
        ./ar319.txt
        ./1471-2156-4-5.txt
        ./1471-2431-2-1.txt
        ./1476-4598-2-22.txt
        ./1471-2180-2-22.txt
        ./1471-2334-3-9.txt
        ./1471-2091-2-11.txt
        ./gb-2001-2-4-research0011.txt
        ./1471-2202-4-12.txt
        ./rr73.txt
        ./1471-2164-2-8.txt
        ./1471-2148-2-12.txt
        ./bcr635.txt
        ./1468-6708-3-10.txt
        ./1471-2202-2-8.txt
        ./1471-2121-3-11.txt
        ./1471-2156-3-10.txt
        ./1471-2458-3-20.txt
        ./1471-2350-4-2.txt
        ./1472-6807-2-3.txt
        ./1472-6807-2-1.txt
        ./1476-4598-1-8.txt
        ./1477-7525-1-9.txt
        ./ar79.txt
        ./1476-0711-2-7.txt
        ./1472-6947-3-8.txt
        ./1471-2121-3-13.txt
        ./gb-2002-4-1-r1.txt
        ./1471-2407-3-18.txt
        ./1471-2229-2-3.txt
        ./1471-2334-1-9.txt
        ./gb-2002-3-9-research0043.txt
        ./1471-2415-3-5.txt
        ./1471-2334-1-21.txt
        ./ar130.txt
        ./1476-069X-2-7.txt
        ./1472-6890-2-5.txt
        ./ar118.txt
        ./gb-2002-3-7-research0032.txt
        ./1471-2253-2-5.txt
        ./1471-2210-1-10.txt
        ./1471-2091-2-13.txt
        ./1471-2180-2-20.txt
        ./1471-2202-3-19.txt
        ./1471-2202-4-10.txt
        ./1472-6963-2-10.txt
        ./1476-4598-2-20.txt
        ./1471-2156-4-6.txt
        ./1471-2458-3-5.txt
        ./1472-6769-1-4.txt
        ./gb-2003-4-4-r26.txt
        ./1472-6882-3-1.txt
        ./cc4.txt
        ./1471-2180-2-35.txt
        ./1471-2202-4-11.txt
        ./gb-2001-2-4-research0012.txt
        ./1471-2091-2-12.txt
        ./1471-2253-2-4.txt
        ./gb-2001-2-7-research0024.txt
        ./1471-2415-3-4.txt
        ./1471-2199-2-12.txt
        ./1471-2121-3-12.txt
        ./1471-2148-1-8.txt
        ./gb-2001-2-3-research0008.txt
        ./1471-2156-2-1.txt
        ./1471-2466-3-1.txt
        ./bcr568.txt
        ./gb-2003-4-7-r46.txt
        ./1475-2875-2-14.txt
        ./1471-2288-2-4.txt
        ./1472-6785-1-3.txt
        ./ar93.txt
        ./1472-6831-2-2.txt
        ./bcr583.txt
        ./cc367.txt
        ./1477-7827-1-17.txt
        ./1477-7827-1-13.txt
        ./1472-6807-2-4.txt
        ./1471-2156-3-17.txt
        ./1475-2875-2-10.txt
        ./gb-2003-4-7-r42.txt
        ./1471-2156-2-5.txt
        ./ar68.txt
        ./1471-2172-3-2.txt
        ./1471-2121-3-16.txt
        ./1472-6750-1-12.txt
        ./1472-6904-2-7.txt
        ./1472-6882-1-7.txt
        ./1471-2334-1-24.txt
        ./1471-2377-2-4.txt
        ./gb-2002-3-9-research0046.txt
        ./rr74.txt
        ./gb-2001-2-8-research0027.txt
        ./1476-069X-2-2.txt
        ./1471-2148-2-15.txt
        ./1472-6874-2-1.txt
        ./1471-2210-1-8.txt
        ./1471-2091-3-8.txt
        ./1472-6793-2-8.txt
        ./1471-213X-2-7.txt
        ./1471-2202-3-20.txt
        ./1471-2091-2-16.txt
        ./1476-4598-2-25.txt
        ./1471-230X-2-21.txt
        ./1476-4598-2-24.txt
        ./1471-2350-2-2.txt
        ./gb-2001-2-11-research0046.txt
        ./1472-6769-1-1.txt
        ./ar120.txt
        ./1471-2148-2-14.txt
        ./1471-2407-1-19.txt
        ./gb-2001-2-8-research0032.txt
        ./gb-2002-3-7-research0036.txt
        ./1471-2415-3-1.txt
        ./gb-2003-4-5-r32.txt
        ./1472-6750-1-13.txt
        ./1472-6920-1-3.txt
        ./1471-2474-2-1.txt
        ./1476-0711-2-3.txt
        ./rr171.txt
        ./1471-2156-3-16.txt
        ./gb-2003-4-7-r43.txt
        ./1472-6807-2-5.txt
        ./1471-2350-4-4.txt
        ./1471-2172-1-1.txt
        ./ar297.txt
        ./1471-2350-4-6.txt
        ./rr167.txt
        ./1471-2474-2-3.txt
        ./1471-2121-3-15.txt
        ./1471-2172-3-1.txt
        ./1472-6904-2-4.txt
        ./1472-6750-1-11.txt
        ./gb-2003-4-5-r30.txt
        ./gb-2002-3-9-research0051.txt
        ./1471-2415-3-3.txt
        ./gb-2002-3-9-research0045.txt
        ./gb-2001-2-8-research0030.txt
        ./bcr631.txt
        ./1472-6769-1-3.txt
        ./cc3.txt
        ./1471-2180-2-32.txt
        ./1471-2202-4-16.txt
        ./1471-2180-2-26.txt
        ./1471-2431-2-4.txt
        ./1471-2458-3-2.txt
        ./1475-9276-1-3.txt
        ./ar321.txt
        ./1471-230X-2-23.txt
        ./ar309.txt
        ./gb-2001-2-4-research0014.txt
        ./1477-7819-1-10.txt
        ./gb-2001-2-11-research0045.txt
        ./1471-2202-4-17.txt
        ./1472-6769-1-2.txt
        ./bcr618.txt
        ./gb-2002-3-7-research0035.txt
        ./gb-2001-2-8-research0031.txt
        ./1471-2148-2-17.txt
        ./1471-2229-2-4.txt
        ./1471-2350-3-12.txt
        ./gb-2002-3-9-research0044.txt
        ./1471-2377-2-6.txt
        ./1471-2474-4-4.txt
        ./1472-6904-2-5.txt
        ./1472-6823-3-1.txt
        ./1471-2474-2-2.txt
        ./rr166.txt
        ./rr172.txt
        ./1471-2156-2-7.txt
        ./1472-6785-1-5.txt
        ./bcr284.txt
        ./gb-2002-3-2-research0008.txt
        ./gb-2002-3-11-research0059.txt
        ./cc2190.txt
        ./gb-2002-3-11-research0065.txt
        ./1471-213X-3-2.txt
        ./1471-2148-3-18.txt
        ./1471-2229-3-3.txt
        ./1471-2172-4-1.txt
        ./ar795.txt
        ./1471-2164-3-15.txt
        ./cc1843.txt
        ./1471-2164-3-29.txt
        ./1471-2458-2-16.txt
        ./1475-925X-2-10.txt
        ./1472-6807-3-1.txt
        ./gb-2003-4-9-r58.txt
        ./1471-2105-4-27.txt
        ./1471-2105-3-12.txt
        ./gb-2003-4-2-r16.txt
        ./ar408.txt
        ./ar409.txt
        ./1471-2407-2-11.txt
        ./gb-2001-2-10-research0041.txt
        ./1471-2288-3-4.txt
        ./1471-2105-4-26.txt
        ./1471-230X-1-5.txt
        ./gb-2002-3-8-research0040.txt
        ./1475-925X-2-11.txt
        ./gb-2001-2-9-research0035.txt
        ./1471-2172-3-12.txt
        ./gb-2003-4-6-r37.txt
        ./1472-6750-1-8.txt
        ./1471-244X-2-9.txt
        ./gb-2002-3-12-research0085.txt
        ./1471-213X-1-1.txt
        ./1471-2164-4-21.txt
        ./cc1856.txt
        ./1471-2180-3-15.txt
        ./1471-2164-3-28.txt
        ./cc105.txt
        ./1471-2202-2-10.txt
        ./1471-2180-1-8.txt
        ./1471-2431-3-3.txt
        ./1471-2369-3-10.txt
        ./1471-213X-3-3.txt
        ./cc1498.txt
        ./1471-2377-1-2.txt
        ./1471-2350-3-7.txt
        ./gb-2002-3-2-research0009.txt
        ./bcr285.txt
        ./1475-2867-3-12.txt
        ./1471-2229-1-2.txt
        ./1471-2407-3-3.txt
        ./1472-6890-1-4.txt
        ./1471-2172-4-2.txt
        ./1471-2164-3-16.txt
        ./1471-2091-3-18.txt
        ./1471-2202-2-12.txt
        ./1471-2164-4-23.txt
        ./1471-213X-1-3.txt
        ./gb-2002-3-12-research0087.txt
        ./1471-2091-3-30.txt
        ./1471-2164-3-9.txt
        ./1471-2172-3-10.txt
        ./1471-2172-2-4.txt
        ./1471-2180-1-12.txt
        ./gb-2001-2-6-research0018.txt
        ./1472-6904-3-1.txt
        ./1472-6793-2-16.txt
        ./1472-6807-3-2.txt
        ./1476-072X-2-4.txt
        ./1471-2121-2-18.txt
        ./1471-2148-2-8.txt
        ./1471-2105-4-24.txt
        ./1471-2156-3-3.txt
        ./1471-2466-2-3.txt
        ./1471-230X-3-5.txt
        ./1471-2407-2-12.txt
        ./gb-2003-4-2-r14.txt
        ./1472-6904-1-2.txt
        ./cc1538.txt
        ./1471-2105-4-25.txt
        ./1471-2105-3-38.txt
        ./ar422.txt
        ./gb-2001-2-10-research0042.txt
        ./1471-2105-4-31.txt
        ./1472-6831-3-1.txt
        ./ar387.txt
        ./1471-230X-1-6.txt
        ./1472-6793-2-17.txt
        ./1471-2156-2-18.txt
        ./1471-2105-2-8.txt
        ./1475-925X-2-12.txt
        ./1478-7954-1-3.txt
        ./1472-6807-1-1.txt
        ./cc1882.txt
        ./1471-2164-3-8.txt
        ./1471-2180-3-9.txt
        ./gb-2002-3-12-research0079.txt
        ./1471-2091-3-31.txt
        ./gb-2002-3-12-research0086.txt
        ./1471-2164-4-22.txt
        ./1471-213X-1-2.txt
        ./1471-2202-3-8.txt
        ./1471-2458-2-6.txt
        ./1477-7827-1-48.txt
        ./1471-2229-1-3.txt
        ./1471-213X-3-4.txt
        ./cc300.txt
        ./1476-069X-1-3.txt
        ./1471-2253-1-1.txt
        ./1471-2431-3-4.txt
        ./1471-2210-2-9.txt
        ./gb-2002-3-12-research0082.txt
        ./1471-213X-1-6.txt
        ./1471-2164-4-26.txt
        ./1471-2164-3-13.txt
        ./1471-2202-2-17.txt
        ./1472-6874-3-2.txt
        ./ar778.txt
        ./ar750.txt
        ./1471-2474-3-3.txt
        ./1472-6785-2-6.txt
        ./1471-2490-3-2.txt
        ./1477-7827-1-9.txt
        ./gb-2001-2-6-research0021.txt
        ./ar624.txt
        ./1471-2121-2-21.txt
        ./1472-6920-2-3.txt
        ./ar383.txt
        ./1471-2105-3-14.txt
        ./1471-2407-2-16.txt
        ./1471-2105-3-28.txt
        ./gb-2003-4-2-r11.txt
        ./cc1529.txt
        ./1471-2407-2-17.txt
        ./1472-6815-2-3.txt
        ./ar619.txt
        ./1471-2458-2-11.txt
        ./gb-2001-2-6-research0020.txt
        ./1472-6785-2-7.txt
        ./1471-2180-1-16.txt
        ./ar745.txt
        ./1472-6890-3-2.txt
        ./cc103.txt
        ./1471-2202-2-16.txt
        ./ar792.txt
        ./gb-2002-3-12-research0083.txt
        ./1471-2180-3-13.txt
        ./1471-2210-2-8.txt
        ./1472-6793-1-8.txt
        ./1471-2458-2-3.txt
        ./1472-6750-2-21.txt
        ./1471-2431-3-5.txt
        ./1472-6882-2-10.txt
        ./1471-2350-3-1.txt
        ./gb-2002-3-11-research0062.txt
        ./1472-6882-2-5.txt
        ./gb-2002-3-11-research0060.txt
        ./1471-213X-3-7.txt
        ./cc303.txt
        ./cc1477.txt
        ./1471-2407-3-5.txt
        ./1471-2377-3-4.txt
        ./1471-2180-3-11.txt
        ./gb-2002-3-12-research0081.txt
        ./cc1852.txt
        ./1471-2164-4-25.txt
        ./1471-2091-3-22.txt
        ./1471-2202-2-14.txt
        ./1471-2164-3-10.txt
        ./1471-2164-4-19.txt
        ./cc713.txt
        ./1471-2172-3-16.txt
        ./1471-2180-1-28.txt
        ./1471-230X-1-10.txt
        ./1471-2121-2-22.txt
        ./1471-2334-2-29.txt
        ./1471-2121-3-8.txt
        ./1472-6963-1-8.txt
        ./1471-2296-3-19.txt
        ./1471-2407-2-15.txt
        ./1471-2105-3-17.txt
        ./1471-230X-3-3.txt
        ./ar430.txt
        ./1471-2156-3-4.txt
        ./1471-2466-2-4.txt
        ./1471-2296-3-18.txt
        ./1471-2105-3-16.txt
        ./1472-6920-2-1.txt
        ./1476-072X-2-3.txt
        ./gb-2003-4-9-r60.txt
        ./ar140.txt
        ./gb-2003-4-3-r17.txt
        ./1472-6793-2-11.txt
        ./1472-6823-2-2.txt
        ./1471-2180-1-29.txt
        ./1471-2172-2-3.txt
        ./1471-2407-1-6.txt
        ./1471-2091-2-9.txt
        ./1471-2202-2-15.txt
        ./1471-2091-3-23.txt
        ./1471-2164-4-24.txt
        ./1471-213X-1-4.txt
        ./gb-2002-3-12-research0080.txt
        ./1471-2180-3-10.txt
        ./cc1476.txt
        ./1471-2407-3-4.txt
        ./1471-2431-3-6.txt
        ./bcr294.txt
        ./gb-2002-3-11-research0061.txt
        ./1477-7827-1-43.txt
        ./1475-2832-1-1.txt
        ./1471-2199-3-12.txt
        ./1471-2202-1-1.txt
        ./1472-6750-2-13.txt
        ./cc2172.txt
        ./1472-6793-1-6.txt
        ./1471-2210-2-6.txt
        ./1471-213X-1-9.txt
        ./1471-2164-3-34.txt
        ./1471-2164-4-15.txt
        ./1471-2202-3-3.txt
        ./1471-2202-2-18.txt
        ./cc2358.txt
        ./1472-6793-3-4.txt
        ./gb-2002-3-12-research0072.txt
        ./1472-6963-3-11.txt
        ./1472-6963-3-6.txt
        ./1476-4598-2-3.txt
        ./1477-7827-1-6.txt
        ./1475-4924-1-10.txt
        ./1472-6874-2-13.txt
        ./1471-2369-4-5.txt
        ./1471-2121-3-4.txt
        ./1471-2121-2-12.txt
        ./1471-2148-2-2.txt
        ./1475-925X-2-6.txt
        ./1471-2148-1-14.txt
        ./1471-2407-2-19.txt
        ./1471-2210-2-14.txt
        ./1475-2867-3-4.txt
        ./ar429.txt
        ./1471-2407-2-31.txt
        ./1471-2105-3-26.txt
        ./1477-7525-1-12.txt
        ./1471-2407-2-18.txt
        ./1471-2105-4-13.txt
        ./gb-2003-4-1-r5.txt
        ./1471-2334-2-24.txt
        ./1471-2318-3-2.txt
        ./1471-2156-2-12.txt
        ./1471-2180-1-31.txt
        ./1476-4598-2-2.txt
        ./1472-684X-2-1.txt
        ./1471-5945-3-3.txt
        ./1472-6963-3-7.txt
        ./1475-2891-2-1.txt
        ./1471-2091-2-5.txt
        ./1472-6793-3-5.txt
        ./1475-4924-1-5.txt
        ./1471-2202-2-19.txt
        ./1471-2091-3-13.txt
        ./1471-2164-4-14.txt
        ./1471-2164-3-35.txt
        ./1471-2164-4-28.txt
        ./cc2167.txt
        ./bcr273.txt
        ./1477-7827-1-54.txt
        ./1471-2334-2-1.txt
        ./1471-2199-3-11.txt
        ./1472-6750-2-10.txt
        ./1471-2210-2-5.txt
        ./cc2171.txt
        ./1471-2164-3-23.txt
        ./1471-2164-4-16.txt
        ./ar774.txt
        ./1476-511X-1-2.txt
        ./1472-6963-3-12.txt
        ./1471-2091-2-7.txt
        ./1471-2180-1-33.txt
        ./gb-2000-1-1-research002.txt
        ./gb-2001-3-1-research0005.txt
        ./bcr45.txt
        ./1471-2091-4-1.txt
        ./gb-2003-4-1-r7.txt
        ./1471-2334-2-26.txt
        ./1471-2121-2-11.txt
        ./1471-5945-1-3.txt
        ./1471-2105-3-18.txt
        ./1471-2261-3-5.txt
        ./1471-2105-3-24.txt
        ./1476-5918-1-2.txt
        ./1477-7525-1-10.txt
        ./gb-2002-3-5-research0024.txt
        ./1471-2105-3-30.txt
        ./1471-2407-2-33.txt
        ./gb-2002-3-5-research0025.txt
        ./1471-2261-3-4.txt
        ./1471-2199-3-3.txt
        ./1471-2121-2-10.txt
        ./1471-2121-3-6.txt
        ./1471-2334-2-27.txt
        ./gb-2001-3-1-research0004.txt
        ./1471-2261-1-6.txt
        ./gb-2003-4-3-r18.txt
        ./ar615.txt
        ./ar601.txt
        ./1476-4598-2-1.txt
        ./1472-684X-2-2.txt
        ./1471-2180-1-26.txt
        ./1471-2458-2-21.txt
        ./1472-6793-3-6.txt
        ./1472-6963-3-13.txt
        ./1471-2164-3-1.txt
        ./1471-2202-3-1.txt
        ./1471-2210-2-4.txt
        ./1471-2199-3-10.txt
        ./1471-2350-2-12.txt
        ./1471-2350-3-9.txt
        ./1475-9268-1-1.txt
        ./gb-2001-2-2-research0004.txt
        ./cc2160.txt
        ./1472-6750-3-4.txt
        ./1471-2202-3-5.txt
        ./1471-2164-4-13.txt
        ./1471-2091-3-14.txt
        ./1471-5945-2-13.txt
        ./1471-2164-3-32.txt
        ./1471-2164-3-26.txt
        ./1471-2288-2-11.txt
        ./1471-2180-3-4.txt
        ./1472-6750-1-6.txt
        ./gb-2003-4-6-r39.txt
        ./1471-2458-2-25.txt
        ./gb-2003-4-3-r20.txt
        ./gb-2003-4-9-r57.txt
        ./1471-2121-3-2.txt
        ./1471-2407-2-23.txt
        ./1471-2105-4-28.txt
        ./1472-6947-2-7.txt
        ./gb-2002-3-5-research0021.txt
        ./ar407.txt
        ./1471-2199-3-7.txt
        ./1475-2867-3-2.txt
        ./1475-925X-2-1.txt
        ./1475-2867-3-3.txt
        ./1471-2105-3-34.txt
        ./gb-2002-3-5-research0020.txt
        ./1471-2407-2-22.txt
        ./1471-2121-2-15.txt
        ./1471-2148-2-5.txt
        ./cc1044.txt
        ./1471-2091-4-5.txt
        ./1471-2288-1-9.txt
        ./rr37.txt
        ./gb-2001-3-1-research0001.txt
        ./1472-6963-3-1.txt
        ./1471-2172-2-9.txt
        ./1471-2458-2-18.txt
        ./1471-2180-3-5.txt
        ./1471-2288-2-10.txt
        ./1471-2164-3-4.txt
        ./1472-6793-3-3.txt
        ./gb-2002-3-12-research0075.txt
        ./1471-2164-3-27.txt
        ./1471-2164-3-33.txt
        ./1471-2091-3-15.txt
        ./1471-2202-3-4.txt
        ./1472-6750-2-14.txt
        ./1471-2180-1-7.txt
        ./cc1497.txt
        ./1471-2334-2-5.txt
        ./1471-2199-3-17.txt
        ./1471-2350-2-11.txt
        ./1471-2334-2-7.txt
        ./cc1495.txt
        ./1475-9268-1-2.txt
        ./1477-7827-1-46.txt
        ./1471-2091-3-17.txt
        ./ar799.txt
        ./1471-2164-3-19.txt
        ./gb-2002-3-12-research0088.txt
        ./1471-2164-3-31.txt
        ./gb-2002-3-12-research0077.txt
        ./1472-6963-3-14.txt
        ./1475-2875-1-14.txt
        ./1471-2164-3-6.txt
        ./gb-2003-4-8-r51.txt
        ./1475-2875-2-4.txt
        ./1472-6963-1-11.txt
        ./ar612.txt
        ./1472-6793-2-19.txt
        ./1471-230X-1-8.txt
        ./1471-2148-2-7.txt
        ./gb-2002-3-5-research0022.txt
        ./1471-2288-3-9.txt
        ./1471-2105-3-22.txt
        ./1472-6947-2-4.txt
        ./bcr317.txt
        ./1475-925X-2-3.txt
        ./bcr303.txt
        ./1471-2105-3-23.txt
        ./1471-2288-3-8.txt
        ./bcr458.txt
        ./1471-2105-3-37.txt
        ./gb-2002-3-5-research0023.txt
        ./1472-6793-2-18.txt
        ./1471-2156-2-17.txt
        ./1471-2369-4-1.txt
        ./ar149.txt
        ./gb-2002-3-6-research0029.txt
        ./1471-2121-1-2.txt
        ./1471-2180-1-34.txt
        ./gb-2003-4-8-r50.txt
        ./1471-2164-3-7.txt
        ./1471-2164-3-30.txt
        ./1471-2202-2-20.txt
        ./1471-2164-3-24.txt
        ./1471-2202-3-7.txt
        ./1471-2091-3-16.txt
        ./1471-2164-3-18.txt
        ./1472-6750-3-6.txt
        ./1472-6793-1-2.txt
        ./1471-2334-2-6.txt
        ./1471-213X-1-15.txt
        ./cc350.txt
        ./1471-2148-3-1.txt
        ./bcr588.txt
        ./1471-2199-2-2.txt
        ./1475-2867-2-7.txt
        ./1468-6708-3-4.txt
        ./1471-2121-3-25.txt
        ./1471-2334-3-12.txt
        ./1471-2202-4-6.txt
        ./1472-6882-1-10.txt
        ./1471-2121-3-19.txt
        ./1471-2164-4-6.txt
        ./1471-2229-2-9.txt
        ./gb-2002-3-9-research0049.txt
        ./1471-2334-1-17.txt
        ./1471-2180-2-1.txt
        ./cc973.txt
        ./1471-2210-1-7.txt
        ./1471-2326-2-4.txt
        ./1471-2180-2-16.txt
        ./1471-2121-4-1.txt
        ./1471-213X-2-8.txt
        ./1472-6793-1-12.txt
        ./1471-2199-4-4.txt
        ./1471-2199-4-5.txt
        ./1471-2369-3-1.txt
        ./1471-2164-2-1.txt
        ./1471-2202-2-1.txt
        ./gb-2002-3-9-research0048.txt
        ./1471-2229-2-8.txt
        ./1471-2474-4-8.txt
        ./1471-2121-3-18.txt
        ./1472-6882-1-11.txt
        ./1471-2334-3-13.txt
        ./cvm-2-1-038.txt
        ./1471-2121-3-30.txt
        ./1471-2156-4-10.txt
        ./1471-2199-2-3.txt
        ./1476-4598-1-3.txt
        ./1471-2172-2-10.txt
        ./1471-2121-2-6.txt
        ./1477-7827-1-21.txt
        ./1477-7827-1-23.txt
        ./1475-2891-1-2.txt
        ./1468-6708-3-7.txt
        ./1471-2199-2-1.txt
        ./1471-2105-1-1.txt
        ./gb-2002-3-10-research0052.txt
        ./1471-2202-4-5.txt
        ./1471-2334-3-11.txt
        ./grep-results-numbered.txt
        ./1471-2164-4-5.txt
        ./cvm-2-6-278.txt
        ./cvm-2-4-180.txt
        ./1471-2105-3-3.txt
        ./gb-2003-4-2-r9.txt
        ./1475-2883-2-11.txt
        ./1475-2867-2-10.txt
        ./1471-2202-2-3.txt
        ./bcr602.txt
        ./1471-2180-2-2.txt
        ./gb-2001-2-12-research0055.txt
        ./1478-1336-1-4.txt
        ./1472-6793-2-4.txt
        ./1471-2210-1-4.txt
        ./1471-2091-3-4.txt
        ./1471-2121-4-2.txt
        ./gb-2002-3-4-research0019.txt
        ./1471-2202-3-10.txt
        ./1471-2180-2-29.txt
        ./1472-6750-2-2.txt
        ./1476-511X-2-3.txt
        ./cc1547.txt
        ./1472-6793-1-11.txt
        ./1471-2407-2-9.txt
        ./1471-2407-2-8.txt
        ./1476-4598-2-28.txt
        ./1476-511X-2-2.txt
        ./1471-2202-3-11.txt
        ./1471-2121-4-3.txt
        ./gb-2002-3-4-research0018.txt
        ./1471-2261-2-11.txt
        ./1472-6793-2-5.txt
        ./1471-2164-2-2.txt
        ./gb-2001-2-12-research0054.txt
        ./ar104.txt
        ./1471-2407-1-15.txt
        ./1471-2202-2-2.txt
        ./gb-2003-4-2-r8.txt
        ./1472-6947-1-2.txt
        ./1471-2105-3-2.txt
        ./1471-2229-2-11.txt
        ./1471-2164-4-4.txt
        ./cvm-2-6-286.txt
        ./1471-2148-1-1.txt
        ./1471-2334-3-10.txt
        ./1472-6882-1-12.txt
        ./gb-2002-3-10-research0053.txt
        ./1471-2156-2-8.txt
        ./rr196.txt
        ./1471-2148-3-3.txt
        ./1472-6807-2-9.txt
        ./1477-7827-1-36.txt
        ./1471-2148-3-7.txt
        ./1471-213X-1-13.txt
        ./1471-2121-2-1.txt
        ./gb-2002-3-3-research0012.txt
        ./1471-2156-3-22.txt
        ./bcr571.txt
        ./1471-2199-2-4.txt
        ./gb-2000-1-2-research0003.txt
        ./1472-6955-2-1.txt
        ./1471-2474-3-23.txt
        ./1472-6947-1-6.txt
        ./1471-2407-3-14.txt
        ./1471-2202-2-6.txt
        ./1475-2867-2-15.txt
        ./1472-6793-2-1.txt
        ./gb-2002-3-8-research0039.txt
        ./1471-2369-3-6.txt
        ./bcr607.txt
        ./1472-6874-2-8.txt
        ./1471-2180-2-7.txt
        ./1471-2164-2-6.txt
        ./1471-2180-2-38.txt
        ./1471-2210-3-3.txt
        ./1471-2431-2-11.txt
        ./1472-6793-1-15.txt
        ./1471-2458-3-9.txt
        ./1471-2121-4-6.txt
        ./1471-2202-3-14.txt
        ./1471-2164-2-7.txt
        ./gb-2001-2-12-research0051.txt
        ./gb-2002-3-8-research0038.txt
        ./1471-244X-3-5.txt
        ./1471-2202-2-7.txt
        ./1471-2334-1-10.txt
        ./1471-2407-3-15.txt
        ./1471-2121-3-22.txt
        ./1471-2334-3-15.txt
        ./1471-2148-1-4.txt
        ./1471-2199-2-5.txt
        ./1468-6708-3-3.txt
        ./bcr570.txt
        ./gb-2002-3-10-research0056.txt
        ./1472-6947-3-5.txt
        ./cc343.txt
        ./1471-213X-1-12.txt
        ./1471-2296-3-3.txt
        ./1477-7827-1-27.txt
        ./1476-4598-1-5.txt
        ./rr191.txt
        ./1471-2148-3-4.txt
        ./1471-2458-3-11.txt
        ./1475-2875-1-5.txt
        ./1477-7827-1-31.txt
        ./1471-213X-1-10.txt
        ./gb-2002-3-3-research0011.txt
        ./gb-2002-3-10-research0054.txt
        ./1468-6708-3-1.txt
        ./1471-2148-1-6.txt
        ./1471-2202-4-3.txt
        ./1472-6947-1-5.txt
        ./1471-2202-2-5.txt
        ./1476-9433-1-2.txt
        ./1471-2210-1-2.txt
        ./1471-2458-1-9.txt
        ./1472-6793-2-2.txt
        ./gb-2001-2-12-research0053.txt
        ./1478-1336-1-2.txt
        ./1471-2202-3-16.txt
        ./1471-2180-2-13.txt
        ./1471-2121-4-4.txt
        ./gb-2003-4-4-r28.txt
        ./1471-230X-2-17.txt
        ./1477-5956-1-1.txt
        ./1471-2156-4-9.txt
        ./1471-2431-2-12.txt
        ./ar328.txt
        ./1471-2210-3-1.txt
        ./1471-2121-4-5.txt
        ./1471-2350-2-8.txt
        ./1471-2202-3-17.txt
        ./1471-2407-1-13.txt
        ./bcr605.txt
        ./1476-069X-2-9.txt
        ./1478-1336-1-3.txt
        ./1471-2164-2-4.txt
        ./1471-2210-1-3.txt
        ./1476-9433-1-3.txt
        ./1471-2334-1-13.txt
        ./1471-2407-3-16.txt
        ./1471-2164-4-2.txt
        ./cvm-2-4-187.txt
        ./1471-2121-3-21.txt
        ./1471-2202-4-2.txt
        ./1471-2172-3-9.txt
        ./gb-2001-2-3-research0007.txt
        ./1471-2199-2-6.txt
        ./bcr567.txt
        ./gb-2002-3-10-research0055.txt
        ./1471-2121-2-3.txt
        ./1471-213X-1-11.txt
        ./1472-684X-1-5.txt
        ./1476-4598-1-6.txt
        ```
    * example 2: 
      * ```
        allisonwang@Allisons-MacBook-Pro 911report % grep -r -L ".txt"
        ```
      * ```
        ./chapter-13.4.txt
        ./chapter-13.5.txt
        ./chapter-13.1.txt
        ./chapter-13.2.txt
        ./chapter-13.3.txt
        ./chapter-3.txt
        ./chapter-2.txt
        ./chapter-1.txt
        ./chapter-5.txt
        ./chapter-6.txt
        ./chapter-7.txt
        ./chapter-9.txt
        ./chapter-8.txt
        ./preface.txt
        ./chapter-12.txt
        ./chapter-10.txt
        ./chapter-11.txt
        ```
    * The -L command does the opposite of the -l command and prints out the names of all the files that don't contain the key phrase rather than printing out every single time the phrase comes up in any of the files. This is useful because it gives the information about which of the files don't contain the key phrase, which could later be useful as a count of how many files don't have the key phrase among other things. 
  * -n
    * example 1: 
      * ```
        allisonwang@Allisons-MacBook-Pro 911report % find . -name "*.txt" > all-txt-files-911.txt
        allisonwang@Allisons-MacBook-Pro 911report % grep -r -n ".txt" all-txt-files-911.txt
        ```
      * ```
        all-txt-files-911.txt:1:./chapter-13.4.txt
        all-txt-files-911.txt:2:./chapter-13.5.txt
        all-txt-files-911.txt:3:./chapter-13.1.txt
        all-txt-files-911.txt:4:./chapter-13.2.txt
        all-txt-files-911.txt:5:./chapter-13.3.txt
        all-txt-files-911.txt:6:./chapter-3.txt
        all-txt-files-911.txt:7:./chapter-2.txt
        all-txt-files-911.txt:8:./chapter-1.txt
        all-txt-files-911.txt:9:./chapter-5.txt
        all-txt-files-911.txt:10:./chapter-6.txt
        all-txt-files-911.txt:11:./chapter-7.txt
        all-txt-files-911.txt:12:./chapter-9.txt
        all-txt-files-911.txt:13:./chapter-8.txt
        all-txt-files-911.txt:14:./preface.txt
        all-txt-files-911.txt:15:./chapter-12.txt
        all-txt-files-911.txt:16:./chapter-10.txt
        all-txt-files-911.txt:17:./chapter-11.txt
        all-txt-files-911.txt:18:./all-txt-files-911.txt
        ```
    * example 2:
      * ```
        allisonwang@Allisons-MacBook-Pro biomed % grep -r -n ".txt" gb-2001-2-9-research0037.txt
        ```
      * ``` 
        gb-2001-2-9-research0037.txt:762:          hyb2dis.txt in additional data files). More importantly,
        gb-2001-2-9-research0037.txt:814:        hyb2dis.txt: patch file that converts White's hybridize
        gb-2001-2-9-research0037.txt:816:        Training sets(GlycineMedicago.txt,Rhizobia.txt,
        gb-2001-2-9-research0037.txt:817:        Stramenopiles.txt, ZygoChytrid.txt): FASTA-formatted text
        gb-2001-2-9-research0037.txt:820:        Test sets(PsojaeHA.txt, PsojaeMY.txt, PsojaeZO.txt,
        gb-2001-2-9-research0037.txt:821:        MtRHE.txt, DSIR.txt, MHAM.txt, KV0.txt, KV2.txt, KV3.txt):
        gb-2001-2-9-research0037.txt:834:        hyb2dis.txt
        gb-2001-2-9-research0037.txt:838:        hyb2dis.txt
        gb-2001-2-9-research0037.txt:843:        GlycineMedicago.txt
        gb-2001-2-9-research0037.txt:844:        Rhizobia.txt
        gb-2001-2-9-research0037.txt:845:        Stramenopiles.txt
        gb-2001-2-9-research0037.txt:846:        ZygoChytrid.txt
        gb-2001-2-9-research0037.txt:851:        PsojaeHA.txt
        gb-2001-2-9-research0037.txt:852:        PsojaeMY.txt
        gb-2001-2-9-research0037.txt:853:        PsojaeZO.txt
        gb-2001-2-9-research0037.txt:854:        MtRHE.txt
        gb-2001-2-9-research0037.txt:855:        DSIR.txt
        gb-2001-2-9-research0037.txt:856:        KV0.txt
        gb-2001-2-9-research0037.txt:857:        KV2.txt
        gb-2001-2-9-research0037.txt:858:        KV3.txt
        ```
    * The -n command places the line number next to each of the lines that have the the key phrase in them. This is useful if you want to know the line number of the occurences of the key phrase as well as improving readability if you use it on a file that contains all files within certain keyword in their name like what I did in the first example.      