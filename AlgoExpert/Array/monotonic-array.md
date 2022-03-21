一次过

```python
# O(n) Time | O(1) Space
def isMonotonic(array):
    if len(array) <= 1:
		return True 
	# if all the number are the same, the it is monotonic
	if len(set(array)) == 1:
		return True
	
	isIncrease = False 
	isDecrease = False 
	
	for i in range(len(array)-1):
		currNum = array[i]
		nextNum = array[i+1]
		
		if nextNum > currNum:
			isIncrease = True 
			
		elif nextNum == currNum:
			pass	
		else:
			isDecrease = True 
			
	return isIncrease != isDecrease
```		
	
