---
title: "Max Area of Island"
type: problem
difficulty: medium
techniques:
  - graphs
date: 2025-09-17
maturity: growing
tags:
  - leetcode
  - cs
  - problem
---
**Topic:** [[Graphs Intro]] | [[Leetcode MOC]]


# [Max Area of Island](https://leetcode.com/problems/max-area-of-island/)

### Code

```python
class Solution(object):
    def maxAreaOfIsland(self, grid):
        """
        :type grid: List[List[int]]
        :rtype: int
        """
        m, n = len(grid), len(grid[0])
        res = 0
        cur = 0

        def dfs(i, j):
            if i < 0 or i >= m or j < 0 or j >= n or grid[i][j] != 1:
                return 0 
            else:
                grid[i][j] = 0
                return 1 + dfs(i, j + 1) + dfs(i + 1, j) +dfs(i, j - 1) + dfs(i - 1, j) 
        
        for i in range(m):
            for j in range(n):
                if grid[i][j] == 1:
                    res = max(res, dfs(i, j))

        return res
```

### Explanation
1. For each element in the matrix iff element = 1, res will be the max of res and dfs(i, j). But what is dfs in this case?
2. **Base case**: we need to check if the indices are out of bounds(less than 0, greater than n or m) and if the current element is not 1
3. **Else**: we change the element from 1 to 0 to indicate that we're done. 
4. **Return**: 1 + dfs to the right, top, left, bottom
5. Then return res at the end

**Time and Space**: $O(m * n)$
## References

[Greg Hogg](https://www.youtube.com/watch?v=rowp_Frq_eI)
