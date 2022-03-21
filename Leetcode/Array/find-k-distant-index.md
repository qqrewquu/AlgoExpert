不是optimal的代码。最优解是O(n) time

```python

# O(n^2) | O(n) Space
        resultList = []
        for i,num in enumerate(nums):
            if num == key:
                leftPtr = i-1
                resultList.append(i)
                rightPtr = i+1
                while leftPtr >=0 and abs(leftPtr-i) <= k: 
                    resultList.append(leftPtr)
                    leftPtr -= 1
                while rightPtr < len(nums)  and abs(rightPtr-i) <= k:
                    resultList.append(rightPtr)
                    
                    rightPtr += 1
                    
        return set(sorted(resultList))    
        
```