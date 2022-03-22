一开始没思路，看了hint后知道了要用两个pointer，但是少了两个东西：
1. 忘记移动第二个while loop里的ptr1了
2. 没有考虑当removed node是head

```python

# This is an input class. Do not edit.
class LinkedList:
    def __init__(self, value):
        self.value = value
        self.next = None

# O(n) Time | O(1) Space
def removeKthNodeFromEnd(head, k):
	ptr1 = head
	ptr2 = head
	
	i = 1
	while i<=k :
		ptr1 = ptr1.next 
		i+=1
	
	# if the removed node is head, which means ptr1 should arrive None 
	if ptr1 is None:
        # set head's value to head's next node's value
		head.value = head.next.value 
        # set head next node to head next next node
		head.next = head.next.next
		# stop the program
		return 
        
	# arrive the node before the node should be removed
	while ptr1.next is not None:
		ptr2 = ptr2.next 
		ptr1 = ptr1.next

	# remove the node by linking prev node's next value to removed node's next node
	ptr2.next = ptr2.next.next
	

	
	
	
	
```