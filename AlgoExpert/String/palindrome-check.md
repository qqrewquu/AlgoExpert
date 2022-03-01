```python
# O(n) Time
# O(1) Space
def isPalindrome(string):	
	startPointer = 0
	endPointer = len(string) - 1
	while startPointer < endPointer:
		startVal = string[startPointer]
		endVal = string[endPointer]
		
		if startVal != endVal:
			return False 
		startPointer += 1
		endPointer -= 1
		
	return True

```