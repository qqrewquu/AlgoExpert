```python

# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def searchBST(self, root: Optional[TreeNode], val: int) -> Optional[TreeNode]:
        # recusion: below needs the 'return' statement in 'elif' and 'else' b/c
        # it would return the result, otherwise, nothing would return 
        
        # O(h) Time | O(h) Space; 
        # h = logn when balanced tree, h = n when in balanced tree
        
        if root ==None:
            return None 
        
        if root.val == val:
            return root 
        

        elif root.val < val:
            return self.searchBST(root.right,val)

        else:
            return self.searchBST(root.left,val)


        # iterative
        # O(h) Time | O(1) Space; 
        # h = logn when balanced tree, h = n when in balanced tree
#         while root:
#             if root == None:
#                 return None 
            
#             if root.val == val:
#                 return root
            
#             elif root.val < val:
#                 root = root.right 
                
#             else:
#                 root = root.left
                
#         return None

```