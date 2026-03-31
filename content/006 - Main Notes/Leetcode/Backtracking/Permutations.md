---
title: "Permutations"
type: problem
difficulty: medium
techniques:
  - backtrack
date: 2025-09-15
maturity: evergreen
tags:
  - leetcode
  - cs
  - problem
---

# [Permutations](https://leetcode.com/problems/permutations/)

### Code

```python
class Solution(object):
    def permute(self, nums):
        """
        :type nums: List[int]
        :rtype: List[List[int]]
        """
        
        res, sol = [], []
        n = len(nums)

        def backtrack():
            # base case
            if len(sol) == n:
                res.append(sol[:])
                return

            for num in nums:
                if num not in sol:
                    sol.append(num)
                    backtrack()
                    sol.pop()

        backtrack()
        return res
```

### Explanation
1. similar to the [[Subsets]] problem except backtrack doesn't take any parameters

**Base Case(s)**: when length of sol = length of nums
**Choices**: all permutations of the elements in nums
**Constraints**: each element can only be used once in a permutation
**Backtracking Step**: Pop the last number added

## References

[Greg Hogg](https://www.youtube.com/watch?v=gFm1lEfnzUQ)
