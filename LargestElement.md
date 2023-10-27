# Largest Element in an  array

## Brute Approach

### Intution 
  If we sort the array the largest element will move to the last of the array, then we can print the last index element to get the largest element.

### Code
``` java 
public class Solution {
	
	public static int findLargest(int arr[]) {
		Arrays.sort(arr); // this will push the largest element to the end
		return arr[arr.length-1];  // return the last index element
	}
	
	public static void main(String args[]) {
		int arr[] = {2,4,6,5,2,3};
		
		System.out.print(findLargest(arr));
	}
}
```


## Recursive Approach

### Intution 
 Assume first element as the largest element then perform linear search to find out element greater than the the current largest element or not---if yes then the update the value of largest element--return it
 
### Code
``` java 
public class Solution {
	
	public static int findLargest(int arr[]) {
		int largest = arr[0];  // assuming the first index element is the largest one

		for(int i=0; i<arr.length; i++) {  // linear search to find element grater than largest or not
			if(arr[i]>largest) {
				largest = arr[i]; // updating largest 
			}
		}
		return largest;
	}
	
	public static void main(String args[]) {
		int arr[] = {2,4,6,5,2,3};
		
		System.out.print(findLargest(arr));
	}
}
``` 
