
一次过

```python
# O(n) Time | O(1) Space; its constant space because there is only 26 unique English Alpha letter
# so it is constant space

def firstNonRepeatingCharacter(string):
	stringCounts = {}

	# count appeared characters' frequencies
	for s in string:
		if s not in stringCounts:
			stringCounts[s] = 1
		
		else:
			stringCounts[s] += 1

	# loop through the appeared character again, 
	# if its frequency == 1, return its index
	for i,s in enumerate(string):
		if stringCounts[s] == 1:
			return i
		
	return -1
```