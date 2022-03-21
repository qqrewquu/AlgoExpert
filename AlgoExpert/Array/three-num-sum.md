一次过

```python
# O(n^2) Time | O(n) Space
def threeNumberSum(array, targetSum):
	resultList = []
	array.sort() # nlogn

		
	for i,num in enumerate(array): # n 
		p1 = i+1 
		p2 = len(array)-1
		while p1 < p2: #n
			if num + array[p1] + array[p2] == targetSum:
				resultList.append([num,array[p1],array[p2]])
				p1 += 1
				p2 -= 1
			elif num + array[p1] + array[p2] < targetSum:
				p1 += 1
			else:
				p2 -=1
				
	return resultList
				
				
	
	
```