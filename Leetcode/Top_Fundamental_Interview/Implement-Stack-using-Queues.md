关键点：创建两个queue，q1和q2。当pop的时候，把q1的所有元素（除了最后一个），放到q2里，然后pop q1里最后一个元素。之后再把q2里的元素放回到q1里


```python

from collections import deque

class MyStack:

    def __init__(self):
        self.queue_in = deque()
        self.queue_out = deque()
            
    
    
    # O(1) Time | O(1) Space
    def push(self, x: int) -> None:
        self.queue_in.append(x)
  

    # O(n) Time | O(1) Space
    def pop(self) -> int:
        if self.empty():
            return None 
    
        for i in range(len(self.queue_in)-1):
            self.queue_out.append(self.queue_in.popleft())
            
        self.queue_in, self.queue_out = self.queue_out, self.queue_in
        
        return self.queue_out.popleft()
    
    
    # O(1) Time | O(1) Space    
    def top(self) -> int:
        if self.empty():
            return None 
        return self.queue_in[-1]
    
    # O(1) Time | O(1) Space 
    def empty(self) -> bool:
        return len(self.queue_in) == 0
        


# Your MyStack object will be instantiated and called as such:
# obj = MyStack()
# obj.push(x)
# param_2 = obj.pop()
# param_3 = obj.top()
# param_4 = obj.empty()
```