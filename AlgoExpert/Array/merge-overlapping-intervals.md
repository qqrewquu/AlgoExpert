
能写出来，但是因为没有加最后一个currentInterval，不能通过所有的tests。看了leetcode别人的答案后想到了。


```python
# O(nlogn) Time | O(n) Space
def mergeOverlappingIntervals(intervals):
	
	# sort first value of all the intervals 
	sortedIntervals = sorted(intervals, key = lambda x : x[0])
	result = []
	currentInterval = sortedIntervals[0]
	
	for nextInterval in sortedIntervals:
		currNumTwo = currentInterval[1]
		nextNumOne = nextInterval[0]
		
		if currNumTwo >= nextNumOne:
			# compare the 2nd number of current and next Intervals, 
			# only modify the currentInterval with the larger value
			currentInterval[1] = max(currentInterval[1],nextInterval[1])

		else:
			result.append(currentInterval)
			currentInterval = nextInterval

	# add last currentInterval
	result.append(currentInterval)
	
	return result
		
			
```