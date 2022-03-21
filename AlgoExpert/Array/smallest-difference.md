一开始当两个数字之减 < smallestAbstract的时候，也移动了两个pointers。当看完答案后删掉了它们就得到了最优解。


```python

#(Onlogn + Omlogm) Time | O(1) Space; n and m are the length of two arrays
def smallestDifference(arrayOne, arrayTwo):
	arrayOne.sort()
	arrayTwo.sort()

	
	# -1 3 5 10 20 28
	# 15 17 26 134 135

	smallAbstr = 99999
	smallPair = [999,999]
	p1 = 0
	p2 = 0 
	while p1 < len(arrayOne) and p2 < len(arrayTwo):
		num1 = arrayOne[p1]
		num2 = arrayTwo[p2]
		if abs(num1 - num2) == 0:
			return [num1, num2]
		elif abs(num1 - num2) <  smallAbstr:
			smallAbstr = abs(num1 - num2)
			smallPair = [num1,num2]
            # should not add these two below
            # p1 += 1
            # p2 += 2

		if num1 < num2:
			p1+=1
		else:
			p2+=1
	
	return smallPair

			
	
	
	
	
```