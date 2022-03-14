第一次：一开始没想到用hashmap，一直再nested loop遍历array。但是一直有点bug，不能通过所有的tests

第二次：看了hint后想到用hashmap，但是没有想清楚如何排列sorted word。看了答案后才明白。

```python
# O(w*n*log(n)) Time | O(w*n); w = number of words, n = len(word)



def groupAnagrams(words):
	wordsCount = {}
	for word in words:
		sortedWord = ''.join(sorted(word))
		if sortedWord not in wordsCount:
			wordsCount[sortedWord] = [word]
		else:
			wordsCount[sortedWord].append(word)
			
	return list(wordsCount.values())

			
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