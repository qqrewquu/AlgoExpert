思路：检查target - curentNum 的差值，如果差值不在hashmap，把当前currentNum和idx储存到里面。如果差值在hashmap里，那么差值 + num = target，也就是说找到了结果。
最后返回差值 和 num 的idxs


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