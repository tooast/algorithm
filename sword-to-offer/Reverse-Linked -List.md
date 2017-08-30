### :page_facing_up: Description

Reverse a linked list.

### :pushpin: Example

For linked list `1->2->3`, the reversed linked list is `3->2->1`

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
    def reverse2(self, head):
        if not head:
            return None
        before = None
        next = None
        while head:
            next = head.next
            head.next = before
            before = head
            head = next
        return before
    
    def reverse(self, head):
        if not head:
            return None
        if not head or not head.next:
            return head
        reversed = self.reverse(head.next)
        head.next.next = head
        head.next = None
        return reversed
```





