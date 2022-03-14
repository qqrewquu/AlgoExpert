
第一次：一开始完全不知道怎么写，后来看了hint之后能想到下面'valOne'的情况。
再看了答案才了解'valTwo'和后面如何储存Palindromic substring前面和后面的index，
和返回longest Palindromic Substring。

第二次：一开始可以想到下面 case1，但是不知道怎么处理case 2。看了一眼答案，立刻想到了解决方法，然后写完一次过。


```python


# O(n^2) Time | O(n) Space

def longestPalindromicSubstring(string):
	if len(string) == 1:
		return string 
	
	# initialize longest value
	longestValue = ""
	
	# loop through string, expanding current character to left and right
	# to determine the current longest Palindrom substring
	for i in range(1,len(string)):
		# case 1) pass in left and right of current char
		valueOne = getPalin(i-1,i+1,string)
		# case 2) pass in left and current char, this is to handle case of the palindrom substring
		# has the two same char right in the middle, such as "xyzzyx"
		valueTwo = getPalin(i-1,i,string)
		
		if len(valueOne) <= len(valueTwo) and len(valueTwo) > len(longestValue):
			longestValue = valueTwo
		elif len(valueTwo) <= len(valueOne) and len(valueOne) > len(longestValue):
			longestValue = valueOne
	
	return longestValue
		

# helper function to get palindrom substring
def getPalin(leftPtr,rightPtr,string):
	while leftPtr >=0 and rightPtr < len(string):
		leftChar = string[leftPtr]
		rightChar = string[rightPtr]
		
		if leftChar != rightChar:
			break
			
		leftPtr -= 1
		rightPtr += 1

	return string[leftPtr+1:rightPtr]
		
		
			


		
		
	
	
	
```