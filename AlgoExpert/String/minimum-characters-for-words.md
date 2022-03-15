第二次做：没什么思路。看了答案会写。需要重新做


第一次做：

最开始的想法：一个for loop 遍历所有word，找到所有的character的frequency。然后再从中找
再找max frequency for each character。但发现这样的想法不能实现

看答案之后的想法：一个for loop一个个遍历word，然后找到这个word所有characters的frequency，然后用一个变量更新并保存这个word的characters出现最多次的frequency。

当for loop结束后，就会得到一个hash map储存着所有characters with max number of frequency across all the words。然后再转变成需要的结果

```python
'''
w = number of words
c = length of longest word
u = number of unique characters

O(w*c) Time 


O(u) Space Lower bound

O(u*c) Space Upper bound: this because when we converting the hashmap to list, 
all the unique characters may appear 'c' times which is the length of longest word


'''
def minimumCharactersForWords(words):
	maxCharCounts = {}
	'''O(w*c)'''
	for word in words: #'''O(w)'''
		# find all the chars frequency 
		charCounts = allCharFreq(word) # '''O(c)'''
		# update maximum chars frequency across all the words
		maxCharCounts = updateMaxCharFreq(maxCharCounts,charCounts) #'''O(c)'''
	
	
    return convertDictToList(maxCharCounts)
	
	
def convertDictToList(maxCharCounts):
	resultList = []
	for c in maxCharCounts:
		freq = maxCharCounts[c]
		for _ in range(freq):
			resultList.append(c)

	return resultList
		
def updateMaxCharFreq(maxCharCounts,charCounts):
	for c in charCounts:
		freq = charCounts[c]
		
		if c in maxCharCounts:
			maxCharCounts[c] = max(freq,maxCharCounts[c])
		else:
			maxCharCounts[c] = freq
			
	return maxCharCounts
	
def allCharFreq(word):
	charCounts = {}
	for c in word:
		if c not in charCounts:
			charCounts[c] = 1
		else:
			charCounts[c] += 1
	
	return charCounts
	
	
	
	
	
	
	
	
	
	
	
	
	
	

```