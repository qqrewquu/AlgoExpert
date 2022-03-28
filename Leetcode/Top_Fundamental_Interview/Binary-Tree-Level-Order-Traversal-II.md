和 level order traverse基本一样。这里只需要反转一下最终的result list
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

# O(n) Time | O(n) Space 
from collections import deque 
class Solution:
    def levelOrderBottom(self, root: Optional[TreeNode]) -> List[List[int]]:
        
        
        if root == None:
            return None 
        
        queue = deque([root,])
        result = []
        
        level = 0
        
        while queue:
            result.append([])
            for _ in range(len(queue)):
                node = queue.popleft()
                result[level].append(node.val)
                if node.left:
                    queue.append(node.left)        
                if node.right:
                    queue.append(node.right)
            level += 1
        
        # reverse result
        result.reverse()
        return result
```