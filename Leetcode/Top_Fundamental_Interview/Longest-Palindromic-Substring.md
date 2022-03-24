一开始不能通过所有的test。后来看了答案后发现忘记加help function里的break，加上后通过


```python
# helper function
def findPanlin(s,leftPtr,rightPtr):
        while leftPtr >= 0 and rightPtr < len(s):
            if s[leftPtr] == s[rightPtr]:
                leftPtr -= 1 
                rightPtr += 1
            
            else:
                break
                
        return s[leftPtr+1:rightPtr]

# O(n) Time | O(n) Space

class Solution(object):

        
    def longestPalindrome(self, s):
        if len(s) <= 1:
            return s
        
        longestPalin = ""
        
        for i in range(1,len(s)):
            currPandlinOne = findPanlin(s,i-1,i+1)
            currPandlinTwo = findPanlin(s,i-1,i)

            currPandlin = currPandlinOne if len(currPandlinOne) > len(currPandlinTwo) else currPandlinTwo
            
                
            if len(currPandlin) > len(longestPalin):
                longestPalin = currPandlin
                
        return longestPalin
            
```  
    
    
