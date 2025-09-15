
2025-01-19  12:05

Status: #child

Tags:  #leetcode-easy #leetcode #trees [[Leetcode]]

# [Maximum Depth of Binary Tree](https://leetcode.com/problems/maximum-depth-of-binary-tree/)

### Code

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def maxDepth(self, root):
        """
        :type root: TreeNode
        :rtype: int
        """  
        # base case
        if not root:
            return 0
            
        max_right = self.maxDepth(root.left)
        max_left = self.maxDepth(root.right)

        return 1 + max(max_right, max_left)
```

### Explanation

Think of recursion as a series of nested function calls. Here's what happens:

1. The function is called on the root node of the tree.
2. It makes recursive calls on `root.left` and `root.right` to find the maximum depth of the left and right subtrees.
3. This process continues until the base case (`if not root`) is reached, where `0` is returned.

When recursion starts returning values, it goes back up the call stack:

- For each node, `max(max_right, max_left)` computes the maximum depth of its left and right subtrees.
- Adding `1` includes the depth of the current node.

### Example

        1
       / \
      2   3
     /
	4

- **Node 1** calls `maxDepth(root.left)` and `maxDepth(root.right)`.
- For **Node 2**, `maxDepth(root.left)` calls `maxDepth(Node 4)`:
    - **Node 4** has no children, so `maxDepth(root.left)` and `maxDepth(root.right)` both return `0`. Thus, `maxDepth(Node 4) = 1 + max(0, 0) = 1`.
- **Node 2** now calculates `maxDepth = 1 + max(1, 0) = 2`.
- **Node 3** has no children, so `maxDepth(Node 3) = 1 + max(0, 0) = 1`.
- **Node 1** finally calculates `maxDepth = 1 + max(2, 1) = 3`.

## References

