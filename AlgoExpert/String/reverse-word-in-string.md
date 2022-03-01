是最优解，但是compile了好几次才通过所有的tests。而且代码看起来有点乱

```python
# O(n) time; n = length of string
# O(n) space
def reverseWordsInString(string):
	if string == " ": return " "
	elif string == "": return ""
	elif len(string) == 1: return string

	i = -1
	# final result list
	resultList = []
	# temp list to store the each word
	tempList = []
	while abs(i) < len(string):
		currentChar = string[i]
		nextChar = string[i-1]
		# add current char and add word(stored in 'tempList') to 
		# results list when next character is space, 
		if nextChar == " ": 
			tempList.insert(0,currentChar)
			# convert list of char to a word string
			resultList.append(''.join(tempList))
			# empty the list for next word
			tempList = []
			
		# when in last second char, add current and next(which is last) char into
		# templist, and add templist to result list
		elif abs(i) == len(string)-1:
			tempList.insert(0,currentChar)
			tempList.insert(0,nextChar)
			resultList.append(''.join(tempList))
			
		# add current char to tempList
		else:
			tempList.insert(0,currentChar)
		i-=1
		
	# add the space at the end for first word
	resultList[0] = resultList[0] + " "
	# remove the space at the end for last word
	resultList[-1] = resultList[-1].replace(" ","")
	# convert list of word to a sentence string
	return "".join(resultList)

```