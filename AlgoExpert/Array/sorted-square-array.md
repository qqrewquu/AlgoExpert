一开始的代码不能通过所有的test cases。后来看了下面的答案后，写了两种version的最优解代码



```python
# O(n) Time | O(n) Space
def sortedSquaredArray(array):
	resultList = [0 for _ in array]
	leftPtr = 0
	rightPtr = len(array) - 1 
	savePtr = len(array) - 1
	
	# while loop version
	while leftPtr <= rightPtr:
		leftVal = array[leftPtr]
		rightVal = array[rightPtr]

		
		if abs(leftVal) > abs(rightVal):
			resultList[savePtr] = leftVal * leftVal
			leftPtr += 1
		else:
			resultList[savePtr] = rightVal * rightVal
			rightPtr -= 1
		
		savePtr -= 1
		
	return 	resultList
		
			
# 	# for loop version
# 	for i in reversed(range(len(array))):
# 		leftVal = array[leftPtr]
# 		rightVal = array[rightPtr]
		
# 		if abs(leftVal) > abs(rightVal):
# 			resultList[i] = (leftVal*leftVal)
# 			leftPtr += 1
# 		else:
# 			resultList[i] = rightVal*rightVal
# 			rightPtr -= 1
# 	return resultList

		

```