# Interview Prep!

!!! Warning "Note"
    Site Under construction

    * [x] - Content - Friday OCT 2

Lets start of with Array Questions.



## 1. two Number Sum

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.

``` py

def twoNumberSum(array, targetSum):
    dic = {}
	for x in array:
		if x in dic.keys():
			return [x, targetSum-x]
		else:
			dic[targetSum-x] = True
	return []
```

Use Hash Map and compliment to do the operation in O(n)


## 2. two Number Sum

Given two non-empty arrays of integers, write a function that determines whether the second array is a subsequence of the first one.
A subsequence of an array is a set of numbers that aren’t necessarily adjacent in the array but that are in the same order as they appear in the array. For example these numbers
[2, 3, 5]
are a subsequence of the array:
[1, 2, 3, 4, 5]

``` py

def isValidSubsequence(array, sequence):
	for x in array:
		if (len(sequence) and x == sequence[0]):
			sequence.pop(0)
	return (not len(sequence))

```
This will be an O(n) operation with pop done on sequence array






