Reset variable 'count' to 1 in the for loop(which is wrong). And if I did not compile the code, I would not know need to handle the case that need to handle 
the last two characters. Need to redo this sometimes


```python
# O(n) Time
# O(n) Space
def runLengthEncoding(string):
	resultList = []
	count = 1
	
	if string == " ":
		return str(count) + " "
	
	for i in range(0,len(string)-1):
		currentChar = string[i]
		nextChar = string[i+1]
		
		if currentChar != nextChar:
			resultList.append(str(count) + currentChar) 
			count = 0
	
		if count == 9:
			resultList.append(str(count) + currentChar)
			count = 0
			
		# handle last two character since the index would stop at the last second position of string
		# case 1) last second != last one 
		if i == len(string) - 2 and currentChar == nextChar: 
			resultList.append(str(count+1) + currentChar)
			
		# case 2) last second == last one
		if i == len(string) - 2 and currentChar != nextChar: 
			resultList.append(str(count+1) + nextChar)
		
		count += 1
		
	return ''.join(resultList)
```
