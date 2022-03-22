有思路，但是在当遍历两个linked list的时候(while loop below)，忘记initialize new node and append it to result linkedlist（我自己仅仅是assign value to result linkedList, 看下面的注视）

```python

# This is an input class. Do not edit.
class LinkedList:
    def __init__(self, value):
        self.value = value
        self.next = None

# O(max(m,n)) Time
# O(max(m,n)) Space

def sumOfLinkedLists(linkedListOne, linkedListTwo):
	# create a new linked list as the result linked list
	resLinkedList = LinkedList(0)
	# the node to new result linked list 
	currentNode = resLinkedList
	
	# two pointer to iterate through two lists 
	pointerOne = linkedListOne
	pointerTwo = linkedListTwo
	
	# initialize carry to 0 
	carry = 0 
	# we also need carry != 0 because for example we have [2] and [9],
	# adding them has a carry, however, if we do not have carry ! = 0,
	# both linked list reach to end and while loop stop. So, 
	# we need this to keep the carry to next iteration and keep adding.
	while pointerOne!= None or pointerTwo != None or carry !=0 :
		
		# add two values 
		valueOne = pointerOne.value if pointerOne != None else 0
		valueTwo = pointerTwo.value if pointerTwo != None else 0
		valueSum = valueOne + valueTwo + carry			
		
		# get the val 
		val = valueSum % 10

        '''
        create new node append it to result list(which is correcy)
        '''
		# creat a new node and add val to its value
		newNode = LinkedList(val)
		# assign the next node to this newly created node
		currentNode.next = newNode 
		# move the node to next one
		currentNode = currentNode.next

        '''
        what I did instead(which is wrong):
        '''
        # currentNode.next = val
        # currentNode = currentNode.next
		


		# record  the carry and add it to sumfor next iteration
		carry = valueSum // 10 
		
		# move the two pointers to next 
		pointerOne = pointerOne.next if pointerOne != None else None
		pointerTwo = pointerTwo.next if pointerTwo != None else None
		
    

    return resLinkedList.next

```