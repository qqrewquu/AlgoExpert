明天再做一次这个题

```python
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:  
        
        # sort
        nums.sort()
        resultList = []
    
        for i in range(len(nums)):
            if nums[i] > 0:
                break
            if i!=0 and nums[i] == nums[i - 1]:
                continue   
            leftIdx = i+1
            rightIdx = len(nums)-1
            
            while leftIdx < rightIdx:
                currentSum = nums[leftIdx] + nums[i] + nums[rightIdx]
                
                if currentSum == 0:
                    resultList.append([nums[leftIdx],nums[i], nums[rightIdx]])
                    leftIdx += 1
                    rightIdx -= 1
                    while leftIdx <  rightIdx and nums[leftIdx] == nums[leftIdx-1]:
                        leftIdx += 1               
                elif currentSum < 0:
                    leftIdx += 1
                    
                else:
                    rightIdx -= 1
                    
        
        return resultList
        
```

First attempt, but did not pass all tests
```python

        target = 0
        if len(nums) < 1:
            return []
        nums.sort()
        resultList = []
                          # i  k
        # [-8, -6, 1, 2, 3, 5, 6, 12]
        for i in range(1,len(nums)-1):
            
            leftIdx = i-1
            rightIdx = i+1
            
            while leftIdx >= 0 and rightIdx < len(nums):
                currentSum = nums[leftIdx] + nums[i] + nums[rightIdx]
                
                if currentSum == target:
                    resultList.append([nums[leftIdx],nums[i],nums[rightIdx]])
                    leftIdx -= 1
                    rightIdx += 1
                    
                    
                elif currentSum < target: 
                    rightIdx += 1
                    
                else:
                    leftIdx -= 1

        return resultList


            

```