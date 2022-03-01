一开始没想到用hashmap，一直再nested loop遍历array。但是一直有点bug，不能通过所有的tests

```python
# O(w*n*log(n)) time; w is number of words, n is length of longest word, log(n) is sort word
# O(w*n) space
def groupAnagrams(words):
	# variable to store all words frequency
	wordsFrequency = {}
	
	# loop through the words 
	for word in words:
		# sorted words will lead to list, so convert it back to string
		# now have sorted string
		sortedword = "".join(sorted(word))
		
		# if sorted string not in hashmap, add unsorted string as a list 
		if sortedword not in wordsFrequency:
			wordsFrequency[sortedword] = [word]	
			
		# if sorted string in hashmap, add unsorted string in the list
		else:
			wordsFrequency[sortedword].append(word)
		
	# return all the word from hashmap value
			
	return list((wordsFrequency.values()))
			
```

最开始的解法（不能通过所有的tests）
```python

def groupAnagrams(words):
    resultList = []
    
	for i,word in enumerate(words):
		j = i+1
		templist = [] 
		while j < len(words):
			nextWord = words[j]
			if sorted(word) == sorted(nextWord):
				if word in templist: 
					templist.append(nextWord)
				elif nextWord in templist:
					templist.append(word)
				else: 
					templist.append(word)
					templist.append(nextWord)
			j+=1
		
		if len(templist) != 0: 
			resultList.append(templist) 
			
	return resultList
	
```