没什么思路，看了答案也有不太明白。下次重新做

```python
# This is an input class. Do not edit.
class Node:
    def __init__(self, value):
        self.value = value
        self.prev = None
        self.next = None


# Feel free to add new properties and methods to the class.
class DoublyLinkedList:
    def __init__(self):
        self.head = None
        self.tail = None

    def setHead(self, node):
        # Write your code here.
        pass

    def setTail(self, node):
        # Write your code here.
        pass

    def insertBefore(self, node, nodeToInsert):
		# insert to head and tail 
		
		if node == self.head:
			self.head.prev = nodeToInsert
			nodeToInsert.next = self.head
			self.head = node 
			
		if node == self.tail:
			self.
			
		
		
		
		
		
		
    def insertAfter(self, node, nodeToInsert):
        # Write your code here.
        pass

    def insertAtPosition(self, position, nodeToInsert):
		pass
			
			
	# O(n) Time | O(1) Space
    def removeNodesWithValue(self, value):
		current = self.head
		while current is not None:
			nodeToRemove = current 
			if nodeToRemove.value == value:
				self.remove(nodeToRemove)
			
			current = current.next

		
		
	# O(1) Time and Space
    def remove(self, node):
		# remove head and tail
		if node == self.head:
			self.head = self.head.next
			
		if node== self.tail:
			self.tail.prev.next = None
			# self.tail = self.tail.prev
			
		# otherwise 
		if node.next is not None:
			node.prev.next = node.next
			
		if node.prev is not None:
			node.next.prev = node.prev
			
		
		
		

    def containsNodeWithValue(self, value):
        # Write your code here.
        pass

```