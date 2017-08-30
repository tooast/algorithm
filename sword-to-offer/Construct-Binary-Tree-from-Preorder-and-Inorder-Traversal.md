### :page_facing_up: Description

Given preorder and inorder traversal of a tree, construct the binary tree.

### :pushpin: Example

Given in-order `[1,2,3]` and pre-order `[2,1,3]`, return a tree:

```
  2
 / \
1   3
```

### :bulb: Solution

```python
"""
Definition of TreeNode:
class TreeNode:
    def __init__(self, val):
        self.val = val
        self.left, self.right = None, None
"""
class Solution:
    """
    @param preorder : A list of integers that preorder traversal of a tree
    @param inorder : A list of integers that inorder traversal of a tree
    @return : Root of a tree
    """
    def buildTree(self, preorder, inorder):
        if len(preorder) == 0 or len(inorder) != len(preorder):
            return None
        root = TreeNode(preorder[0])
        pos = inorder.index(preorder[0])
        
        root.left = self.buildTree(preorder[1:pos + 1], inorder[:pos])
        root.right = self.buildTree(preorder[pos + 1:], inorder[pos + 1:])
        return root
```





