```python
# O(n) Time
# O(n) Space
def caesarCipherEncryptor(string, key):
	if key == 0: 
		return string
	stringList = list('abcdefghijklmnopqrstuvwxyz')
	resultList = []
	
	for cha in string:
		charPosition = stringList.index(cha)
		newCharPosition = charPosition + key
		
		if newCharPosition >= 26:
			newCharPosition %= 26
		
	    resultList.append(stringList[newCharPosition])
		
		
	return ''.join(resultList)
	
	
```