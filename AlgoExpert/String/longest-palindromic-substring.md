
一开始完全不知道怎么写，后来看了hint之后能想到下面'valOne'的情况。
再看了答案才了解'valTwo'和后面如何储存Palindromic substring前面和后面的index，
和返回longest Palindromic Substring。


```python


# O(n^2) time
# O(n) space: ultimately still need to slice the longest palindromic substring out of the string, 
#             and this longest palindromic substring can be as large as the string itself, 
#			  in the worst case.
def longestPalindromicSubstring(string):
	
	# declare a list including start iddex and end index that including the longest
	# palindromic string 
	bestLongest  = [0,1]
	
	# loop through the string, and move the slider to find the longest palindromic substring
	
	for i in range(1,len(string)):
		# get palindrmoc from left and right idx of current val
		valOne = getPadlin(i-1,i+1,string)
		# get palindrmoc from left idx of current val and current val 
		# this is to handle 'Sample Input' cases: 'abaxyzzyxf'
		# when slide to either first or second 'z', if using above getPadlin function
		# it will never return the longest padlin. But this padlin function will handle 
		# such case
		valTwo = getPadlin(i-1,i,string)
		
		# return either valOne or valTwo whose absolute differenece value is larger
		currentLongest = max(valOne,valTwo,key=lambda x: abs(x[1] - x[0]))
		# return either previus bestLongest  or currentLongest 
		# whose absolute differenece value is larger
		bestLongest = max(bestLongest,currentLongest,key=lambda x: abs(x[1] - x[0]))

	print(bestLongest)
	return string[bestLongest[0]:bestLongest[1]]

# helper fucntion:
# expand left and right index to find longest palindromic index
def getPadlin(leftPointer,rightPointer,string):
	while leftPointer >= 0 and rightPointer <= len(string)-1:
		leftValue = string[leftPointer]
		rightValue = string[rightPointer]

		if leftValue != rightValue:
			break
		else:
			leftPointer -= 1
			rightPointer +=1
	
	# need left pointer to plus one because left pointer will 
	# move left one position away from position we should return(to jump out of while loop)
	# so, need to add one to move right one position
	# rightPointer no need to move left one position because
	# when we return the longest value index from last line of main()
	# the right value will be return as value-1. e.g. lis[1:3] will only return 
	# 1 - 2 posiition value, not 3
	return [leftPointer+1,rightPointer]

```