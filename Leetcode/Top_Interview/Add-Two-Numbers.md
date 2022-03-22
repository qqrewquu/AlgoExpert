思路是对的，有两个错误

1. 下面的2： 我是直接给linkedlist 赋值，忘记linked list是由每一个node组成的，不是数值。
2. 下面的3: 我没有写 if else 导致下面的1会出错


```python
# Definition for singly-linked list.
# class ListNode:

#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

# O(max(m,n)) Time | O(max(m,n)) Space
class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        
        nodeOne = l1
        nodeTwo = l2
        
        carry = 0 
        newList = ListNode()
        newListNode = newList
        
        while nodeOne is not None or nodeTwo is not None or carry != 0:
            
            # 1. two linked list length might be the same,
            # so when shorter list is over, the rest values are 0 for adding the sum
            nodeOneVal = nodeOne.val if nodeOne is not None else 0
            nodeTwoVal = nodeTwo.val if nodeTwo is not None else 0
            
            sumValue = nodeOneVal + nodeTwoVal + carry
            

            stayValue = sumValue % 10 
            carry = sumValue // 10 
            
            # 2. create a new node and append it to result linked list
            newNode = ListNode(stayValue)
            newListNode.next = newNode
            newListNode = newNode
            
            
            # 3. if currentNode is None, assign its next is also None
            # this is to set the none value to 0 for 1.
            nodeOne = nodeOne.next if nodeOne is not None else None
            nodeTwo = nodeTwo.next if nodeTwo is not None else None
            
        return newList.next
            
            
            
```