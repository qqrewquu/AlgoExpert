First time did not did not come up with when input is 'space' string.

Also, I thought about the two cases below and implemented in the wrong way,
so failed to pass all the tests

```python
# O(n) Time
# O(n) Space
def runLengthEncoding(string):
	counter = 1
	result = [] 
	# if string only has 'space', then return 1 + space
	if string == " ": return str(counter) + str(" ")
	
	for i in range(len(string)-1): 
		currentChar = string[i]
		nextChar = string[i+1]
		
		# if encouter same char for 9 time OR the currentchar != nextChar
		if counter == 9 or currentChar != nextChar:
			result.append(str(counter) + str(currentChar))
			# counter = 0
			counter = 0

		# Two cases need to handle in the last second position
		
		# if last second == last one
		if i == len(string)-2 and currentChar == nextChar:
			result.append(str(counter+1) + str(currentChar))
		
		# if last second != last one
		if i == len(string)-2 and currentChar != nextChar:
			result.append(str(counter+1) + str(nextChar))
		
		counter += 1
		
	
	return ''.join(result)
```
