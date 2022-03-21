最优解是O(1) Space, 但是答案是基于integers array between 1 to n，并且答案特别奇怪。所以跳过了

```python

# O(n) Time | O(n) Space
def firstDuplicateValue(array):
	numCount = {}
	
	for num in array:
		if num not in numCount:
			numCount[num] = 1
		else:
			return num
	return -1
```