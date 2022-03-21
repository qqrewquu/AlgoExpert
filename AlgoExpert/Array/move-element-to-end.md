一开始没想法，看了hint后想到用two pointer。然后得到最优解

```python

# O(n) Time | O(1) Space
def moveElementToEnd(array, toMove):
	p1 = 0
	p2 = len(array) - 1
	while p1 < p2:

		numOne = array[p1]
		numTwo = array[p2]

		if numOne == toMove and numTwo == toMove:
			p2-= 1
		
		elif numOne == toMove and numTwo != toMove:
			array[p1],array[p2] = array[p2],array[p1]
			p1+=1			
			p2 -= 1
					
		# elif numOne != toMove and numTwo == toMove:
		#	pass
			 

		else: # numOne != toMove and numTwo != toMove
			p1+=1
	return array
			
			
	

```