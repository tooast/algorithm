### :page_facing_up: Description

As the title described, you should only use two stacks to implement a queue's actions.

The queue should support `push(element)`, `pop()` and `top()` where pop is pop the first(a.k.a front) element in the queue.

Both pop and top methods should return the value of first element.

### :pushpin: Example

```
push(1)
pop()     // return 1
push(2)
push(3)
top()     // return 2
pop()     // return 2
```

### :bulb: Solution

```python
class MyQueue:

    def __init__(self):
        self.stack1 = []
        self.stack2 = []

    def push(self, element):
        self.stack1.append(element)

    def top(self):
        if self.stack2:
            return self.stack2[-1]
        elif self.stack1:
            while self.stack1:
                self.stack2.append(self.stack1.pop())
            return self.stack2[-1]

    def pop(self):
        if self.stack2:
            return self.stack2.pop()
        elif self.stack1:
            while self.stack1:
                self.stack2.append(self.stack1.pop())
            return self.stack2.pop()
```





