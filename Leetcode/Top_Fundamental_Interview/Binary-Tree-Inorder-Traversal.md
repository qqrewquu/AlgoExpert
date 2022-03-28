```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right


class Solution:
    def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        # Method: recursion  
        # O(m+n) Time 
        # O(h) Space; h = height of the tree
        #  h = O(n) when worse case(un-balanced tree)
        #  h = O(log(n)) when best case(balanced tree)
        if root == None:
            return None 
        
        result = []
        def traversal(root):
            if root == None:
                return 
            
            traversal(root.left)
            result.append(root.val)
            traversal(root.right)
        traversal(root)
        
        return result
        


        # Method: iterative - use stack
        # O(n) Time | O(n) Space
        result = []
        stack = [] # do not add root 
        
        current = root
        
        while stack or current:
            # keep iterate the node until find the left-most node
            if current != None:
                stack.append(current)
                current = current.left 
            # if current is None, which means arrives at left-most node
            # pop value from stack, and 
            # move the pointer to pop node's right node
            else: 
                current = stack.pop()
                result.append(current.val)
                
                current = current.right
                
        
        return result
        
            
```    