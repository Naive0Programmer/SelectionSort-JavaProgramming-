# Selection Sort (Java Programming)

The selection sort algorithm sorts an array by looping through an array, finding the smallest element (considering ascending order) from unsorted part and putting it at the start of the array. 

Has the worst case and average complexity of $O(n^2)$

For more information ([geeksforgeeks](https://www.geeksforgeeks.org/selection-sort/))

```java
import java.util.Arrays;

public class Sort {
	public static int array[] = { 20, 25, 30, 199, 22, 15, 88, 60, 45, 37, 21, 6, 73, 8, 20, 25, 30, 11, 23, 13, 104,
			60, 46, 38, 24, 77, 2, 1, 29, 27, 32, 18, 31, 14, 66, 60, 48, 33, 24, 7, 3, 9 };

	public static int[] selectionSort(int[] array) {
		int len = array.length;
		for(int i = 0; i < len-1;i++) {
			int min = i;
			for(int j = i+1 ; j<len;j++) {
				if(array[j] < array[min]) {
					int minValue = array[j];
					array[j] = array[min];
					array[min] = minValue;
				}
			}
		}
		return array;
	}

	public static void main(String args[]) {
		System.out.println("Original: 	" + Arrays.toString(array));
		float start = System.currentTimeMillis();
		int myNewArray[] = Sort.selectionSort(array);
		System.out.println("Sorted:		" + Arrays.toString(myNewArray));
		float done = System.currentTimeMillis() - start;
		System.out.println("Time: " + done);
	}
}
```

