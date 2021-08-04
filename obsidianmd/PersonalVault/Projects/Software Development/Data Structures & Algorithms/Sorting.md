---
source: https://www.cs.usfca.edu/~galles/visualization/Algorithms.html
source: https://www.bigocheatsheet.com/ 
---
# Sorting
## Stable vs Unstable Sorting Algorithms
![[Pasted image 20210707160109.png]]
source: wikipedia
### What are stable algorithms?
### Why is stability of sorting algorithms important?
1. When we want to sort based on more than one criteria/attribute/field/column
	- Example:
		- Score and time of submission
			- If scores are tied than time of submission is priority 
		- Two columns in excel spreadsheet Names and Country
			- We want to sort by Country and Names. Country takes priority
				- This is can only be achieved via stable sort
2. Stable sorting is used as a subroutine for __Radix Sort__
	- Example:
		- __Counting Sort__, a stable algorithm, is used for __Radix Sort__
		- __Radix Sort__
			- Apply __Counting Sort__ on a list of integers by their digits backwards
			- ![[Pasted image 20210707180605.png]] 
			- source: https://www.youtube.com/watch?v=KJuxI1BBLyQ
			- If the same

## Merge Sort
__Recursive Merge Sort__

Time: 

Space:

```java
public static void mergesort(int[] a) {
	mergesort(a, new int[a.length], 0, a.length - 1);
}

private static void mergesort(int[] a, int[] temp, int low, int high) {
	if (high - low <= 0) return;
	int mid = low + (high - low) / 2;
	mergesort(a, temp, low, mid);
	mergesort(a, temp, mid + 1, high);
	merge(a, temp, low, mid, high);
}

private static void merge(int[] a, int[] temp, int low, int middle, int high) {
	int i = low, k = low, j = middle + 1;
	
	while (i <= midle && j <= high) {
		if (a[i] < a[j]) temp[k++] = a[i++];
		else temp[k++] = a[j++];
	}
	
	while (i <= middle)  temp[k++] = a[i++];
	while (j <= high) temp[k++] = a[j++];
	
	for (i = low; i <= high; i++) a[i] = temp[i];
}
```

## Insertion

__Iterative Insertion Sort__

```java
public void insertionSort(int[] a) {
	for (int i = 1; i < a.length; i++) {
		int temp = a[i], j = i;
		while (j > 0 && a[j - 1] > temp) {
			a[j] = a[j - 1];
			j--;
		}
		a[j] = temp;
	}
}
```

## Heap Sort

__Recursive Heap Sort__

```java
public static void heapSort(int[] a) { // maxHeap needed to sortin in ascending order
	if (a == null || a.length <= 1) return;
	
	for (i = (n / 2) - 1; i >= 0; i--) siftDown(a, n, i); // build max heap
	
	for (i = a.length - 1; i >= 1; i--) {
		swap(a, 0, i);
		siftDown(a, i, 0);
	}
}

public static void siftDown(int[] a, int end, int i) {
	int k = i;
	
	int left = 2 * i + 1;
	int right = 2 * i + 2;
	
	if (left < end && a[left] > a[k]) k = left;
	if (right < end && a[right] > a[k]) k = right;
	
	if (k != i) {
		swap(a, k, i);
		siftDown(a, end, k)
	}
}
```