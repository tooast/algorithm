### :page_facing_up: Description

Reverse a linked list from position m to n.

Given m, n satisfy the following condition: 1 ≤ m ≤ n ≤ length of list.

### :pushpin: Example

Given `1->2->3->4->5->NULL`, m = `2` and n = `4`, return `1->4->3->2->5->NULL`.

### :bulb: Solution

```python
"""
Definition of ListNode

class ListNode(object):

    def __init__(self, val, next=None):
        self.val = val
        self.next = next
"""
class Solution:
    """
    @param: head: n
    @return: The new head of reversed linked list.
    """
class Solution:
    """
    @param: head: ListNode head is the head of the linked list 
    @param: m: An integer
    @param: n: An integer
    @return: The head of the reversed ListNode
    """
    def reverseBetween(self, head, m, n):
        if m == n:
            return head
            
        dummyhead = ListNode(0)
        dummyhead.next = head
        pre = dummyhead
        
        for _ in range(m - 1):
            pre = pre.next
            
        head = pre.next
        before = None
        
        for _ in range(n - m + 1):
            next = head.next
            head.next = before
            before = head
            head = next
            
        # link three parts together    
        pre.next.next = head
        pre.next = before
        
        return dummyhead.next
      
```





