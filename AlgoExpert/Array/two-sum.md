一次过
```python

# O(n) Time | O(n) Space

def twoNumberSum(array, targetSum):
	numMap = {}
	
	for num in array:
		abstractNum = targetSum - num
		if abstractNum in numMap:
			return [num,abstractNum]
		else: 
			numMap[num] = num
			
	return []
		

```