```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def postorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        
        # Method: Iterative - use pre-order tranvere method, and reverse the result list
        
        # O(n) Time | O(n) Space

        if root == None:
            return []

        result = []
        stack = [root]
        while len(stack) != 0:
            
            node = stack.pop()
            
            result.append(node.val)
            
            if node.left:
                stack.append(node.left)
                
            if node.right:
                stack.append(node.right)
                
        return result[::-1]
            
        

        
        # Method: Recursion
        # O(n + m) Time; n is number of nodes, and m is number of edges 
        # O(h) Space; h = height of the tree
        # h = O(n) when worse case(un-balanced tree)
        # h = O(log(n)) when best case(balanced tree)
        result = []
        def traversal(root):

            if root == None:
                return 
            traversal(root.left)
            traversal(root.right)
            result.append(root.val)
        
        traversal(root)

        return result
```