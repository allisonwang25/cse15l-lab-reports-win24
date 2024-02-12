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
      * ```java
        grep -r ".txt"
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
    

  
