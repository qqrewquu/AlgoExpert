After look at hint, then know need to use Hash map. Then, came up with code with solution(method 1 below)

But, below method 2 is preferred since its provide more clear solution 

```python

# O(m+n) Time: m = len(characters), n = len(document)

# O(c) Space: c = len(unique characters) ** it could be O(1) since there are only 26 alpha letter

def generateDocument(characters, document):
	charsMap = {}
	for c in characters:
		if c not in charsMap:
			charsMap[c] = 1
		else:
			charsMap[c] += 1
			
	# (my method) method 1: if document's character in the characters.
	# delete current character frequency, and if its frequency < 0, which means,
	# the char in document does not in character. Return False
	# otherwise, Return True
	for c in document:
		if c not in charsMap:
			return False 
		
		charsMap[c] -= 1
		
		if charsMap[c] < 0: 
			return False 
	
	# (preferred method) method 2: if document's char not in character OR char exist but its frequency == 0,
	# Return False 
		
	for c in document:
		if c not in charsMap or charsMap[c] == 0:
			return False 
		
		charsMap[c] -= 1
		
	return True
		

	
	
	
	
```