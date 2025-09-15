
2025-01-06  13:28

Status: #child

Tags: #leetcode #leetcode-easy #trees #binary-trees [[Leetcode]]

# [Invert Binary Tree](https://leetcode.com/problems/invert-binary-tree/)

### Code

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution(object):
    def invertTree(self, root):
        """
        :type root: Optional[TreeNode]
        :rtype: Optional[TreeNode]
        """
        if not root:
            return 

        temp = root.left
        root.left = root.right
        root.right = temp
        self.invertTree(root.left)
        self.invertTree(root.right)
        return root
```

![[Pasted image 20250106132952.png]]
### Explanation
- pretty self explanatory but store one of the roots(root.left) in a temp and the rest is easy

## References

