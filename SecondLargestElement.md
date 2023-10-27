# Second Largest or Second Smallest Element in an  array

## Brute Approach

### Intution 
  If we sort the array the  smallest element will lie in the first index of the array and largest element will move to the last, then we can print the 1st index to get the second smallest element and second last index to get the second largest element of the array.

### Code
``` java 
public class Solution {
	public static void main(String args[]) {
		int arr[] = {2,4,6,5,2,3};

    Arrays.sort(arr); // this will push the smallest element to the first and largest element to the end of the array

    System.out.println(arr[1]); //second smallest element
		System.out.println(arr[1]); // second largest element
		
	}
}
```

Time Complexity: O(n*log n)

Space Complexity: O(1)


## Better Approach - I

### Intution 
Assuming   
### Code
``` java 
public class Solution {
	
	public static int findSecondLargestorSmallest(int arr[]) {
		int largest = Integer.MIN_VALUE;   //store the minimum value that can exist
		int second_largest = Integer.MIN_VALUE;
		
		int smallest = Integer.MAX_VALUE;   //stores the maximum value that can exist
		int second_smallest = Integer.MAX_VALUE;
		
		for(int i=0; i<arr.length; i++) {
			if(arr[i]>largest) {
				largest = arr[i];
			}
			if(arr[i]<smallest) {
				smallest = arr[i];
			}
		}

		for(int i=0;i<arr.length; i++) {
			if(arr[i]>second_largest && arr[i]!= largest) {
				second_largest = arr[i];
			}
			if(arr[i]<second_smallest && arr[i]!= smallest) {
				second_smallest = arr[i];
			}
		}
		System.out.println(second_smallest);
		return second_largest;
	}
	
	public static void main(String args[]) {
		int arr[] = {2,4,6,5,2,3};
		
		System.out.print(findLargest(arr));
	}
}
``` 

Time Complexity: O(2N)

Space Complexity: O(1)

## Better Approach - II

### Intution 
Assuming   
### Code
``` java 
public class Solution {
	
	public static int findSecondLargest(int arr[]) {
		int largest = Integer.MIN_VALUE;
		int second_largest = Integer.MIN_VALUE;
		int smallest = Integer.MAX_VALUE;
		int second_smallest = Integer.MAX_VALUE;
		
		for(int i=0; i<arr.length; i++) {
			largest = Math.max(largest, arr[i]);
			smallest = Math.max(smallest, arr[i]);
		}
		
		for(int i=0; i<arr.length; i++) {
			if(arr[i]>second_largest && arr[i]!= largest) {
				second_largest = arr[i];
			}
			if(arr[i]<second_smallest && arr[i]!=smallest) {
				second_smallest = arr[i];
			}
		}
		System.out.println(second_smallest);
		return second_largest;
	}
	
	public static void main(String args[]) {
		int arr[] = {2,4,6,5,2,3};
		
		System.out.print(findLargest(arr));
	}
}
``` 

Time Complexity: O(2N)

Space Complexity: O(1)
