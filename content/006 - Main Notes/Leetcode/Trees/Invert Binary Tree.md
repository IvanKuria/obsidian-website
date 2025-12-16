
2025-01-06  13:28

Status: #child

Tags: #leetcode #leetcode-easy #trees #binary-trees #computer-science  [[Leetcode]]

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
1. If the root is None, return  
  
2. Set tmp = root.left(you'll see why)  
  
3. root.left = root.right because we're inverting the positions  
  
4. root.right = tmp because root.left got overidden  
  
5. Call self.invertTree(root.left) and self.invertTree(root.right)  
  
6. Return root

## References

