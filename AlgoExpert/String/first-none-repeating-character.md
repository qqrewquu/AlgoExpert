
一开始以为最优解是O(1) Space，所以没用hashmap去储存每个char出现的频率（因为认为hashmap回储存 all the length of input）。后来看了hint才发现hashmap是 O(1) Space。然后写完一次过

```python
# O(n) time; where n = length of input string

# O(1) space; where is constant because hashmap only store 26 alphabet letter's 
# with corresponding's frequency,

def firstNonRepeatingCharacter(string):
	
	stringFrequency = {}
	
	# store all the char's frequency
	for i,cha in enumerate(string):
		if cha not in stringFrequency:
			stringFrequency[cha] = 1
			
		else:
			stringFrequency[cha] +=1
			
	
	# if there is a char frequency == 1, return its index
	for i,cha in enumerate(string):
		if stringFrequency[cha] == 1:
			return i
		
	return -1

```