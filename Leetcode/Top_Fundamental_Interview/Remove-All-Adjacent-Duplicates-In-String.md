一开始的代码是对的，但是exceed memory。整体思路是对的，只是我一开始的方法创建了太多的stack。
看了答案后改成下面的答案

```python
# O(n) Time 

# O(n) Space [worse case]:  if no adjacent same characters in the given input;
# O(n-d) Space [average case]: where d is length of all duplicated 

class Solution:
    def removeDuplicates(self, s: str) -> str:
    
        stack = []

        for char in s:
            
            # method 1: more efficient
            if len(stack) != 0 and stack[-1] == char:
                stack.pop()
            
            else:
                stack.append(char)
            
            # method 2: not efficient        
#             if char not in stack:
#                 stack.append(char)
                
#             elif len(stack) != 0 and stack[-1] == char:
#                 stack.pop()
                
#             elif len(stack) != 0 and stack[-1] !=char:
#                 stack.append(char)
                
            
        return ''.join(stack)        
        
        
        
        
        
        
        

```