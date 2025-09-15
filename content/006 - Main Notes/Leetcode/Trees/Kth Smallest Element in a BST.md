
2025-01-22  20:07

Status: #child 

Tags: #leetcode #leetcode-medium #trees [[Leetcode]]

# [Kth Smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst/)

### Code

```python
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution(object):
    def kthSmallest(self, root, k):
        """
        :type root: Optional[TreeNode]
        :type k: int
        :rtype: int
        """
        self.res = []

        def dfs(cur):
            # base case
            if not cur:
                return

            self.res.append(cur.val)
            dfs(cur.left)
            dfs(cur.right)

        dfs(root)

        return sorted(self.res)[k - 1]
```

### Explanation
- Honestly Ivan this is so simple that you didn't even need Neetcode's help!!
- Perform  and sort of traversal(Preorder, Inorder, Postorder) and append the val of the node to a global list variable
- sort the list and return the kth index which will be the kth smallest value in the BST
## References

