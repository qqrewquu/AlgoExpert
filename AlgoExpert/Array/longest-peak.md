一开始思路是正确的，但是实现的方法不对，导致不能通过所有的test cases。最后看了一下答案，改了下面的‘below two while loops are  based on solution’

```python
# O(n) Time | O(1) Space

# is O(n) time because we only iterate through all the items at most 2 or 3 times since
# there is no consective number that forms 'peak'(i-1 > i < i+1), so it simplies to O(n) tiome.

def longestPeak(array):
	longestPeak = 0
	for i in range(1,len(array)-1):
		# found peak 
		if array[i] > array[i-1] and array[i] > array[i+1]:
			p1 = i-2
			p2 = i+2
			currentPeak = 3

            #### below two while loops are  based on solution
			while p1 >= 0 and array[p1] < array[p1+1]:
				p1-=1
				currentPeak += 1
			
			while p2 < len(array) and array[p2] < array[p2-1]:
				p2+=1
				currentPeak += 1 
        
			longestPeak = max(longestPeak,currentPeak)
				
	return longestPeak


```