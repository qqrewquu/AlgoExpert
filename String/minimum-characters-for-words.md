最开始的想法：一个for loop 遍历所有word，找到所有的character的frequency。然后再从中找
再找max frequency for each character。但发现这样的想法不能实现

看答案之后的想法：一个for loop一个个遍历word，然后找到这个word所有characters的frequency，然后用一个变量更新并保存这个word的characters出现最多次的frequency。

当for loop结束后，就会得到一个hash map储存着所有characters with max number of frequency across all the words。然后再转变成需要的结果

```python
# n = length of words list
# w = length of longest word
# c = number of unique characters across all the words
'''
O(n*w) Time 

Space:

O(c) is lower bound. For example, some unique character only occur constant time in most of words
uut the output array of characters might take up more space if some unique characters appear 
multiple times in a single word. For example, we might have a hash table {"a": 3"} 
with one character but an output array ["a", "a", "a"] with three characters.

O(c*w) is upper bound. For example, every single characters acorss all the words are unique

'''
def minimumCharactersForWords(words):
	maxCharFrequency = {}
	# loop through each word 
	
	# O(n*w)
	for word in words: #O(n)
		# count each char's frequency for current word
		characterFrequencies = countCharacterFRequencies(word) #O(w)
		# update the char's max frequencies 
		updateMaxiumFrequencies(characterFrequencies,maxCharFrequency) #O(w)
	# convery the hashmap that contains all chars with max frequency
	# to the list as requested
	return makeCharFreqToArray(maxCharFrequency) # O(n*w)


def makeCharFreqToArray(maxCharFrequency):
	resultList = []
	for cha in maxCharFrequency:
		frequency = maxCharFrequency[cha]
		for _ in range(frequency):
			resultList.append(cha)
	return resultList 

def updateMaxiumFrequencies(charFrequency,maxCharFrequency)
	for cha in charFrequency:
		frequency = charFrequency[cha]
		
		if cha not in maxCharFrequency:
			maxCharFrequency[cha] = frequency
		else:
			maxCharFrequency[cha] = max(maxCharFrequency[cha],frequency)
	
	return maxCharFrequency
	
def countCharacterFRequencies(word):
	charFrequency = {}

	for cha in word:
		if cha not in charFrequency:
			charFrequency[cha] = 1
		else:
			charFrequency[cha] += 1
		
	return charFrequency
```