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


## 2. Valid Subsequence

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


## 3. Three Number Sum problem - Important concept

Given an array and a value, find if there is a triplet in array whose sum is equal to the given value. If there is such a triplet present in array, then return the triplets. The triplets must be in ascending order

Eg Array = [12,3,1,2,-6,5,-8,6] target = 0
Solution: [[-8,2,6],[-8,3,5],[-6,1,5]]

The brute force solution is to use 3 for loops 

``` py

def threeNumberSum(array, targetSum):
	triple = []
	array.sort()
	for x in range(len(array)):
		for y in range(x+1,len(array)):
			for z in range(y+1,len(array)):
				sum = array[x]+array[y]+array[z]
				if sum == targetSum:
					triple.append([array[x],array[y],array[z]])
	return triple

```
This will be an O(n^3) operation not the best way

The other way is to use pointers. First we sort data using an efficent sorting algorith. Then we will here use 2 loops. The there will be two pointers left and right.
The right will start from end and first one will follow the first for loop.
When sum is larger than target we can decrement right index similarly if the sum is less we increment the left index.
The important point is the increment which occurs when we find a sum. The reason we increment both index is because we know for sure that if we increment/decrement one value it is definitly not going to be equal to sum. 

```py

def threeNumberSum(array, targetSum):
    
	triple = []
	left,right = 0,0
	array.sort()
	for x in range(len(array)-2):
		left = x+1
		right = len(array)-1
		while left < right:
			if (array[x] + array[left] + array[right] == targetSum):
				triple.append([array[x],array[left],array[right]])
				left+=1
				right-=1
			elif (array[x] + array[left] + array[right] > targetSum):
				right-=1
			else:
				left+=1
	return triple
			
```


## 4. Smallest Number

Given two arrays find a pair of numbers that has absolute difference closest to zero

Eg Array1 = [-1, 5, 10, 20, 28, 3] 
Array2 = [26, 134, 135, 15, 17]
Solution: [28,26]

The brute force solution is to use 2 for loops and find all possible combinations

``` py

def smallestDifference(arrayOne, arrayTwo):
	smallest_pair =[]
	smallest_val = abs(arrayOne[0] - arrayTwo[0]
	for x in arrayOne:
		for y in arrayTwo:
			diff = abs(x - y)
			if( diff < smallest_val ):
				smallest_val = diff
				smallest_pair = [x,y]
	
	return smallest_pair
			

```
This will be an O(n^2) operation not the best way

The other way is to use pointers. And exploit the ability to sort the array. First we sort data using an efficent sorting algorithm. Here we are doing a kind of calculated heurestic approach. with time complexity of `nlog(n) + mlog(m)`

!!! Info "Note"
    Note how we iinitialized float to have inifinte value
	smallest_val = float("inf")

```py

def smallestDifference(arrayOne, arrayTwo):

    arrayOne.sort()
    arrayTwo.sort()
    data = []
    i, j = 0, 0
    smallest_val = float("inf")

    while (i < len(arrayOne) and j < len(arrayTwo)):
        arr1 = arrayOne[i]
        arr2 = arrayTwo[j]
        diff = abs(arr1-arr2)

        if diff < smallest_val:
            smallest_val = diff
            data = [arrayOne[i], arrayTwo[j]]

        if (arr1 > arr2):
            j += 1
        elif (arr1 < arr2):
            i += 1
        else:
            return [arr1, arr2]
    return data
	
```

