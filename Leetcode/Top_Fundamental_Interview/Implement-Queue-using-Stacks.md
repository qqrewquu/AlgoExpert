没思路，看了答案写出来的


```python

class MyQueue:

    def __init__(self):
        """
        in主要负责push，out主要负责pop
        """
        self.stack_in = []
        self.stack_out = []
    
    # O(1) Time | O(n) Space
    def push(self, x: int) -> None:
        """
        有新元素进来，就往in里面push
        """
        self.stack_in.append(x)

        
    # O(n) time worst case [stack_out is empty] 
    # O(1) time average case [stack_out is not empty] 
    
    # O(1) Space (don't know why, need to revisit this )
    
    
    def pop(self) -> int:
        """
        Removes the element from in front of queue and returns that element.
        """
        if self.empty():
            return None
        
        if self.stack_out:
            return self.stack_out.pop()
        else:
            for _ in range(len(self.stack_in)):
                self.stack_out.append(self.stack_in.pop())
            return self.stack_out.pop()

    # O(1) Time | O(1) Space
    def peek(self) -> int:
        """
        Get the front element.
        """
        # call my own pop function
        ans = self.pop()
        
        # add back the number since my own pop function delete the value from the stack
        self.stack_out.append(ans)
        return ans

   # O(1) Time | O(1) Space
    def empty(self) -> bool:
        """
        只要in或者out有元素，说明队列不为空
        """
        return not (self.stack_in or self.stack_out)


# # Your MyQueue object will be instantiated and called as such:
# # obj = MyQueue()
# # obj.push(x)
# # param_2 = obj.pop()
# # param_3 = obj.peek()
# # param_4 = obj.empty()
```