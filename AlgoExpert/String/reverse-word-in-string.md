第二次做不是最优解，看了video explanation才明白。需要下次重新再做一次

```python
# O(n) time | O(n) Space

def reverseWordsInString(string):
	resultList = []
	ptr = 0
	for i,cha in enumerate(string):
		# if current char is space, then add all previous characters
		if cha == " ":
			resultList.append(string[ptr:i])
			# move the pointer to current idx(which is space)
			ptr = i
		
		# if ptr' char is space, add space, and move the ptr to current idx(i)
		elif string[ptr] == " ":
			resultList.append(" ")
			ptr = i
			
			
	# after for loop, the last string is not added, then add the last string
	# using 'ptr' which stays at the first char of the last string
	resultList.append(string[ptr:])
	
	# reverse the list
	reverseList(resultList)
	
	return (''.join(resultList))


# helper function
def reverseList(resultList):
	start = 0
	end = len(resultList)-1
	
	while start <= end:
		resultList[start],resultList[end] = resultList[end],resultList[start]
		
		start+=1
		end-=1
		
		
		
	
	
	
	
	
	
	
	
	
	
	
	
	
	

			
```