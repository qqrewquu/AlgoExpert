没思路，看了答案写出来的

```python

# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right


# O(n) Time | O(n) worst case [in-balanced tree] and O(logn) best [balanced tree]

# ** when it is balanced tree, the height(tree) - logN
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        
        if not root: 
            return 0
        
        
        depth = 0
    
        stack = [(1,root)]
        
        node = root 
        
        while stack != []: 
            currentDepth,node = stack.pop()
            
            depth = max(depth,currentDepth)
            if node.left: 
                stack.append((currentDepth + 1, node.left))
                
            if node.right:
                stack.append((currentDepth + 1, node.right))


        return depth
    
        
        
        
        
        
        
```