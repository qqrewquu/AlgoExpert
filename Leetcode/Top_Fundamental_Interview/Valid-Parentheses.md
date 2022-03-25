```python
# O(n) Time | O(n) Space worst case if we have all one direct bracket, and do not have another direct's(e.g. s = '({({({({')
class Solution:
    def isValid(self, s: str) -> bool:
    
        stack = []
        
        '''
        Method 1: use stack and dictionary 
        '''
        parMap = {'[':']','{':'}','(':')'}
        
        
        
        for char in s:
            if char in parMap:
                stack.append(parMap[char])
                
            elif len(stack) == 0 or stack[-1] != char:
                return False 
            
            else:
                stack.pop()
                
        return True if len(stack) == 0 else False 
    
        '''
        Method 2: just use stack 
        '''
        
#         for char in s:
#             if char == "[":
#                 stack.append("]")
#             elif char == "(":
#                 stack.append(")")
                
#             elif char == "{":
#                 stack.append("}")
                
#             elif len(stack) == 0 or stack[-1] != char:
#                 return False 
            
#             else:
#                 stack.pop()
                

#         return True if len(stack)==0 else False
        
            

```