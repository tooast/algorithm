### :page_facing_up: Description

Implement an algorithm to delete a node in the middle of a singly linked list, given only access to that node.

### :pushpin: Example

Linked list is `1->2->3->4`, and given node `3`, delete the node in place `1->2->4`

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
    # @param node: the node in the list should be deleted
    # @return: nothing
    def deleteNode(self, node):
        if not node:
            return
        if not node.next:
            node = None
            return
        node.val = node.next.val
        node.next = node.next.next
        return
```





