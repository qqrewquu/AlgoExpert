一开始不能处理负数，看了原来的submission后想到先把数字换成正数，但保留原来的数值。最后如果原来的数值<0，再把result换成负数。

```python
# O(n) Time | O(n) Space
class Solution:
    def reverse(self, x: int) -> int:
        
        # check if value out of bound
        if x >= 2**31-1 or x <= -2**31:
            return 0
        
        
        positiveNum = abs(x)
        newNum = []
        for char in reversed(str(positiveNum)):
            newNum.append(char)
            
        result = int(''.join(newNum))
        
        if x < 0:
            result = -result
            
        # check if value out of bound
        if result >= 2**31-1 or result <= -2**31:
            return 0
        
        return result
```