```python
# O(n) Time
# O(n) Space

def caesarCipherEncryptor(string, key):
	alphaLetter = 'abcdefghijklmnopqrstuvwxyz'
	resultList = []
	
	for cha in string:
		newPosition = alphaLetter.index(cha) + key
		newPosition = newPosition % 26
		newChar = alphaLetter[newPosition]
		resultList.append(newChar)
		
	return ''.join(resultList) 
		
	
	
	
```