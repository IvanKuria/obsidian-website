
2025-09-17  13:19

Status: #child

Tags: #leetcode #leetcode-medium #graphs [[Graphs Intro]] [[Leetcode]]

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

**Time and Space**: $O(m * n)$
## References

[Greg Hogg](https://www.youtube.com/watch?v=rowp_Frq_eI)