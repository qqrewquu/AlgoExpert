完全没思路，看了答案后写出来的

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right


# O(n) Time | O(n) Space
class Solution:
    def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        
        
        # Method:  use stack 
        result = []
        stack = []
        node = root
        
        while node != None or len(stack) != 0: # or -> while node and stack
            while node:
                stack.append(node)
                node = node.left    
            currNode = stack.pop()
            result.append(currNode.val)
            node = currNode.right 
        
        return result
            
```    