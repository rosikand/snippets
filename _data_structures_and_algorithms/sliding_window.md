---
layout: default
title: Pattern 1 - Sliding Window 
---

# Pattern 1: Sliding Window 

> **Pattern 1: Sliding Window**: This pattern deals with an array/linked list where we are asked to find or calculate something among all of the subarrays of a given size.

*Example*: “Given an array, find the average of all subarrays of ‘$K$’ contiguous elements in it.”


```python
def sliding_window(arr, window_size):
	"""
	This function implements pattern 1: Sliding Window. 
	Parameters:
		- arr: input array (list)
		- window_size: the size of each subarray 
	Returns:
		- sub_arrays: all of the ordered sub arrays of length 
		window_size in arr  
	""" 

	sub_arrays = []

	# number of sub arrays in arr of len(window_size) 
	# is given by len(arr) - window_size + 1
	num_sub_arrays = (len(arr) - window_size) + 1

	for i in range(num_sub_arrays):
		curr_sub_array = []
		for j in range(i, i + window_size):
			curr_sub_array.append(arr[j])
		sub_arrays.append(curr_sub_array)

	return sub_arrays
```

Source: [Grokking the Coding Interview course](https://www.educative.io/courses/grokking-the-coding-interview)


### Double for-loop over array 

It is also good to know, in general, how to loop over an array using a double for loop such that each element in the array is compared with every other element in the array. 

```python
arr = [1,2,3]

for i in range(len(arr)):
    for j in range(i, len(arr)):
        # do comparison here 
        print(arr[i], "*", arr[j])
```

Output: 
```
1 * 1
1 * 2
1 * 3
2 * 2
2 * 3
3 * 3
```
It is also good to know how to enumerate all subarrays of any length: 

```python
arr = [1,2,3]
master = []
for i in range(len(arr)):
    for j in range(i, len(arr)):
        master.append(arr[i:j+1])  # + 1 since non-inclusive end 
print(master)
```



