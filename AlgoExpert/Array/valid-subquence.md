自己答案不是最优解。下面的是看了答案（最优解）后才想出来的


```python
# O(n+m) Time | O(1) Space; n = len(array) and m = len(sequence)
def isValidSubsequence(array, sequence):
	arrayPtr = 0
	seqPtr = 0
	
	while (arrayPtr < len(array)) and (seqPtr < len(sequence)):
		if array[arrayPtr] == sequence[seqPtr]:
			arrayPtr += 1
			seqPtr += 1
			
		else:
			arrayPtr += 1
			
	return seqPtr == len(sequence)
```