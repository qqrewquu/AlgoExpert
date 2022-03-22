第二次尝试 method 1没有加 else statement，导致不能remove 超过两个以上的 duplicated value。看了leetcode答案后加上

Method 2是algoexpert的答案：用了一个nested while loop去 remove the duplicated in the second while loop。

```python
# This is an input class. Do not edit.
class LinkedList:
    def __init__(self, value):
        self.value = value
        self.next = None


# O(n) Time | O(1) Space
def removeDuplicatesFromLinkedList(linkedList):
	current = linkedList 
	
	# Method 1: 
	while current is not None and current.next is not None:
		if current.value == current.next.value:
			current.next = current.next.next
		else:
			current = current.next
			
	
	# Method 2:
# 	while current is not None:
# 		nextDistinct = current.next 
# 		while nextDistinct is not None and current.value == nextDistinct.value:
# 			nextDistinct = nextDistinct.next 
# 		current.next = nextDistinct
# 		current = nextDistinct
		

	return linkedList
```