At first, did not come up with a correct solution. 

After glancing the solution, achieve optimal solution 

```python
# O(m+n) Time; where m & n are lengths of characters and documents
# O(c) Space; where c is number of unique characters in the characters string

def generateDocument(characters, document):
	
	# Variable to store the number of chars in characters
	charCounts = {}
	
	# store the number of chars in characters
	for cha in characters:
		if cha not in charCounts:
			charCounts[cha] = 1
		else:
			charCounts[cha] += 1
			
	
	# check target char is in the characters 
	for cha in document:
		# if target char not in characters or characters char has smaller frequency than target char
		# return false 
		if cha not in charCounts or charCounts[cha] == 0:
			return False 
		
		# if target char in characters, then characters char frequency minus 1
		charCounts[cha] -=1 
	
	# if code goes to here, then true
	return True
```