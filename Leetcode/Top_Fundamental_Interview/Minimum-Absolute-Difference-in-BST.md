```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def getMinimumDifference(self, root: Optional[TreeNode]) -> int:
        # recursion: use in-order traverse that convert the binary tree to an ordered list, 
        # then compare the adjacent pair value in the list 
        
        # ! The reason use in-order travser becuase the small diff is the  diff between the parent node 
        # and its two children, so use in-order will convert the list to [child 1, parent, child2 .....]
        # in this case, the diff between parent and its two children will be calcuated
        
        
        # O(n) Time | O(n) Space b/c store all the values in the list
        
        
        orderedList = []
        
        # in-order traverse
        # O(n) balanced tree; O(log(n)) un-balanced tree
        def buildaList(root):
            if root == None:
                return 
            buildaList(root.left)
            orderedList.append(root)
            buildaList(root.right)
            
        buildaList(root)
        
        # loop through the ordered list, and compare adjacent pair
        
        smallestDiff = float('inf')
        
        
        # O(n)
        for i in range(len(orderedList)-1):
            currentDiff = abs(orderedList[i].val - orderedList[i+1].val)
            smallestDiff = min(smallestDiff,currentDiff)
            
        return smallestDiff
```