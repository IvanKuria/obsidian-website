---
title: "Count Square Submatrices with All Ones"
type: problem
difficulty: medium
techniques:
  - backtrack
  - dynamic-programming
date: 2025-09-19
maturity: evergreen
tags:
  - leetcode
  - cs
  - problem
---

# [Count Square Submatrices with All Ones](https://leetcode.com/problems/count-square-submatrices-with-all-ones/)
### Code

```python
class Solution(object):
    def countSquares(self, matrix):
        """
        :type matrix: List[List[int]]
        :rtype: int
        """
        ROWS, COLS = len(matrix), len(matrix[0])
        cache = {}

        def dfs(r, c):
            # base case
            if r == ROWS or c == COLS or matrix[r][c] == 0:
                return 0
            if (r, c) in cache:
                return cache[(r, c)]

            cache[(r, c)] = 1 + min(
                dfs(r, c + 1),
                dfs(r + 1, c),
                dfs(r + 1, c + 1)
                )

            return cache[(r, c)]

        res = 0
        for r in range(ROWS):
            for c in range(COLS):
                res += dfs(r, c)

        return res
```

### Explanation
![[leetcode-count-square-submatrices-grid.png]]
1. Given an array like this, the tip to solving this problem is checking the minimum square that can be created from each point.
2. Let's use the bottom right 1 as an example. We'll check the right, down and diagonal point relative to the 1 and see the minimum square that can be created.
	1. **right**: 0
	2. **bottom**: 0
	3. **diagonal**: 0
	4. We return 1 because just the 1 can be made into a square
3. We then do this for every element except for 0.
4. The base case is if the row or col goes out of bounds or if the current element is a 0: return
5. Ideally, we want to cache our results to save time.
	1. This is done by adding the (r, c): length to the dict if they aren't already in there.
## References

[Neetcode](https://www.youtube.com/watch?v=5Li-cR5h_uw)
