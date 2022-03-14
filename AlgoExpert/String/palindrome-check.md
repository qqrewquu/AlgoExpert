```python
# O(n) Time
# O(1) Space

def isPalindrome(string):
	if len(string) == 1:
		return True 
	leftPtr = 0
	rightPtr = len(string)-1
	
	while leftPtr <= rightPtr:
		leftVal = string[leftPtr]
		rightVal = string[rightPtr]
		
		if leftVal == rightVal:
			leftPtr += 1
			rightPtr -= 1
		else:
			return False 
	return True 
	
```