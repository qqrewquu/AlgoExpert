第一次没有加最后一行的return，导致没有通过所有的tests。看了答案后才想起来加最后一行

```python
# O(nlogn) Time | O(1) Space
def nonConstructibleChange(coins):
	if len(coins) < 1: 
		return 1 
	
	coins.sort()
	
	sumNum = 1
	for num in coins:
		if num > sumNum:
			return sumNum #+1?
		sumNum += num
	
	return sumNum 
	
		
```