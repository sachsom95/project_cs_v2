# Hello, World!

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