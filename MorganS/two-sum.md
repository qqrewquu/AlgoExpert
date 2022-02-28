明天再做一遍这个题

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        numsMap = {}
        
        for i,num in enumerate(nums):
            someNum = target - num

            if someNum in numsMap:
                return [i, numsMap[someNum]]
            
            else:
            # elif someNum not in numsMap:
                numsMap[num] = i
                
```