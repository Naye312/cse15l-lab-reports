### Lab Report 3 
#### Part 1 - Bugs
We are going to choose the bug with the reverse methods in `ArrayExamples.java`, specifically the method `reverseInPlace`.

1. The failure inducing input. 
   ```
   public void testReverseInPlace() {
    int[] input1 = {1,2,3};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{3,2,1}, input1);
	}
   ```
2. The input without failure
   ```
	public void testReverseInPlace() {
    int[] input1 = { };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ }, input1);
	}
   ```
3. ![Image](Fail.png)

   ![Image](Success.png)
4. Before and after code fixing the bug
   ```
   static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
   }
   ```
   ```
   static void reverseInPlace(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    for(int i = 0; i < arr.length; i++){
      arr[i] = newArray[i];
    }
   }
   ```   
5. The bug is fixed by adding a new variable called newArray. The reason this works is because if we just try to change the original variable directly by calling itself, it will not have the original values anymore and thus not know what numbers to actually reverse. (e.g if we started with 1,2,3, the method will swap 1 with 3 but then the original just becomes 3,2,3 and thus the method gets confused since it'll start referencing 3,2,3 instead of 1,2,3 as intended). 

#### Part 2 - Researching Commands
