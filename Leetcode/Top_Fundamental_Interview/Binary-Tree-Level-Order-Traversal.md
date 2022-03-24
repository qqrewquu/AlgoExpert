完全没思路，看了答案后写出来的

```python

# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right


# O(n) Time | O(n) Space
# iterative solution: 
from collections import deque
class Solution:
    def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:

        result = [] 
        if not root:
            return result        
        # add root node to queue
        queue = deque([root,])
        level = 0
        while queue: 
            result.append([])
            for i in range(len(queue)): 
                currentNode = queue.popleft()
                result[level].append(currentNode.val)
                if currentNode.left:
                    queue.append(currentNode.left)
                if currentNode.right:
                    queue.append(currentNode.right)        
                    
                    
            level += 1
            
        return result
```