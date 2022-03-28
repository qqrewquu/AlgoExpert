```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right



class Solution:
    def preorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        
        # Method: iterative
        # O(n) Time | O(n) Space
        if root == None:
            return [] 
                
        stack = [root]
        result = []
        
        while len(stack) > 0:
            node = stack.pop()
            result.append(node.val)
            if node.right != None:
                stack.append(node.right)
            if node.left != None:
                stack.append(node.left)
            
            
        return result
        
        

        
        # Method: Recursion
        
        # O(n + m) Time; n is number of nodes, and m is number of edges 
        # O(h) Space; h = height of the tree
        # h = O(n) when worse case(un-balanced tree)
        # h = O(log(n)) when best case(balanced tree)
#         result = []
    
#         def traversal(root):
#             if root == None:
#                 return 
            
#             result.append(root.val)
#             traversal(root.left)
#             traversal(root.right)
    
#         traversal(root)
        
#         return result
```