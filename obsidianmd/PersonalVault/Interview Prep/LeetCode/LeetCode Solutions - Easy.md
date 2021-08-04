# Leet Code Solutions - Easy
## HINTS:
- __Always come with brute force and then optimize that__
- __Other ways: sorting, maps, sets__
# Array Qs
## Rotate Array
## Contains Duplicates
__Given an array of integers, find if the array contains any duplicates.__

Hint: O(n^2) > O(nlgn) > O(n). TIME-SPACE TRADE OFF
- Approach 1: Brute force. O(n^2), O(1)
	- Loop through all n integers. For the ith integer nums[i], we search in previous i -1 integers for the duplicate of nums[i]. If we find one, we return true; if not, we continue until we reach the end of the array. Return false at the end of the program.
	 ```java
		public boolean containsDuplicate(int[] nums) {
			for (int i = 0; i < nums.length - 1; i++) {
				for (int j = i + 1; i < nums.length; j++) {
					if (nums[i] == nums[j]) return true;
				}
			}
			return false;
		}
	 ```

- Approach 2: Sorting. O(nlgn), O(n) b/c of TimSort
	- __Intuition: if there are any duplicate integers, they will be consecutive after sorting. __
	- This approach employs sorting algorithm. Java’s built in Arrays.sort() uses a modified merge sort, Timsort, that provides O(nlgn) performance. After sorting, we can sweep the sorted array to find if there are any two consecutive duplicate elements.
	```java
		public boolean containsDuplicate(int[] nums) {
			Arrays.sort(nums);
			for (int i = 0; i < nums.length - 1; i++) {
				if (nums[i] == nums[i + 1]) return true;
			}
			return false;
		}
	```

- Approach 3: Hash Set. O(n), O(n)
	```java
		public boolean containsDuplicate(int[] nums) {
			HashSet<Integer> set = new HashSet<>(nums.length);
			for (int i = 0; i < nums.length; i++) {
				if (!set.add(nums[i])) return true;
			}
			return false;
		}
	```

## Single or Odd Number
__Given a non-empty array of integers, every element appears twice (or an even #  of times) except for one. Find that single one.__

- Approach 1: Brute Force. O(n^2), O(1)
	- **Check every element with every other to find the one that does not have a match.**
	```java
		public int singleNumber(int[] nums) {
			boolean foundMatch = false;
			for (int i = 0; i < nums.length - 1; i++) {
				for (int j = i + 1; j < nums.length; j++) {
					if (nums[i] == nums[j])  { foundMatch = true; break; }
				}
				if (!foundMatch) return nums[i];
			}
			return false;
		}	
	```

- Approach 2: Sorting. O(nlgn), O(n)
	- Sort the array using Arrays.sort(). Then, find the element that does not equal nums[i] != nums[i + 1]

- Approach 3: HashMap. O(n), O(n)
	- Generate a frequency table and get a set of all the keys in the table iterate over the key-value pairs. and if the value is = 1, return key.

- Approach 4: HashSet: O(n), O(n)
- Add and remove the elements as you go. If the element is not in the hashtable added. If it already exists, remove it. At the end, you’ll be left with the single one element.

## Fibonacci Sequence
## Two Sum
## Move Zeroes
## Intersection of Two Array
## Plus One
## Valid Sudoku


# String Qs 

## Reverse String
__Write a function that makes a string as input and returns the string as reversed__. Ex: "hello" > "olleh"

- Approach 1: Swap Using Pointers. O(n), O(n)
	- One pointer is pointing at the start of the string while the other pointer is pointing at the end of the string. Both pointers will keep swapping its elements and travel towards each other.
	```java
		public String reverseString(String s) {
			char[] str = s.toCharArray();
			int i = 0, j = s.length() - 1;
			while (i < j) {
				char tmp = str[i];
				str[i++] = str[j];
				str[j++] = temp;
			}
			return new String(str);
		}
	```

- Approach 2: Build StringBuilder backwards traversal of string
- Approach 3: Recursive

## Reverse Integer
__Given a 32-bit signed integer, reverse digits of an integer. Assume an environment that stores integers within 32-bit signed integer range__ Ex: [- (2^31) - (2^31) - 1]

- Approach 1: 
	- Intuition, we can build up the reverse integer one digit at a time. While doing so, we can check beforehand whether or not appending another digit would cause an overflow.
	```java
		public int reverse(int x) {
			int rev = 0;
			while (x != 0) {
				int digit = x % 10;
				x /= 10;
				if (rev > Integer.MAX_VALUE / 10 || (rev == Integer.MAX_VALUE / 10 && digit > 7)) return 0;
				if (rev < Integer.MIN_VALUE / 10 || (rev == Integer.MIN_VALUE / 10 && digit < -8)) return 0;
				rev = (10 * rev) + digit;
			}
		}
	```
	

## First Unique Char in a String
__Given a string, find the first non-repeating char and return its index. If not, return -1. Assume the string contains only lowercase letters.__

- 

## Valid Anagram 
## Valid Palindrome
## String to Integer (atoi)
## Longest Common Prefix

# Linked Lists (LL)
## Reverse a Linked List
__Given a pointer to the head of a linked list, reverse the list and return the head.__

- Approach 1: Iterative
```java
	public Node reverse(Node head) {
		Node prev = null, current = node, next = null;
		while (current ! = null) {
			next = current.next;
			current.next = prev;
			prev = current;
			current = next;
		}
		head = prev;
		return head;
	}
```

- Approach 2: Recursive
```java
	public Node reverse(Node head) {
		if (head == null || head.next = null) return head;
		Node rest = reverse(head.next); // put first element at end
		head.next.next = head; 
		head.next = null;
		return rest;
	}
```

- Approach 3: Stack

- Approach 4; Array
## Delete Middle Node
__Delete a node (except the tail) in a singly linked list, given only access to that node.__

- Approach 1: Overwrite the current value with next node.
	- The usual way of deleting a node from a linked list is to modify the next pointer of the node before it to point to the node after the current node. Since, we do not have access to the previous node, we cannot modify the next pointer of that node. Instead, overwrite the data value of the current node (node to be deleted) with the value of the node after it. Then, delete the node next node. NOTE: since the node we want to delete will not be tail of the list, we can guarantee that is approach will work for nodes between the head & tail (exclusive).
	```java
		public boolean deleteNode(ListNode node) {
			if (node == null || node.next == null) return false;
			node.val = node.next.val;
			node.next = node.next.next;
			return true;
		}
	```

## Remove Kth to Last Node
__Given a linked list, remove the kth node from the end of the list and return its head.__

- Approach 1:
	- Intuition and alternative problem is to remove the (n - k +1)th node from the beginning of list 1-based indexing. N is the length of the list. Create a auxiliary node, which points to the list head to simplify corner cases such as a list with one node or removing the head of the list. On the first pass, find the length of list. Then, we set a pointer to the auxiliary node and start to move it through the list till it comes to the (n - k)th node. Then, next pointer of (n-k)th node will point to the (n-k+2)th node.
	```java
		public ListNode removeNthFromEnd(ListNode head, int k) {
			int n = 0;
			ListNode current = head;
			while (current != null) { // get size of list
				len++; current = current.next;
			}
			// delete node
			n -= k;
			current = head;
			while (n > 0) {
				n--;
				current = current.next;
			}
			current.next - current.next.next;
			return head;
		}
	```
		
- Approach 2:
	- 


## Reverse LL
## Merge Two Sorted Lists
## Palindrome LL
## LL Cycle

