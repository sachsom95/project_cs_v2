# Interview Prep!

!!! Warning "Note"
    Site Under construction

    * [x] - Content - May 4

Lets start of with LinkedList Questions.

## 1. Remove Duplicate

Given an **ordered** linkedlist. Write a function that returns a modifed version of linkedlist that doesn't have duplicate values for example

Input
```
linkedlist : 1 -> 1 -> 2 -> 2 ->3 
```

Output
```
linkedlist : 1 -> 2 -> 3
```

``` py

class LinkedList:
    def __init__(self, value):
        self.value = value
        self.next = None

def removeDuplicatesFromLinkedList(linkedList):
    prev = linkedList
	current = prev.next
	while(current):
		if(prev.value == current.value):
			current = current.next
			continue
		else:
			prev.next = current
			prev = prev.next
			current = current.next
	
	if(prev.next!= None):
		prev.next = current
		
    return linkedList
```

Here note the last if condition. This is needed when we have duplicates in the last part. This is `O(n)`.
This is possible because the linkedlist is ordered.