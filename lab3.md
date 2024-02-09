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
  
