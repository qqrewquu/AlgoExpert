```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isValidBST(self, root: Optional[TreeNode]) -> bool:
        # iterative: using preorder traverse 
        # O(n) Time | O(n) Space 
        
        stack = [] 
        current = root 
        prev = None
        
        while stack or current:
            # go to left child until hit None 
            if current: 
                stack.append(current)
                current = current.left 
            else:
                current = stack.pop()
                if prev and current.val <= prev.val:
                    return False 
                prev = current 
                current = current.right 
    
    
        # after check all the nodes in the tree, it must be a valid BST
        return True
                
        
        
        # (TO-DO)recursion: do know how to do 
        
```