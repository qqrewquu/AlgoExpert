```python

# O(n) Time | O(1) Space
'''
思路: loop through the item

if item = int:
    add to stack
    
else: # an operand
    pop two numbers from stack and do math with operand 
    
    push the result back to stack
'''
class Solution:
    def evalRPN(self, tokens: List[str]) -> int:
        
        operands = "+-*/"
        stack = []
        
        for item in tokens:
            if item not in operands:
                stack.append(item)
                
            else:
                num1 = stack.pop() 
                num2 = stack.pop()
                res = int(eval(str(num2) + item + str(num1)))
                stack.append(res)
                
        print(stack)
        return stack.pop()
```