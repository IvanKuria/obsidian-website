---
title: "Subsets"
type: problem
difficulty: medium
techniques:
  - backtrack
date: 2025-09-11
maturity: growing
tags:
  - leetcode
  - cs
  - problem
---
**Topic:** [[Backtracking Intro]] | [[Leetcode MOC]]


# [Subsets](https://leetcode.com/problems/subsets/)

### Code

```python
class Solution(object):
    def subsets(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """

        res, sol =  [], []
        n = len(nums)

        def backtrack(i):
            if i == n:
                res.append(sol[:])
                return
            
            # not choose(go right)
            backtrack(i + 1)

            # choose(go left)
            sol.append(nums[i])
            backtrack(i + 1)
            sol.pop()

        backtrack(0)
        return res
```

### Explanation
1. The solution requires taking two paths; one where you don't pick the num at i, and one where you do
2. You'll have two global lists, res to store a copy of sol and sol to store the current nums at i
3. **Base case**: when i is out of range we want to append a copy of sol into res and return
4. **Right**: this case we just call backtrack recursively on i + 1
5. **Left**: 3 things are done here:
	1. We append the current nums at i into sol
	2. We call backtrack recursively on i + 1
	3. We perform sol.pop() in an effort to undo our previous decision


## References

[Greg Hogg](https://www.youtube.com/watch?v=L0NxT2i-LOY)
